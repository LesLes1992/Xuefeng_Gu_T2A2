



# T2A2-Two-sided Marketplace application




## R7. Problem I planned to solve 

In 2020, there are around 4.2 million ageing people in Australia. At the same time, around 1 in 6 of Australian people are known to have some forms of disability. Vulnerable physical and mental conditions are essentially the major barriers to this group of individuals making it difficult for them to explore and experience the outside world.  Hence, I would like to develop a web application to improve their accessibility to more convenient and friendlier mode of transportation, which would hopefully help them to live a normal life same as everyone else. 

## R8. why we need solve it

_**UberRed**_  is a Uberish web application specially designed to improve ease of transportation for the disabled and ageing communities. Current modes of transportation available for these groups of individuals may not be ideal, which pose a great obstacle for them when it comes to exploring the physical world around them. This web application will help to solve the challenges that they would normally face when making a booking for taxis or rideshares. For instance, residents in the nursing homes may need to make a doctor appointment or plan for their shopping trips weeks in advance. This web application provides feature that allows rideshare drivers to target these special groups of customers and boost their income.  

At present, there are a lot of other marketplace applications focusing on the transportation such as Uber, DiDi, and Grab. However, these applications are generally not focused on transportation with special amenities to support disabled and ageing individuals. This web application allows customers to opt for vehicles which meet their special needs by offering wheelchair hoist or other useful amenities (updating). 

### R9. A link (URL) to your deployed app (i.e. website)

