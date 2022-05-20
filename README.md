# T2A2-Two-sided Marketplace application

Visit the site: [UberRed (Hosted on Heroku)](https://infinite-atoll-55873.herokuapp.com/)

Github:

## Installation and setup

- If you would like to setup this Applicaiton on your personal machine these are the steps required.

  <details>
  	<summary>
  		<b> Instructions </b>
  	</summary>


  -   fork and clone
  -   bundle install
  -   update  `config/database.yml`  with your postgresql username & password
  -   update  `config/credentials.yml`  with your cloudinary api key. In order to decrypt the file to edit, type  `EDITOR='code --wait' rails credentials:edit`  into your command line.
  -   `rails db:setup`  - setup the database
  -   `rails db:schema:load`  - load the schema for the database
  -   `rails db:seed`  - load the items into the database
  -   `rails s`  to run the server


## Problem & why we need solve it

_**UberRed**_  is a Uberish Web application special for the disabled group. The transportatoin for disability people is not that perfect, which is a great barrier to them to see the world as other people. The _**UberRed**_  is planning to solve their trouble to help them enjoy the world. In this web application, the drivers will provide the vehicles with wheelchair hoist, and other useful equipments ( updating) to meet the disabled traveler requirement to help with them transportation. 

## Functionality and Features

_**UberRed**_ is a vehicle booking web application to help the drivers and disability community for the effictive transportation.

For **Driver** : If the user sign-up and be a driver , they can **create their vehicles** on the systme with special attribute such as *wheelchair-hoist* and others (under-updating) . They also can **view their pending bookings**  and **cancel the booking** if they don't want to.

For **Traveler** : if the user sign-up as a traveler, they can **view all the vehicles** on the web and **make a booking** to the vehicle meet their requirement,and **cancle the booking** if they don't need it anymore. 

## Site map

![Sitemap](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/Sitemap.png)

## Screenshots

![Home](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/screenshot/Home.png)



[All other screenshot images](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/screenshot)

## Tech stack

<details>
	<summary>
		<b> Ruby on Rails </b>
	</summary>

Ruby on Rails, or Rails, is a server-side web application framework written in Ruby under the MIT License. Rails is a model–view–controller framework, providing default structures for a database, a web service, and web pages
	
[Ruby on Rails](https://guides.rubyonrails.org/)

[Ruby](https://ruby-doc.org)

</details>

<details>
	<summary>
		<b> PostgreSQL </b>
	</summary>

PostgreSQL is a free and open-source relational database management system emphasizing extensibility and technical standards compliance built on the SQL language. It is designed to handle a range of workloads, from single machines to data warehouses or Web services with many concurrent users.
	
[PostgreSQL](https://www.postgresql.org)

</details>

<details>
	<summary>
		<b> HTML 5 </b>
	</summary>
HTML5 is a software solution stack that defines the properties and behaviors of web page content by implementing a markup based pattern to it. HTML5 is the fifth and current major version of HTML, and subsumes XHTML. HTML was used for our web front end.
	
[HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)
</details>

<details>
	<summary>
		<b> Bootstrap</b>
	</summary>
Bootstrap, the world’s most popular framework for building responsive, mobile-first sites. Bootstrap was used for all styling and interactive components on the site. Bootstrap was used for its ease of use, aesthetic appeal, numerous components, JS integrations and responsive first properties. Bootstrap speeds up front end development immensely.

[Bootstrap](https://getbootstrap.com)

</details>

## Ruby Gems

 <details>
	<summary>
		<b> Devise </b>
	</summary>
Devise is used for user authentication. Everything from Login, Sessions, Secure passwords and more.

[Devise Gem](https://rubygems.org/gems/devise/versions/4.2.0)
</details>

<details>
	<summary>
		<b> Rolify </b>
	</summary>
Rolify was first originally used in this Appliction for user Authorisation. However it was conflicting with Heroku, resulting in it being uninstalled. Users are now all Authorised by their user id. Many actions will only go through if they are signed in with devise and their current user id matches the resources attached user id.

[Rolify Gem](https://rubygems.org/gems/rolify)
</details>

<details>
	<summary>
		<b> Cloudinary </b>
	</summary>
The Cloudinary gem is used for the integration of the 3rd party service cloudinary. This is used for image uploads through the applicaiton.

[Cloudinary Gem](https://rubygems.org/gems/cloudinary)

</details>

## User Stories

- Usesr have two sides -- drivers and travelers.
- Users can view all the vehicles on the web with Sign-in.
- Users can sign-up to create an account.
- Users can log-in and log-out.

#### For Drivers

- Users as driver can create their own vehicle specifications on the web .
- Users as driver can edit their vehicles.
- Users as driver can upload their vehicles pictures
- Users as driver can cancel the booking sent from the traveler.
- Users as driver can delete their vehicle not to accpet the bookings from the traveler.

#### For Travelers

- Users as traveler can make a booking which Meer their standards.
- Users as traveler can cancel the booking if they don't need the vehicle any more.

## Wireframes

![Wireframe](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/Wireframe.png)

## ERD and Database structure

![EDR](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/EDR.png)



Ruby on Rails database is basing on active record associations, which relay on the relationships between the different models. In every table, There will be pprimary key and forenigner key. This project is using postgreSQL as database manage system. I firstly generate the models woth the commond line ``rails g model Modelname column:datatype`` . After this tep we generate models and set up the realtionship between diffrenet models. At same time, we have created a ``migration`` file which contain the information about strcuture of our tables in the database. Then we run ``rails db:migrate`` to create the``schema`` file, which at same time push the migration file structures into database.

My database focuses on users and vehicles. Users create vehicles, and vehicels used by the users. The user also can create the order over the vehicle_id, which mean **a client make an order on a specific vehicle.** ``Devise gem`` helps in creating users. And thanks to the ``	Rolify gem`` , we give users  two roles options, one is Driver, and another is Traveler. And relaying on ``Pundit gem`` we create policies, give different roles different authorization.

On one hand, a user with Driver role can create only one vehicle, he can also view, edit and delete the vehicle he creates as well. On the other hand, a user with Traveler role can view all the vehicles content, and he can make a booking to which ever vehicles as long as the vehicle does not belong to him.

## Components(abstractions )

- Conditional rendering -- on the index page, under different condition will dispaly different amount of vehicles. Such as , as a driver, it will only show the vehicle belongs to the current log in driver. He can only edit and delete his car . If no user logging in or loged in user is a traveler, he can view all the vehicles content to make a booking. 
- Different authroization with different roles-- a driver can create ,edit and delete the vehicle belongs to him . A travel can not do that. A traveler acan make a booking and cancel the booking as well, but the driver can not do that to his own car after he use the same email changing the role to be a traveler.

## Third Party Services

<details>
	<summary>
		<b> Cloudinary </b>
	</summary>
Cloudinary is a image cloud hosting service that allows you to off-load the tasks of uploading and handling image assests. Cloudinary dynamically optimises your content and delivers it in a fast and efficient manner. 

[Cloudinary](https://cloudinary.com/)

</details>

<details>
	<summary>
		<b> Heroku </b>
	</summary>
Heroku is a container-based cloud Platform as a Service (PaaS). Developers use Heroku to deploy, manage, and scale modern apps. This Appliction makes use of Heroku's free service model for small projects. Heorku also streamlines deployment through its Git integration allowing updates to easily be pushed to Heroku as you would any other remote git repository.

[Heorku](https://www.heroku.com/home)

</details>

<details>
	<summary>
		<b> Github</b>
	</summary>
Last but not least it Github, a developers best friend. GitHub is a website and cloud-based service that helps developers store and manage their code, as well as track and control changes to their code.

[Github](https://github.com/)

</details>

## Task allocation

![Trello](/Users/leslie/Desktop/Coder-Assignment/term_2/Xuefeng_Gu_T2A2/docs/Trello.png)

##### --------Trello KanBan system ,which was used all along the project to chase which  step I have done, and what is the next step.

- 11/05/2022 Get the permission pass the idea about the two side application **UberRed** which help the disabled community transpotation.  Search the gem I may use and a resonable database structures. Have the ERD for the project.

- 12/05/2022 Starting the project setting up the models and the relationships.

- 13/05/2022 rewind the vedio content to summary the working flow, cause having a lot of troubles in coding ,a lot of error because of the databse setting up.

- 14-15/05/2022 chilling weeeeeeekends, I should do something , otherwise I won't writing this README at the very last due day. But may brain said no.

- 16/05/2022 restart setting up the models from the simple and indevidual one. And from the simple one to go up one layer by layer. And generate the controller as well. Doing the ``devise`` gem to give authentication functions to create ``user`` model , as it has relation with other models. 

- 17/05/2022 Doing with the ``view`` part. Fix the bugs in CRUD. 

- 18/05/2022 Doing the ``Rolify`` and ``Pundit`` to give the project authrization function. Setting up different policies between different roles. Starting CSS setting up.

- 19/05/2022 Finishing  CSS  parts, and find part of authorization should be given by conditional rendering in the ``view html`` file. Deploy the web application on Heroku 

- 20/05/2022 Bug fixing (found by my friend, really do not want to fix it  :unamused:) ,finish all the paperwork and ppt.:tada:









