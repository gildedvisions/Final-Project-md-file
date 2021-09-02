# Light A Candle
A social media experiemnt

My project has a very simple premise. To create something that can outlast the duration of the CS50 course. With that at the back of my mind i aimed to create something that could pring about posivite social change.

I belong to India. Current live and work here, and have seen how the country has really struggle through the second wave of covid. Deaths were in the thousands and those were only the ones that were reported. There were stories of boddies in the thousands getting washed up on the banks of our holy rivers. All this is undocumented and there is no data. there in no voice for the common person cause they have no outlet. In a country of cheap data and internet adoption there was no data on the thousands that have gone missing. 

I set out with one bassic missions in mind which further expanded
- create a way to gather actual covid death figures in the country. I decided to create some sort of a platform that could croud source the information. Maybe a kind of social media experence where the gieving could come and upload orbituaaries for their near and dear loved ones to see. Each orbituary is to have a prayer wall and upon receiving prayers from diffent user of the platform the data in a way is automatically verifyable. 
- this fundamental idea of trying to create a cround sounce of information lead to my second mission. tryin to create a social media experience that in some way can be engaging and interactive. this lead me to create 4 seperate emojies for each orbituary, a set of hand offering prays, a hand offering support, a dove to show peace in the afterlife and a candle which when lit turns goldern. 

It was this last emojie that help me coin the title of my project **Light A Candle**

People come registe with the application and become users. After a user has been created they have many options of interactions.
1. the main one being creating a memory/uplading the orbituary of a loved one. This will basically be a post that they as a user can create, give some basic information about the deceased like location, cause of death, date of birth and date of expiery and a few kind words on thir behalf
2. the application then prcoess this information:
      - if the casue of death is covid or covid related then the user is are directed to a second form that will guide them into entering infomation about their covid experience. this will be where i gather my covid related data from. Besdies covid our county was plagued with count less other problems like lack of medical attention, oxygen shortage, balck fungues deaths. After this the post is created and displyed on the main landing page. No covid related informatin is ever shown or displayed on the site.
      - if the cause of death is not covid related the post will be created and displyed on the main landing page. 
3. any other user that enters the site can now interact with each post/orbituary that is created by offering them upto 4 emojies or enter into the the individual posts page and further offer pray's on the deseased's prayer wall. 
4. There is also a search feature where a user can look up for a post/orbituary using any key words mentioned in the deceased's name, loaction or orbituary text.
5. A side pannel is created that will house the names of the deseased whos death anniversary falls within that current month in a way giving remeberance to thems so they are not forgotten.


## Light a candle: Project Discription 
light a candle in a simple flask application with an SQLLite3 database backend and a Bootstrap front end, though you would think it is much more. The basic flask modules/libraries that helped to acheive this task are broadly 
- Login Manger: to control user login session 
- Flask_wtf and wtforms: to simplify the process of form creation and writing the form validations
- Flask_SQLAlchemy: to create run and interact and act as a brigde between flask and SQLlite and to tackly SQL injection attacks, also can assist is upscaling the project to a larger database application if so required in the furture
- Flask_mail: to send out validation emails for new users registering with the site as well as to complete the forgot password journey
- werkzeug.security: to help with encrypting and checking passwords against the database 
- itsdangerous: to generate time limited tokens for the forgot password route
- flask_migrate: to make edits to the database after its initial creation 

## light a candle: package distribution
the flask app is split into an application package. The run.py file has only one job to start the application with a simple command of python run.py
Inside the candle folder we have the static folder and the templates folder which contain the images/CSS/JS files and the html files respectively, also containded in the candle folder are 
1. /_/_init/_/_py: housing all the configuations for the application 
2. forms.py: containing all the forms and their respective validations
3. models.py: containing the db model classes 
4. routes.py: containing all the app routes
5. passwordcheck.py: a custom program i wrote that checks whether a password when entered at the time of registration meets all the requirments to make it a strong password
6. states.py: a program i wrote to add the names of all the states of the indian teritory and their short forms from a csv into the sqllite database 

## Proud Moments for my project
throughout my project i managed to push many bounderies with things that i had nvr experienced before when its comes to creating or developing this project, but there were a few micro hurdels what i am extreamly proud to have over come
1. The date of birth and date of death date validators in the orbituary forms: as this was my first tryst with dates, as well as validators, i was plesently surprised with the quality of work that turned out. The validators not only took account for present date to ensure no one cauld put a date that was in the furture but further account for leap years and months with 30 or 31 days. the validators even take reference from each other so as not to allow a mallicious user to input a date of death earlier than the date of birth.
2. The database design process and how i created realtionships between tables to keep track of the emojies given by the users as well as a total emojie count per orbituary. Along with that i aimed to keep database memory requirment as small as possible by using boolian and integer vales where ever repetative data is to be input
3. The custom emojis: not only did i envision and design the concept but i managed to get them to work as i had intended. The concept was simple. Each orbituary has 4 emojis. Each user can give each orbituarey an emojie and once an emojie is given a second click on the icon again will take the emojie back. There is a small counter next to the emaojie that shows the number of emojie received per orbituary. When an emojie is given by a user to an orbituary the emojie glows goldern. 
Initaially i had written this code in python but this caused one major problem. Everytime the emojie button was clicked the page would refresh causing the user to lose his place on that paricular page. This was not the user experience that i had intended. so i went back to the drawing board and learnt how to code in Jquery. The process was slow and arduos but eventually i managed to get the emojies to count up or count down along with changing colour without having to refresh the page every time. cheers!!!
4. The individual orbituaries page have a dedicated prayer wall. here users can come and offer them prayres, read other users prayers and give likes/hearst to those prayers. The loop within the loop that casued the code to work the way it does really got my brains twisted for a long long while.

## closing statment 
in the end i would just like to say i am very satisfied with the fruits of my labour. Though the HTML,CSS and responsive design would require a lot more indepth work i feel satisfied with it for now. Im am sure there are many ways to make the code lighter and sleeker as well as the databse more robust. I look forward to lean from all the inputs that are provided to me cause only then will i be able to better my self. 

### Thank you




