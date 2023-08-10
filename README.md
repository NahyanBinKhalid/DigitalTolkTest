# DigitalTolk Test
Conducted By Nahyan Bin Khalid
<hr />

Refractor
-
Points that I noticed are covered by the programmer.
1. The use to Repository Pattern enables the code base to shrink down.
2. It adds another separation layer to the Business Logic and response.
3. In case of Project which has web app and Mobile app and same data is required on both Apps, the repository pattern helps in to reduce data redundency.
4. Most of the normal CRUD operations can be performed by BaseRepositoy and no need of code to be replicate to its own repository.

Points I noticed missed by the Programmer or could be better. 
1. Putting Validation rules in Repository is good but it will be better if they were extending Request Class e.g: BookingRequest.
2. After validation, exception handling is missing try {} , catch {}.
3. Null Safe operator can be used
4. Interfaces binding with Repositories are missing.
5. Its not compulsory but a service layer can be added. If service layer is added, the request, data and business logic can more be segregated.
   1. Controller will be responsible for request.
   2. Service Layer will be responsible for Business Logic to be implemented. if else statements, calculations etc
   3. Repository Layer will be responsible for the data.
6. The Email, Notification and SMS Notifications are processed inline. This has to be done inside Queues with Job::Dispatch(). Inline process will slow down the page load and if the services failed, error handling will be a problem.
7. Namespaces in both Repository Files is not correct.
8. In *BookingRepository->sendPushNotificationToSpecificUsers*, CURL is being used. There no problem using CURL directly but its better to use guzzleHttp as it has better error handling and code reuseability.

Test
-
Points that I noticed are covered by the programmer.
1. Most of the points are same as in above project.
2. Additional positive thing in this project is Helper Function *TeHelper.php*
3. Helper Functions help to hold functions doing small or redundant tasks.

Points I noticed missed by the Programmer or could be better.
1. Most of the negative points in this project are same as the above one.
2. Additionaly I've found that env variables are used directly in code.
3. I personally suggest and use it as define config variables assigning them env variables and than use those config variables in the code.
4. That helps in more meaningful variable names and provide abstraction.
5. When writing tests using config variables, it helps in easy changing of configuration values.
6. Another thing is that config values can be tracked in version control so you have a complete history of the values assigned to them,.