goto :
https://internal.paypalinc.com/sitenotebooksv2/user/pamoghe/lab? 
	OR
go/sitenotebooks

//also below query provided can be used coming from trex flow.
INTERNAL_MSG_LINKING_ID is   engine activity ID from trex .
open a new query and enter
%%oracle -db pes
select * from PES_PDS_MSG_STORE where rownum < 10  and INTERNAL_MSG_LINKING_ID = '21195639438594417'

copy the payload

open https://te-testonia.qa.paypal.com:22074/index.html
paste the payload in box 9 for decompressing (remove any additional white spaces that might have got added)

copy the result into a new file in intellij .

replace  /" with "

select all
 command + option + L
