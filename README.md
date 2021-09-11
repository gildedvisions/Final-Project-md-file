# Light A Candle

#### Video Demo:  https://youtu.be/e3VkVXPAU0U


#### Description:

My project has a very simple premise. To create something that can outlast the duration of the CS50 course. With the COVID-19 pandemic raging around I aimed to create a platform that could enable people to remember and talk about loved one’s lost. It is about enabling people to share and come to terms with grief, and to ensure that the ones they lost did not become a mere statistic.

I belong to India. Currently live and work here, and have seen the country struggle through the second wave of covid. Deaths reported were in the thousands. Many others remained uncounted with stories of bodies in the thousands getting washed up on the banks of our holy rivers. These were the ones the media forgot, with no data even. Could a platform be created that gave a voice, a name to the forgotten? 

As I began working, the basic mission further expanded. In a country of cheap internet adoption why should the story of thousands go missing?
- could we aim to, in some way,  gather actual covid death figures in the country? I decided the best way to gather this information would be via crowd sourcing. Let the people who were survived by the deceased post information about their personal loss. Give people a platform, where they could voice their pain, hopes, memories of little acts of kindness, feelings of helplessness.. whatever..... The platform would give people access to be able to share their story, their experiences, maybe even point to resources and facilities they found useful or the ones that frustrated them.  
- this fundamental idea of trying to create a crowd source of information lead to my second mission. Create an interactive experience where the grieving could come and upload obituaries for their loved ones for friends and family to see. 
      - During the process of uploading an obituary the platform would ask cause of death and in the eventuality the person indicated covid/covid-related causes they would have the option of providing such further information about their experience. This would all be on a purely voluntary basis. 
- Friends and family could register to engage with each other, share condolences, memories. They could also use 4 emotionally sensitive emojis to pay tribute to the deceased. Enabling wide social engagement would itself act as a validation tool for the information uploaded. Once an obituary/post is created the more interaction a post got, chances would be lower that it would be fake.

I created four separate emojis for this 
1) a set of hands offering prayers 
2) a hand offering support, 
3) a dove to show peace in the afterlife 
4) and finally a candle which when lit turned golden 

It was this candle emoji that led me to coin the title of my project **Light A Candle**

A Users would require to register with the application to access it. Once they register they have many options for interacting.
1. The main one being "creating a memory" i.e. post an obituary of a loved one. They could give basic information about the deceased like location, cause of death, date of birth and date of expiry along with mentioning a few words in their memory. 
2. the application then processes this information and displays the post on the home page. The home page is paginated to show a maximum of 8 posts per page and over 10 pages show the latest 80 posts created chronologically. 
3. A side panel on the home page is also created that lists names of those whose death anniversary falls within the current month for people to give remembrance to.
4. Other users can register to interact with each post/obituary that are created by offering them a choice of 4 emojis as a way to offer their condolences. They may also enter the post/obituaries individual page and further offer prayers, condolences and memories to the deceased on the deceased’s personal prayer wall. 
5. A search feature allows users to look up posts/obituaries using any key words such as name, location or obituary text. This can be used to quickly access or find any particular person quickly.

Now how do we address our primary mission of collection Covid related information? If at the time of creating the post the cause of death is entered as "covid or covid related" then the user is directed to a second form where the user can choose to provide insight into about their covid experience. Providing this information would be purely voluntary and in no way affect the outcome of the post created. In a country with poor public health infrastructure (such as India) people could come forward to provide information on the gaps that were most glaring as well as the strengths - availability of beds, oxygen shortage, lack of trained staff, the helping hands, organizations, people etc. however, No covid related information is displayed on the site (this is specified in the form itself), nor is it mandatory to provide any covid information(also specified). The obituary is created irrespective of data provide in the second form



## Light a candle: Project Description 
light a candle in a flask application with an SQLLite3 database backend and a Bootstrap front end, though you would think it is much more. The basic flask modules/libraries that helped to achieve this task are broadly 
- Login Manger: to control user login sessions
- Flask_wtf and wtforms: to simplify the process of form creation and form validations
- Flask_SQLAlchemy: to create and act as a bridge between flask and SQLlite. To tackle SQL injection attacks. In the future it may also assist is upscaling the project to a larger database application if so required
- Flask_mail: to send out validation tokens via emails for new users registering with the site, as well as to complete the forgot password journey
- werkzeug.security: to help with encrypting and checking passwords against the database 
- itsdangerous: to generate time limited tokens for the forgot password route
- flask_migrate: to make edits to the database schema after its initial creation 

## light a candle: package distribution
the flask app is split into an application package. The run.py file has only one job, to start the application with a simple command of python run.py
Inside the candle folder we have a static folder and a templates folder which contain the images/CSS/JS files and the html files respectively, also contained in the candle folder are 
1. __init__.py: housing all the configurations for the application 
2. forms.py: containing all the forms and their respective validations
3. models.py: containing the db model classes 
4. routes.py: containing all the app routes
5. passwordcheck.py: a custom program I wrote that checks whether a password when entered at the time of registration meets all the requirements to make it a strong password and give appropriate feedback if there are any short comings 
6. states.py: a program I wrote to add the names of all the states of the Indian territory and their short forms from a csv into the sqllite database 
7. checkinputdate.py: a program I wrote to help check and validate the dates put in the create a memory form (NewPostform)

## Proud Moments for my project
throughout my project I managed to push my boundaries using programming that I had no earlier experience with, before creating or developing this project. Along the way I also overcame many a hurdles. Among them the few worth mentioning are specified below:
1. The date of birth and date of death date validators in the “create a memory” forms: as this was my first tryst with dates, as well as validators, I was pleasantly surprised with the quality of work I turned out. The validators not only took account for present date to ensure no one could put a date that was in the future but further accounted for leap years and months with 30 or 31 days. The validators even take reference from each other so as not to allow a malicious user to input a date of death the predates the date of birth.
2. The database design process where I created relationships between tables to keep track of the emojis given by the users as well as a total emoji count per obituary. Along with that I aimed to keep database memory requirements as small as possible by using Boolean and integer values where ever repetitive data is to be input
3. The custom emojis: not only did I envision and design the concept but I managed to get them to work as intended. The concept was simple. Each obituary has 4 emojis. Each user can give each obituary an emoji by clicking on the icon. Once an emoji is given a second click on the icon again will take the emoji back. There is a small counter next to the emoji that shows the number of emojis received per obituary per emoji. When an emoji is given by a user to an obituary the emoji glows golden and the count increases by 1. 
Initially I had written this code in python but this had one major drawback. Every time the emoji button was clicked the page would refresh causing the user to lose his place on that particular page. This was not the user experience that I had intended. So I went back to the drawing board and learnt how to code in Jquery. The process was slow and arduous but eventually I managed to get the emojis to count up or count down, keep track of which user had given an emoji to which obituary/post, along with changing colour without having to refresh the page every time. cheers!!!
4. The individual obituaries page have a dedicated prayer wall. Here users can come and offer prayers to the deceased, read other users prayers and give likes/hearts to those prayers. The loop within the loop that executes the code to work the way it does really got my brains twisted for a long long while.

## closing statement 
In the end I would just like to say I am very satisfied with the fruits of my labour. Though the HTML, CSS and responsive design would require a lot more in-depth work I feel satisfied with it for now. I am sure there are many ways to make the code lighter and sleeker as well as the database more robust. I look forward to lean from all the inputs that are provided as only then will I be able to better myself. 

### Thank you