Visit the site: [UberRed Marketplace Application](https://infinite-atoll-55873.herokuapp.com/)

## R10. A link to your GitHub repository (repo).

Github: [Xuefeng_Gu_T2A2](https://github.com/LesLes1992/Xuefeng_Gu_T2A2)

## R11. Description of your marketplace app (website), including:

- **Purpose**

  To help the vulnerable people to find the right vehicle which is suitable for their transportation quickly and easily based on their requirements and needs.

- **Functionality and Features**

  - _**UberRed**_ is a vehicle booking web application to help the disabled and ageing communities find transportation with special amenities such as wheelchair hoist. This web application also enables rideshare drivers to tap into these groups of customers who require special needs.
  - For **Driver** : If the user signs up as a 'driver', they can **create their vehicles** in the system to show availability of special features such as *wheelchair hoist* and others (under-updating) . They also can **view their pending bookings**  and **cancel the booking** if they don't want to.
  - For **Traveler** : If the user signs up as a 'traveler', they can **view all the vehicles** on the web application and **make a booking** for the vehicle which meets their requirement,and **cancel the booking** if they don't need it anymore. 

- **Site map**

  ![Sitemap](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/Sitemap.png)

- **Screenshots**

  ![Home](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/screenshot/Home.png)

  [All other screenshot images](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/screenshot)

- **Tech stack**

  - ***Ruby on Rails***

    Ruby on Rails, or Rails, is a server-side web application framework written in Ruby under the MIT License. Rails is a model–view–controller framework, providing default structures for a database, a web service, and web pages.

    [Ruby on Rails](https://guides.rubyonrails.org/)

    [Ruby](https://ruby-doc.org)

  - ***PostgreSQL***

    PostgreSQL is a free and open-source relational database management system emphasizing extensibility and technical standards compliance built on the SQL language. It is designed to handle a range of workloads, from single machines to data warehouses or Web services with many concurrent users.
    [PostgreSQL](https://www.postgresql.org)

  - ***HTML5***

    [HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)

  - ***Bootstrap***

    [Bootstrap](https://getbootstrap.com)

- **Target audience**

  - Drivers who want to boost their income by offering special vehicles for disabled and ageing communities.
  - Travelers who want to easily find the vehicles that meet their special needs and requirements.
  - Government who wish to see greater support for communities with special needs.



## R12. User Stories 

#### For Users have two sides -- drivers and travelers

***[User story 1]*** For individuals who have not signed up to web application, they are able to view all the vehicles on the web  without signing up. After browsing, they can choose to sign up by creating an account with their email and password. They can also log into and log out from the web application. They can reset their password if they forget their password. They also can choose to be a 'driver' or 'traveler'.

#### For Drivers

- ***[User story 2]*** **Users as driver who want to create(list) their own vehicle specifications on the web .**

  As a 'driver', user should be able to list their vehicles on the web application to enable travelers to view, select and make a booking. 

- ***[User story 3]*** **Users as driver can edit their vehicles.**

  As a 'driver', user can edit their vehicles specifications after making modifications to their vehicles or other changes to their vehicles.

- ***[User story 4]* Users as driver can upload their vehicles photos.**

  As a 'driver', user can upload their vehicle photos to let the customers directly view the vehicles, which may boost their booking rate because customers are likely to be attracted by actual photos.

- ***[User story 5]* Users as driver can cancel the booking from a traveler.**

  As a 'driver', user can cancel the booking from the customer. They can choose to fulfill the order in accordance with their conditions.

- ***[User story 6]*** **Users as driver can delete their vehicle not to accept the bookings from the traveler.**

  As a 'driver', users can choose to delete their vehicles in the system, which means no customers can view and make a booking for their vehicles. They can choose not to be an **UberRed** driver, or have a short break.

#### For Travelers

- ***[User story 7]* Users as traveler can make a booking which meet their requirements.**

  As a 'traveler', users can view all the vehicles in the system, and make a booking according to their requirements and needs. 

- ***[User story 8]*** **Users as traveler can cancel the booking .**

  As a 'traveler', user can choose to cancel the booking when they need to. If they have other plans other than to travel to the initial booking place, they can choose to cancel the order.



## R13. Wireframes

![Wireframe](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/Wireframe.png)



## R14. ERD and Database structure

![EDR](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/EDR.png)



## R15. Components (abstractions) [Need to update]

- User
  - The 'User' table has two attributes which are email and password. Both of them are string type. It has one-to-one relationship with 'Role' table.
  - The 'User' table is built up with the Devise Gem which has basic functions like 'Sign-up', 'Sign-in', 'Log-out', 'Forget Password' and etc. By signing up, user will be able to create an account with email and encrypted password.

- Role
  - Role table has two attibutes which are 'name' and 'resource type'. 'Name' will be the title of the Role while 'resource type' defines the role which class or module it is under.
  - The 'Role' class is built via the Rolify Gem in combination with Devise Gem and Punbit to create authorisation for specific user. Such as, only the 'driver' can create (list) a vehicle on the web, edit the vehicle specifications, and delete the vehicle in the system. At the same time, after a 'traveler' has signed in, he can view all vehicles, make a booking, and cancel the booking.

- Order
  - Order table has three attributes, which include address of the order, foreign keys to User and foreign keys to Vehicle.
  - Order will be listed after the traveler has made a booking. To the driver, he will be able to see the address of the order in order to know the location to pick up the traveler. The traveler will see the vehicle brand and plate number of the vehicle as part of the order information.  Both of the 'driver' and 'traveler' can cancel the order depending on their conditions.

- Vehicle
  - Vehicle would be the most complex table with many attributes. These attributes are the specifications of the vehicle, such as if they have the wheelchair hoist.
  - Vehicle ``belongs_to`` the User and ``has_one`` order. This table attributes will be created and edited by the drivers. A driver can only have one vehicle at a time, as they can only drive one car at a time. But the traveler can make many bookings of the vehicle at the same time. This is achieved by using the conditional rendering.


**For controllers**

As the models above, according to the MVC format, I will have four controllers, which are 'users', 'vehicles', 'roles', 'orders' . Except for the 'roles' controller, the other three controllers have create , read, update and delete methods. The 'roles' will only have update method, as the user will have the default role as 'traveler' which can be updated to 'driver'. The user controller is designed through the Devise Gem, which will help to modify the user controller and actions easily and quickly.

**For models**

This project will contain 4 models, by seperately setting to four models. It will help with future maintenance, which means it will be easier to change the attribute of different entities. It will not change the relationship as we have set up in the model class file.

**For views**

These views are mainly mapping with the actions in different controllers such as vehicles can be listed (created) , edited, viewed ( read) and deleted . Each view will be conditional rendered under different roles authorisation.



## R16. Third Party Services

- [Cloudinary](https://cloudinary.com/) is an image cloud hosting service that allows you to offload the tasks of uploading and handling image assests. Cloudinary dynamically optimises your content and delivers it in a fast and efficient manner. 
- [Heroku](https://www.heroku.com/home) is a deploying platform. Developers use Heroku to deploy, manage, and scale modern applications. This application makes use of Heroku's free service model for small projects. Heroku also streamlines deployment through its git integration allowing updates to be easily pushed to Heroku as you would with any other remote git repository.
- [PostgreSQL](https://www.postgresql.org) is a free and open-source relational database management system emphasising extensibility and technical standards compliance built on the SQL language. It is designed to handle a range of workloads, from single machines to data warehouses or Web services with many concurrent users.



## R17 & R18. Active Record Associations and database relationship.

- User Model

  - ``has_many`` vehicles

    This will be conditional rendered as User with 'driver' role has and only has one vehicle. User with 'traveler' role will have many vehicles.

  - ``has_many`` orders

    This will be conditional rendered as User with 'driver' role has and only has one order. User with 'traveler' role can have many orders at one time.

- Vehicle Model

  - ``belongs_to`` user

    A vehicle can only belong to one driver.

  - ``has_one`` order

    It can has one order at one time.

- Order Model

  - ``belongs_to`` user

    an order can only belong to one user at one time. 

  - ``belongs_to`` vehicle

    an order can only be created via one vehicle at the same time. It cannot contain information for two vehicles.

- Role Model

  - ``has_and_belongs_to_many `` users

    Different users can have the same roles, which mean the same role can belong to different users.

Ruby on Rails database is based on active record associations, which relay on the relationships between the different models. In every table, there will be primary key and foreigner key. This project is using postgreSQL as database manage system. I firstly generate the models with the command line ``rails g model Modelname column:datatype`` . After this step, we generate models and set up the relationship between different models. At the same time, we have created a ``migration`` file which contain the information about structure of our tables in the database. Then we run ``rails db:migrate`` to create the``schema`` file, which at the same time push the migration file structures into database.

My database focuses on users and vehicles. Users create vehicles, and vehicles used by the users. The user also can create the order over the vehicle_id, which mean **a client make an order on a specific vehicle.** ``Devise gem`` helps in creating users. And thanks to the ``	Rolify gem`` , we give users two roles options - one is 'driver', and another is 'traveler'. And relying on ``Pundit gem`` to create policies, we can give different roles different authorisation.

A user with 'driver' role can create only one vehicle, he can also view, edit and delete the vehicle he has created as well. On the other hand, a user with 'traveler' role can view all the vehicles content, and he can make a booking on whichever vehicles as long as the vehicle does not belong to him.



## R19 - Database Schema

Please chech the content under **R14**, which is the ERD for this project.



## R20. Task allocation

![Trello](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/Trello.png)

##### --------Trello KanBan system ,which was used throughout the project to track the steps that I have completed, and identify the next step.

- 11/05/2022 Get the permission to pass the idea about the two side application **UberRed** which help the disabled community transportation.  Search the gem I may use and a reasonable database structures. Have the ERD for the project.

- 12/05/2022 Starting the project and setting up the models and relationships.

- 13/05/2022 Rewind the video content to summarise the working flow, which causes a lot of issues with the coding, a lot of error because of the database setting up.

- 14-15/05/2022 Chilling weekends, I should do something , otherwise I won't writing this README at the very last due day. But my brain said no.

- 16/05/2022 Restart setting up the models from the simple and individual one. And from the simple one to go up one layer by layer. And generate the controller as well. Doing the ``devise`` gem to give authentication functions to create ``user`` model , as it has relationship with other models. 

- 17/05/2022 Doing with the ``view`` part. Fix the bugs in CRUD. 

- 18/05/2022 Doing the ``Rolify`` and ``Pundit`` to give the project authorisation function. Setting up different policies between different roles. Starting CSS setting up.

- 19/05/2022 Finishing  CSS  parts, and find part of authorisation should be given by conditional rendering in the ``view html`` file. Deploy the web application on Heroku 

- 20/05/2022 Bug fixing (found by my friend, really do not want to fix it  :unamused:) ,finish all the paperwork and ppt.:tada:









