## Q1: Describe the architecture of a typical Flask application

Flask is a web application framework that gives developers the ability to assign their application to a flask object and allows you to associate your routes to view functions. <sup>(1)</sup>

The start of a Flask framework will see you importing flask from Flask (using pip install flask on a terminal or virtual environment), then importing flask from flask in your app.py file [This is what Flask will recognize as your application]. 

Next you'll assign your application by creating a flask object (example below), then you're able to create the association between the function and route by using the app.route decorator. A very simple example for the index page would look like below:


```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return "This is the index of your app"

```

The function can then be viewed (by default) on your web browser at http://localhost:5000, then including the route specified (e.g. /login).

At the end of your flask application the following code will let you run flask by running the ```python app.py``` command. You can expand on this by turning debugging = True to allow you work with changes in code in real time without restarting the server.


```python
if __name__ == "__main__":
    app.debug = True
    app.run()
```

Flask also allows for Dynamic routes, which shown below allows for input such as strings, integers and floats that will return different information depending on the value. For example if it were an integer based on age, you would be able to allow access to only people who were of a certain age based off dynamic routing like below. 

```py
@app.route('/site/<int:Age>')
def allow(Age):
    if Age < 18:
        return f'You have been allowed to enter because you are over {str(Age)} years old.'
    else:
       return f'You are not allowed to enter'
```

----

## Q2: Identify a database management system (DBMS) commonly used in web applications (including Flask) and discuss the pros and cons of this database

SQL is a language for storing and using information in a relational database using rows & columns to represent data & their relationships. SQL gives you the ability to store, update, remove, search & retrieve data from its database. 

PostgreSQL (also called postgres) extends the standard SQL programming language to provide better architecture, reliability, data integrity, robust features & extensibility. <sup>(2)</sup>
This provides great customization for making databases to cater to the exact needs of the developer/users. PostgreSQL can be accessed via python by using a connector library such as Psycopg2, allowing python scripts to perform UPDATES, INSERTS, DELETE etc. When combined with flask this gives the ability for users to perform these actions from the website. 

PostgreSQL is very well regarded due to its long-standing history of being a powerful & open-source with >35 years of development, is almost completely SQL compliant (with exceptions being intentional for better architectural decisions), processes complex datatypes (and highly expandable), has great language support (for example, python with flask -- supports JSON) and is cross-platform. The disadvantages are that most supporting documentation is available only in English and it has a low reading speed compared to other database management systems. 

These disadvantages do not keep it from being one of the most popular DBMS's availability as the power & flexibility of PostgreSQL is incredibly useful to developers. 

----
## Q3: Discuss the implementation of Agile project management methodology

An Agile workflow describes an approach to software development that allows for quick (read: agile) responses to changes in project scope, objective and requirements. Instead of having distinct sequential projects and phases Agile prefers work cycles that include customers, testers and evaluation/feedback at every phase.

Another benefit agile workflow gives is allowing the entire team to contribute all the way throughout the cycle instead of distinct from eachother giving flexibility, insight and understanding to the entire team, while also preventing "blockages" along the way causing the project to be held up in one 'stage' before proceeding to the next. Each person is able to do their work simultaneously. 

To implement an agile workflow you can follow the 6 steps no matter which methodology you wish to follow. Keep in mind the wording can change from user to user, but the ideas are similar.  

### **1. Ideation:**

The team should conceptualize the project, determine the product features needing to be developed and realize the minimum viable product. Tools such as user stories can be of assistance in this stage. This should output a business scope and product backlog.

### **2. Planning:**

Here sprint teams should be created & assigned tasks, with goals, timeframes and resources allocated. User stories can also be completed in this stage. 

### **3. Iteration:**

Sprint teams work on their first iteration of the project and product backlog is addressed. If it's not the first iteration, then customer / stakeholder feedback is taken into account in another sprint. 

### **4. Release:**

The current iteration is released to the customer, customer feedback can be obtained and the cycle is repeated until the final iteration is delivered meeting all stakeholder & customer requirements/expectations. 

### **5. Production:**

After all testing & documentation is complete, the product is now in the production phase. The Agile team oversees the successful launch and provides support where needed for its release. 


### **6. Retirement:**

The completion of the agile process is a successful product given to the customer. The Agile team then moves on to the next project/project development cycle. 


Within the umbrella Agile framework there are multiple approaches in methodology. The most common are: Scrum, Kanban, Extreme Programming (XP), Lean Development and Crystal. Scrum and Kanban used widely, and feature different approaches to the same framework, where scrum is usually more structures with regular sprints and a focus on learning loops to gain feedback and knowledge. Kanabn focuses on visualization of the work, usually through a Kanban board that focus on breakdowns of the project (usually in user stories) and focus on continuous improvement.

----

## Q4: Provide an overview and description of a standard source control workflow

Git has multiple workflow templates available for everyone to use or take inspiration from when creating their source control workflow; for example "Centralized workflow". It uses a central repository with a "main" branch where all changes are committed to.

To use a centralized workflow developers clone the repositories, then edit and commit locally. These changes remain independent from the origin until the developer is ready to "push" the commits to the main branch. This is fine on it's own if only one person is working on the code at a time, however that usually isn't the case, which is where managing conflicts becomes important.

If your local commits do not match the central repository (i.e. there has been another commit since you cloned the repository) then Git will refuse to push your changes which will overwrite the central commits. You can however fetch these commits and add your changes along with the other changes merging your changes onto the online stream. This can be done with ```git pull --rebase origin main```.

Git will transfer the local commits individually allowing you to resolve conflicts at every stage and create a 'cleaner' and easier history to navigate. If possible, it's best to have people working on seperate sections of code as this will prevent rebasing from generating conflicts. If there is, the individual needs to resolve the conflicts to finalize the push. 

