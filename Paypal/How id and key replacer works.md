
event ids taken from PDS event  and new ids randomly generated.(a map is created  from ids present in pds to new ID)
the request sent to server has reaplced keys from step 1.
response is received.
golden response is stored in FPDA file.
the same map from step 1 is used to replace IDS in golden response.

a new map is created with unique ID for each record as key and transaction key(or other primary key of table) as value for response.

similar map is created for golden response.

a final map is created with key as golden response transaaction key vs actual response transaction key.

keys are replaced in golden response using above map.

Golden response and actual repsonse are compared .
