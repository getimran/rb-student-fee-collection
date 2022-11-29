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
    Postman Collection can be found in current repo
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
    Postman Collection can be found in current repo
    <br/>

<h3>rb-view-reciept-service</h3>
    <p>View Receipt Service is used to view receipt based of studentId or txnReferenceId (receipt no)<br/>
API:<br/>
<li>POST - /rakbank/api/receipt/student/{studentId} (VIEW RECEIPT BY STUDENT_ID - check swagger for more details)</li>
<li>GET - /rakbank/api/receipt/{referrenceId} (VIEW RECEIPT BY REFERENCE_ID - check swagger for more details)</li></p>
    Repository: <a href="https://github.com/getimran/rb-view-reciept-service">
                https://github.com/getimran/rb-view-reciept-service</a><br/>
    Local Swagger URL: <a href="http://localhost:8084/rakbank/api/view-receipt/swagger-ui.html">
http://localhost:8084/rakbank/api/view-receipt/swagger-ui.html</a> <br/>
    Postman Collection can be found in current repo
    <br/>

