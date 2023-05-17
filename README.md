# Assigiment_Microservices

Candidates need to Speed up their workflow by adding snippets of
their code to the given assignment while keeping their IDE fully
integrated so that it runs in the web browser. Take your code
and add it as an image or upload the PDF file shared it over the
mail
Question 1: Lottery System
Flow:
a. Calculation microservice -> Winner Microservice
b. Caller -> Rest Api -> Winner Microservice
Scenario
Calculation -> lottery ids are sent to Winner service. Today its 100, tomorrow its
1000 and so on. No control on the number of lottery ids which are pushed from the
upstream. These are sent once every day at 12am midnight.
Winner -> Take the integers and store it in a Storage. During the day, the only
operation is search on the Storage. O(1)
Rest Api -> checkNumber(int num) -> Check in Storage -> true if present, false if not
present. storage.get(num);
Which Storage will you use for this scenario in the Winner service?
Storage can be an inbuilt collection(List, Map, Set, Array etc) or a database.
12am -> Push
6am -> winner service goes down
6:10am -> winner is up
Question 2:
Bank App -> Many Accounts
Account -> account_id, balance
1 Account -> many Users
A1 -> U1, U2
A2 -> U3, U4
User -> user_id, Name
Each user does credit and debit on the account balance
Credit scenario -> Account balance cannot go beyond 10 million
Debit scenario -> Account balance cannot go below 0
Operation: Multiple users can do credit and debit on a single account at the same
time.
Microservice: Transaction
Rest Api -> Credit api, Debit Api
credit(user_id, amount)
debit(user_id, amount
