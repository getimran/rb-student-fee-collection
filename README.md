# rb-student-fee-collection
Student Fee Collection System is an application for collecting Student fees.


The application is built on distributed microservices architecture. Below mentionioned microservices are involved.

<h3>rb-student-service</h3>
<p>Student services to add new students and retrieve student details based on studendId.<br/>
API:<br/>
<li>POST - /rakbank/api/student (ADD STUDENT - check swagger for more details)</li>
<li>GET - /rakbank/api/student/{studentId} (GET STUDENT BY STUDENT_ID - check swagger for more details)</li></p>
    Repository: <a href="https://github.com/getimran/rb-student-service">
                https://github.com/getimran/rb-student-service</a><br/>
    Local Swagger URL: <a href="http://localhost:8080/rakbank/api/student/swagger-ui.html">
                        http://localhost:8080/rakbank/api/student/swagger-ui.html</a><br/>
    Postman Collection and Swagger file can be found in current repo
    <br/>

<h3>rb-fee-collection-service </h3>
    <p>Fee Collection Service is used to collect fee based on studentId. <br/>
    Retrieve Fee details based on studentId or txnReferenceId (receipt no)<br/>
API:<br/>
<li>POST - /rakbank/api/fee/collect (COLLECT FEE - check swagger for more details)</li>
<li>GET - /rakbank/api/fee/student/{studentId} (GET FEE DETAIL BY STUDENT_ID - check swagger for more details)</li>
<li>GET - /rakbank/api/fee/{referenceId} (GET FEE DETAIL BY REFERENCE_ID - check swagger for more details)</li></p>
    Repository: <a href="https://github.com/getimran/rb-fee-collection-service">
 https://github.com/getimran/rb-fee-collection-service </a><br/>
    Local Swagger URL: <a href="http://localhost:8082/rakbank/api/fee-collect/swagger-ui.html">
                        http://localhost:8082/rakbank/api/fee-collect/swagger-ui.html</a> <br/>
    Postman Collection and Swagger file can be found in current repo
    <br/>

<h3>rb-view-reciept-service</h3>
    <p>View Receipt Service is used to view receipt based of studentId or txnReferenceId (receipt no)<br/>
API:<br/>
<li>GET - /rakbank/api/receipt/student/{studentId} (VIEW RECEIPT BY STUDENT_ID - check swagger for more details)</li>
<li>GET - /rakbank/api/receipt/{referrenceId} (VIEW RECEIPT BY REFERENCE_ID - check swagger for more details)</li></p>
    Repository: <a href="https://github.com/getimran/rb-view-reciept-service">
                https://github.com/getimran/rb-view-reciept-service</a><br/>
    Local Swagger URL: <a href="http://localhost:8084/rakbank/api/view-receipt/swagger-ui.html">
http://localhost:8084/rakbank/api/view-receipt/swagger-ui.html</a> <br/>
    Postman Collection and Swagger file can be found in current repo
    <br/>

<h3>END USER API'S:</h3>
<li>POST - /rakbank/api/student (ADD STUDENT - add new students)</li>
<li>POST - /rakbank/api/fee/collect (COLLECT FEE - collect fee for a student)</li>
<li>GET - /rakbank/api/receipt/student/{studentId} (VIEW RECEIPT BY STUDENT_ID - view receipt based on studentId)</li>
<li>GET - /rakbank/api/receipt/{referrenceId} (VIEW RECEIPT BY REFERENCE_ID - view receipt based on referenceId)</li>

<h3>Let's understand flow</h3>

<li><strong>rb-student-service</strong> is used to add new students in H2 databases, and student can be retrieved using studentId.</li><br/>
<li><strong>rb-fee-collection-service</strong> is used to collect student fee based on studentId. Once request is received in /collect service, /student service is called to check if student exists or not. <br/><br/>
If student exists fee collection gets process and txnReferenceId gets generated and txn details gets saved in H2 database. <br/><br/>
If student doesn't exists fee collection doesn't happen.</li>
<br/><br/>
<li><strong>rb-view-reciept-service</strong> is used to view receipt based on studentId or txnReferenceId.</li>
<br/><br/>
When request id received to view receipt based on studentId, then /student service is called to get student details and /fee/student/{studentId} service is called to get all fees paid by that student and final view receipt response is sent.
<br/><br/>
When request id received to view receipt based on referenceId, then /fee/{referenceId} service is called to get the fee details of specified referenceId. From fee response student id is retrieved and the /student service is called to get student details and final view receipt response is sent.


<h3>How to run in your local?</h3>
<strong>Please visit each repository link provided above and clone it, follow README.md to run in your local.</strong>