This control workflow is great for teams of few members as each conflict will take time to resolve, and will esculate with the number of people working on it. There are other workflows designed for teams of larger numbers that reduce the work required, however are usually more complex.<sup>3<sup>
 
----

## Q5: Provide an overview and description of a standard software testing process (e.g. manual testing)

----

Manual testing is as the name implies, done manually by a person rather than automatically running coded tests. This can be done by a dev or tester to verify features are working as intended in both a closed environment, and working between features that need to communicate. 

A process can be laid out with a description of every step the user needs to take, the status of that function and expected vs actual result. The below is a manual test I made in a terminal application that took one lot of data, and ran it through various other functions to manipulate it.

This was more effective than automatic tests to implement as my main concern was data integrity between functions and that none of the functions caused errors between uses, so by manually testing each of these functions and verifying it was working as intended manual testing is able to verify the functions are working as intended and potentialy identify what functions would not be working or passing the data correctly if new functions were added. 

This same reasoning can be applied to many projects where data needs to be manipulated in various forms depending on the current need. As each function is designed, its interaction with other functions can be monitored in ways that are more complicated to write automatic tests for. 

![](./resources/testing.jpg)

## Q6: Discuss and analyse requirements related to information system security and how they relate to the project

----

ACME's database and website will will likely have sensitive information that should only be distributed to selected users, making this project in need of data protection & user authentication and assigning permission. 
In a Flask application, JWT is a simple and effective security module to provide API authentication. 

JWT authentication works by taking the user entered username and password and comparing it to the User table for a match. Once a match is found, it generates and returns a JSON web Token (A long alphanumeric token) and gives the front end a 200 success status, which the front-end will use for future requests. In future requests include an authorization header, and the API validates that token for further requests (if that token is valid). Once JWT is set up on the Flask server, getting authorization for any function is as simple as using the @jwt_required() decorator. 

JWT Tokens are bigger than both Basic tokens, which are the shortest and therefore easier to hack (less combinations), and Bearer Tokens. Another benefit over bearer tokens is they also don't need to be stored in a database, and therefore reduce the memory and steps required -- all the information needed from the token are found in the token instead, which is separated into its header containing the encryption algorithm, the payload which identifies the user and the signature which is generated by the other sections. 

----

Flask-security (installed with ```pip install flask-security-too```) which installs a number of dependencies focused on security mechanisms for a Flask app. 


Flask-Login provides session-management for logging in & out and "remember me" functions for user sessions in whatever form you want -- however it is restricted to only usernames & passwords. It does this with an "alternative token" based off a randomly generated id linked to the users primary id, making the old session invalid when a new id is generated. 

It also provides Access-control by assigning permissions to specific roles (e.g. administrator, editor), which can then be assigned to users. These permissions are made into strings giving complete control to the developer to how they're assigned.     

Passwords from users must meet secure requirements that can be defined by the developers, checking parameters such as password-length, if the password has been in a security breach (or an amount of breaches it is allowed to have been in), assess the complexity of the password, how long it would take to 'crack', and provide feedback to improve to improve it. The password is then protected with hashing algorithms which can be decided by the developer, or defaulted to bcrypt. 

Authentication toakens are generated via username & password and can be used to authenticate throughout the website, and can be customized with extra layers of protection depending on the devs needs -- for example by making them csrf tokens, or by changing when they expire, or the conditions that trigger the expiration. Flask-security provides many other common problem-solving methods; Two-factor authentication, email confirmation & password recovery.

----

Overall, Flask-security provides many customizable options for the developers to create a secure Flask application the way that they want, however some of the packages are no longer kept up to date and for pure authentication JWT is much easier to set up, but has less customization. 

----

## Q7: Discuss common methods of protecting information and data and how you would apply them to the project

I am familiar with using JWT-extended as mentioned above to provide authentication and protect information. By setting up the secret key, the endpoint (POST) for creating tokens you can use the jwt_required() decorator to prevent access to unauthorized users.  

Other practices I am familiar with are implementing CSRF protection from flask_wtf. This along with other best-practices (properly using GET requests for retrieving data, POST for changing information) and mandating CSRF tokens will protect the site from a CSRF attack. 

Flask-security also provides a lot of options to use (like flask_wtf above) that I have read about and would appreciate learning to use these in practice to add security to this project. 


----

## Q8: Research what your legal obligations are in relation to handling user data and how they can be met for the project

----

## Q9: Describe the structural aspects of the relational database model. Your description should include information about the structure in which data is stored and how relations are represented in that structure.

----

## Q10: Describe the integrity aspects of the relational database model. Your description should include information about the types of data integrity and how they can be enforced in a relational database.

----

## Q11: Describe the manipulative aspects of the relational database model. Your description should include information about the ways in which data is manipulated (added, removed, changed, and retrieved) in a relational database.

----

## Q12: Conduct research into a web application (app) and answer the following parts:
  a. List and describe the software used by the app.
  b. Describe the hardware used to host the app.
  c. Describe the interaction of technologies within the app
  d. Describe the way data is structured within the app
  e. Identify entities which must be tracked by the app
  f. Identify the relationships and associations between the entities you have identified in part (e)
  g. Design a schema using an Entity Relationship Diagram (ERD) appropriate for the database of this website (assuming a relational database model)

----


----

# References

(1) https://realpython.com/python-web-applications-with-flask-part-i/#what-we-are-building <br>
(2) https://www.postgresql.org/about/ <br>
(3) https://www.atlassian.com/git/tutorials/comparing-workflows <br>
(4) https://flask-security-too.readthedocs.io/en/stable/ <br>
(5) https://jwt.io/introduction