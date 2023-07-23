
 
 
 
reverse transaction key ye ek id hai jo customer transaction wale table me ek hi payment me agey wale event ko piche wale event se link karti hai.

Jaise agar pehle payment hui aur fir refund aya. toh refund ki jo rows hongi custpomer transaction me (U rows, @ row, Hash9997 rows) in sab ki corresponding rows jo payment wale event me ke time bani thi unki transaction. key hoti hai.
 
 
 
 
 
 T1  

  

TXN_ID   PAC_ID(partyID)   TXN_TYPE  PAC_TYPE  (txn type code from party additional attributes)

  

1001      1003     9997     U

  

1002      1003     R        U

  

1003      1003     U        U

  

1004      1006     9997     U

  

1005      1006     BAL      U

  

1006      1006     U        U

  

  

  
T2

  

TXN_ID   PAC_ID  TXN_TYPE  PAC_TYPE  REV_KEY  
  
2001      2003    9996     V          1004

  

2002      2003    BAL      V          1005

  

2003      2003    V        V          1003   

  

2004      2006    9996     V          1001

  

2005      2006    T        V          1002

  

2006      2006    V        V          1006