# fipkart_webscraping_final

![design and development](https://resize.indiatvnews.com/en/resize/newbucket/715_-/2021/06/flipkart-1624348486.jpg)


## High level Documentaion and Low Level Documentation

### HLD 

The projects main idea was to to showcase the reviews that are put on the Flipkart main website .What is **Flipkart** ? its an Indian online shopping hub that was created
by the brains of *Sachin and Binny Bansal* . 

Flipkarts net worth is $40 billion . It surely is a big giant in India when it comes to online shopping.

Much of the problem was to solve if we can  manage to scrape the website to its core through automation.

The initial idea was to scrape the **Amazon** website but it wasnt possible because Amazon has a load of restriction for scraping their websites. 

if you open the link to Amazon.in/robots.txt you will find that they actually have so much restrection in their website,some of them are ---

    Disallow: */s?k=*&rh=n*p_*p_*p_
    Disallow: /dp/product-availability/
    Disallow: /dp/rate-this-item/
    Disallow: /exec/obidos/account-access-login
    Disallow: /exec/obidos/change-style
    Disallow: /exec/obidos/dt/assoc/handle-buy-box
    Disallow: /exec/obidos/flex-sign-in
    Disallow: /exec/obidos/handle-buy-box
    Disallow: /exec/obidos/refer-a-friend-login
    Disallow: /exec/obidos/subst/associates/join
    Disallow: /exec/obidos/subst/marketplace/sell-your-collection.html
    Disallow: /exec/obidos/subst/marketplace/sell-your-stuff.html
    Disallow: /exec/obidos/subst/partners/friends/access.html
    Disallow: /exec/obidos/tg/cm/member/
    Disallow: /gp/cart
    Disallow: /gp/content-form
    Disallow: /gp/customer-images
    Disallow: /gp/customer-media/upload
    Disallow: /gp/customer-reviews/common/du
    Disallow: /gp/customer-reviews/write-a-review.html
    Disallow: /gp/flex
    Disallow: /gp/gfix
    Disallow: /gp/history
    Disallow: /gp/item-dispatch
    Disallow: /gp/legacy-handle-buy-box.html
    
It was surely a better Idea to skip Amazon given that a single "for loop" can immediately give the site a notice and stop our automation process.
### LLD 

Requirements of the Project -

Python programming language 

Scrapping software include **Selenium and BeautifulSoup4**

A database to store the incoming values from the chromium driver -**MongoDb**

Using a framework for the rendering of web templates -**Flask**

Here is the requirements.txt for the project 


    beautifulsoup4==4.9.1
    brotlipy==0.7.0
    bs4==0.0.1
    chardet==3.0.4
    click==7.1.2
    colorama==0.4.4
    configparser==5.0.2
    crayons==0.4.0
    cycler==0.10.0
    dnspython==1.16.0
    Flask==1.1.2
    Flask-Cors==3.0.9
    gunicorn==20.0.4
    idna==2.10
    itsdangerous==1.1.0
    Jinja2==2.11.2
    kiwisolver==1.3.1
    MarkupSafe==1.1.1
    matplotlib==2.2.3
    numpy==1.19.5
    pandas==1.1.5
    Pillow==8.1.2
    pymongo==3.11.3
    pyparsing==2.4.7
    python-dateutil==2.8.1
    pytz==2021.1
    redis==3.5.3
    requests==2.24.0
    rq==1.7.0
    selenium
    six
    soupsieve==2.0.1
    urllib3==1.25.11
    webdriver-manager==3.3.0
    Werkzeug==1.0.1
    wincertstore==0.2
    
### Table of Contents 

      1 Files
      2 Runnning the project
      3 Use of templating 
      4 DB operations**
      5 deployment
      6 Credits
      7 Adding license


### 1) Files 
  please refer to the code in the **flipkart_webscraping_final**
  
### 2) Running the project 

  Initially we create an app.py file which will be the main file to run our application along with the Flask framework . WE have defined certain classes for each module and we 
  have initailized the modules and classes across the project to so that our code remains in a modular fashion Modularity allows us to refactor our code in the future or cross 
  validation of the code done by the testing team . Along with adding classed we have created a looger file so that we can get the logs and read the logs while debugging the program
  . We have set the logging to the file **logger_class.py** file. Creating a database was necessary because the information withing a loop after scraping can provide a huge set
  of records and it can degrade the programming performance if we initiate a variable and store in it . Mongodb was a good choice because of its lean agility and structure is clearer
  than other Structured Query Languages . We have a module names as **FlipkratScrapping.py** which is the main focus of the project , this module contains all the necessary imports reuired
  for Webscraping . Through the main page we have created a flask app and have rendered some of the templates in the templates files and also created some of the static which contains the csv
  files for taking the classes and ids of the HTML elements inside . 
  
  When we run the app.py file it gives us the required url for localhost which is **http://127.0.0.1:5000/**, the page that is redirected is a webpage which contains 
  a build in form and that form takes the name of the product or the brands name and the background process then work.
  
  but everything is done afer we have made objects of different modules and passed it the root modeule  which is the app.py , some of the logging files may contain the exceptions that is because of 
  the internal errors that are raised during the internal process or it may have been caused by the dynamic loading of the webites or simply put too many requests at the same time .
  
  
  
  
### 3) Use of templating 

  <a href="https://imgbb.com/"><img src="https://i.ibb.co/7R3RZfy/flask.png" alt="flask" border="0"></a>

  The templating in Flask is particularly Jinja templating . Jinja templating allows us to use the blocks of python code and inject it directly to the templates .
  
  Flask is a web Framework that allows us to combne our programming language with front-end part . 
  
  
### 4) Db operations 


  <a href="https://ibb.co/gTMFz5k"><img src="https://i.ibb.co/yynBWwH/kuzt9r42or1fxvlq2-Meta-Generic.png" alt="kuzt9r42or1fxvlq2-Meta-Generic" border="0"></a><br />
  
  
 As I have mentioned that we have chosen Mongo Db because its less complex than MySQl in terms of data handling is sufficiently faster .
 
 The file that we have made is called as the MongoDBOperations and in the file we have created a class called as mongoDBManagement in the class we have made some methods 
 which are **CRUD**.
 
 Along with some basic CRUD operations there are several other to handle the data for the creation of the databases and then to make the DATAFRAMES using **Pandas**,
 it is important to use Pandas library to make the data in the tabluar form to display it in a webpage . Also pandas capture the effeciency of handling and modifying the data 
 with much more verstility 
 
     
    def getResultToDisplayOnBrowser(self, db_name, collection_name):
        """
        This function returns the final result to display on browser.
        """
        try:
            response = self.findAllRecords(db_name=db_name, collection_name=collection_name)
            result = [i for i in response]
            return result
        except Exception as e:
            raise Exception(
                f"(getResultToDisplayOnBrowser) - Something went wrong on getting result from database.\n" + str(e)
                
                
                
                
### 5) Deployment 

<a href="https://ibb.co/m6cMbxJ"><img src="https://i.ibb.co/HnHkBJ7/1-kg8a-AUNx-I055-Oh-Nh-T04sr-Q.png" alt="1-kg8a-AUNx-I055-Oh-Nh-T04sr-Q" border="0"></a><br />

The deployment was done in Heroku, I was hoping to deploy it in **AWS or GCP** but it was costing too much and Heroku seemed the perfect choice because it was free 
and also the steps that are needed to deploy was much simple and error free . The one thing that Heroku has is its instant capablity of creating an application by just 
writing the below lines --

    heroku create
    git remote -v
    heroku git:remote -a thawing-inlet-61413
    git remote rename heroku heroku-staging
    git push heroku main
    git push heroku testbranch:main
  
  
  
### 6) Credits 

  Below are the people who have helped me thrughout the project and also sites that have helped me to make this possible.
  
  websites--
  
  https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/
  https://realpython.com/beautiful-soup-web-scraper-python/
  https://www.dataquest.io/blog/web-scraping-python-using-beautiful-soup/
  https://oxylabs.io/blog/python-web-scraping
  https://www.selenium.dev/
  https://www.opensourceforu.com/2019/04/database-programming-python/
  https://www.computerhope.com/jargon/b/batchfil.htm
  https://docs.fileformat.com/executable/bat/
  https://docs.python-guide.org/writing/structure/
  https://www.w3schools.com/python/python_mongodb_getstarted.asp
  https://pymongo.readthedocs.io/en/stable/tutorial.html
  https://stackoverflow.com/questions/16249736/how-to-import-data-from-mongodb-to-pandas
  https://stackoverflow.com/
  
  I would like to thank my friend Ashutosh and Ravi for helping me out in various places that I was stuck for hours .
  I would also like to thank my friend Shruti for her efforts in managing databases for her expertise in MongoDB .
          Ash.tayal@gmail.com
          RAvvi.Malhotra1996@yahoo.in
          sav_SHRUTI@gmail.com
          
          
### 7) License 


            git/git-scm.com is licensed under the

            MIT License

            Permission is hereby granted, free of charge, to any person obtaining
            a copy of this software and associated documentation files (the
            "Software"), to deal in the Software without restriction, including
            without limitation the rights to use, copy, modify, merge, publish,
            distribute, sublicense, and/or sell copies of the Software, and to
            permit persons to whom the Software is furnished to do so, subject to
            the following conditions:

            The above copyright notice and this permission notice shall be
            included in all copies or substantial portions of the Software.

            THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
            EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
            MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
            NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
            LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
            OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
            WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


  
  
  
  
  

   
  












    
    
















