To run any query in MSMASTER / DATABASE
for read queries we goto go/datatrek

Documentation : https://engineering.paypalcorp.com/confluence/display/DeveloperExperience/JAWS+API+Documentation

for update query 
we use JAWS swagger api 
hosted at  :

[http://jaws.paypalcorp.com/v1/QIJawsServices/#!/query/executeQuery](http://jaws.paypalcorp.com/v1/QIJawsServices/#!/query/executeQuery "http://jaws.paypalcorp.com/v1/qijawsservices/#!/query/executequery")

search for execute query .
Payload 


body -> {
  "sqlQuery": "SELECT count(*) from transaction_exception "
}
hostname -> msmaster.qa.paypal.com

dburl -> occ-fpda