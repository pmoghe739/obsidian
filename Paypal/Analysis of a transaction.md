
	%%oracle -db PYMTSH1

select * from payment_side_action where PAYMENT_SIDE_ID in (21469214112338994,21469214112338993)

This transaction has 2 entries in paymentSide action table and 2 entries in monemmovement action tables which means this is a 2 party transaction basically guy topping up his paypal wallet via bank ACH(Automated cleaaring House).  
  
there are 7 entries in customer transaction table , 4 debit side and 3 credit side, lets have a look at how these all are formed.

Code flow starts at payment data event processor.java

There are 2 parties so  for each party we loop and get instrument txn entities

For each party(payment data event processor.java)

Party 1(DEBIT SIDE) : 2 inst txn from bank (1 PENDING, 1 PROCESSING)

For each inst (Instrumenttxnprocessor.java -> banktranslator.java):

INST 1 : processing status(BANK):

1 CT Entity created for processing row in with txn type code H and subtype code null.

3 txn participant (sender , receiver  and coounter party)

1 txn event

1 BTR

INST 2 : pending status(BANK):

Processing skipped

Now writing stmu0balancetranslator.java cause BAL is not present in above party

[stmu row]1 CT Entity created with txn type code 9991 (this represents the Party(DEBIT SIDE)[STMU0 row][txn id is party id]

Now code goes to Party Data processor

Writing stm_hash rows (stm hash helper)

[hash row]1 CT Entity created with txn type code 9997(this represents the Party(DEBIT SIDE)STM_HASH row)[ for STM HASH row transaction id is same as transaction key]

[u row, base layer row]1 CT Entity created with txn type code U (this represents PARTY, this is similar to STM U0 row above, transaction id is party id, just different is this is type U instead of 9991.

(this above one is base layer entry for party txn earlier only going in customer payment table.)

PARTY 2(CREDIT SIDE)

1 INSTTXN FOR SUCCESS-BAL

For each inst (Instrumenttxnprocessor.java -> Balance translator.java)

	INST 1 : BALANCE :

		1 CT Entity created with txn type code 9991 (this represents the instrument(CREDIT SIDE)[STMU row][txn id is instrument id]

Not writing stmu0balancetranslator.java cause BAL is present in above party

[hash row] 1 CT Entity created with txn type code 9997(this represents the Party(CREDITSIDE)STM_HASH row)[ for STM HASH row transaction id is same as transaction key]

[u row, base layer row] 1 CT Entity created with txn type code U (this represents PARTY, this is similar to STM U row above, transaction id is party id, just different is this is type U instead of 9991.