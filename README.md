Download Link: https://assignmentchef.com/product/solved-csi235-lab6
<br>
<strong>Logical design and implementation of BSON documents</strong>

<strong> </strong>Consider the following conceptual schema of a sample database that contains information about the transportation companies that own the trucks and employ the drivers.

Transform a conceptual schema given above into a logical schema of BSON document. To draw a logical schema of BSON document you can use a graphical notation presented in the lecture slides 22 BSON DESIGN.

<u>An important objective of the design is to maximize the size and complexity of hierarchical</u> <u>structures in a database and in the same moment to eliminate any redundancies from a</u> <u>database.</u>

Next, use a diagram of a logical schema created in the previous step to implement JSON schema, that can be used to validate the documents, that contain information about transportation companies, drivers, and trucks.

Next, create a MongoDB script solution1.js that performs the following actions.

<ul>

 <li>First, the script creates a collection task1 using a method createCollection() with the JSON schema implemented in the previous step as a validator (see a presentation 21 Validation with JSON Schema).</li>

 <li>Next, the script inserts into a collection task1 the documents that contains information about one transportation company that owns two trucks and employs two employees. The documents must validate well against JSON schema used as a validator for a collection task1. The documents must contain meaningful data and the types of values associated with the keys must be consistent with the meanings of the keys. For example, a value associated with a key “date of birth” must be of type date.</li>

 <li>Next, the script inserts into a collection task1 the documents that contains information about one transportation company that owns two trucks and employs two employees. One of the documents must fail validation against JSON schema used as a validator for a collection task1. The documents must contain meaningful data and the types of values associated with the keys must be consistent with the meanings of the keys. For example, a value associated with a key “date of birth” must be of type date.</li>

 <li>Finally, the script prints the explanations on why one of the documents failed the validation. A simple way to print the explanation is to use print(“text’).</li>

</ul>

To process a script solution1.js and to create a report solution1.lst from processing of a script, perform the following steps.

<ul>

 <li>Use gedit editor to open a file js with the implementations of the actions listed above.</li>

 <li>Select the entire contents of gedit window and Copy it into a buffer.</li>

 <li>Open a new Terminal window and start mongo client in the following way.</li>

</ul>

mongo –port 4000

<ul>

 <li>Paste the contents of the buffer copied earlier from gedit window in front of &gt; prompt of mongo You may have to press Enter key to process the last data manipulation in a case when it is not followed by a newline control character.</li>

 <li>Select the entire contents of the Terminal window and Copy&amp;Paste it into a file lst. Save a file solution1.lst.</li>

</ul>

<strong>Deliverables </strong>

A file solution1.lst with a report from processing of MongoDB script solution1.js that creates a collection task 1 with JSON validator and inserts the documents into the collection. Do not forget about the explanations why one of the documents failed the validation.

Please remember that:

– a report without listings of the processed methods scores no marks, – a report that contains any kind of processing errors scores no marks.

<u>                                                                                                                                                            </u>

<h1>Prologue 2</h1>

Start MongoDB server in a way explained in<strong> Prologue 1</strong>.

Next, open a new Terminal window and use the following command to start a command line client mongo.

mongo –port 4000

Download to your virtual machine the files: bsontpchr.bmp, customer.zip, part.zip, and supplier.zip from a section SAMPLE DATABASES on Moodle.

Unzip the files: customer.zip, part.zip, and supplier.zip.

You should get the files: customer.js, part.js, and supplier.js.

To create a collection tpchr and to load the documents into the collection, process the scripts customer.js, part.js, and supplier.js. at &gt; prompt of mongo client in the following way.

load(“customer.js”); load(“part.js”); load(“supplier.js”);

A logical schema of a collection tpchr is available in a file bsontpchr.bmp. It is strongly recommended to make yourself familiar with a logical schema of a sample database.

Next, you can use the methods

db.orders.find().count() and   db.orders.find().pretty()

to count the total number of the documents in a collection tpchr and to list all documents in a pretty format.

Next try few simple queries.

For example, to list information about a hierarchy of parts process a method:

db.tpchr.find({“PART”:{$exists:true}}).pretty();

For example, to list information about a customer who has a customer key equal to 7 process a method:

db.tpchr.find({“CUSTOMER.customer key”:7}).pretty();

For example, to list information about a customer who submitted an order that has an order key equal to 7 process the following method:

db.tpchr.find({“CUSTOMER.submits.ORDER.order key”:7}).pretty();

For example, to list information about the parts of type LARGE BRUSHED BRASS process the following method.

db.tpchr.find({“PART.type”:”LARGE BRUSHED BRASS”}).pretty();

No report is expected from implementation of the actions included in <strong>Prologue 2</strong> section.

<u>                                                                                                                                                </u>

<strong>Task 2 (1 mark) </strong>

<strong>Implementation of simple queries in MongoDB </strong>

Download and unzip a file solution2.zip. You should get a file solution2.js. The file contains the comments with the specifications of the following 5 queries.

Use the methods find() and pretty() to implement the following queries.

<ul>

 <li>Display in a pretty format information about the total number of customers who submitted empty orders, i.e. orders with no lines.</li>

 <li>Display in a pretty format information about the available quantities of parts (availqty), that have retail price greater than 908. List only information about the available quantities, and retail prices.</li>

 <li>Display in a pretty format information about the customers from the nations of JORDAN or MALAWI. Do not list information about the submitted orders.</li>

 <li>Display in a pretty format information about the customers whose account balance (acctbal) is less then 122 and about the parts that have size less than 3. In a relation to customers, list only information about the customer keys and account balances. In a relation to parts, list only information about part key and part size.</li>

 <li>Display in a pretty format information about the part keys and the supplier keys of all suppliers who supplied at least one part that has a retail price equal to 909 and a size equal to 12.</li>

</ul>

Implement the queries in a query language of MongoDB, i.e. use the methods find() and pretty() to implement the queries. Write your solutions into a file solution2.js into the empty slots following a specification of each query. Do not remove the specifications of the queries and semicolons following the specifications !

When ready create a report from processing of the queries in the following way.

Use gedit editor to open a file solution2.js with the specifications of the queries and implementations of the queries.

Select the entire contents of the file and Copy it into a buffer.

Open a new Terminal window and start mongo client in the following way.

mongo –port 4000

Paste the contents of the buffer copied earlier from gedit window in front of &gt; prompt of mongo client. You may have to press Enter key to process the last query in a case when it is not followed by a newline control character.

Select the entire contents of the Terminal window and Copy&amp;Paste it into a file solution2.lst. Save a file solution2.lst.

<strong>Deliverables </strong>

A file solution2.lst with a report from processing of MongoDB script solution2.js with the implementation of the queries listed above.

And again, please remember that:

<ul>

 <li>a report without the specifications of the queries and listings of the processed queries scores no marks,</li>

 <li>a report that contains any kind of processing errors scores no marks.</li>

</ul>


