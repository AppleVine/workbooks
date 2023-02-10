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



## Q2: Identify a database management system (DBMS) commonly used in web applications (including Flask) and discuss the pros and cons of this database

SQL is a language for storing and using information in a relational database using rows & columns to represent data & their relationships. SQL gives you the ability to store, update, remove, search & retrieve data from its database. 

PostgreSQL (also called postgres) extends the standard SQL programming language to provide better architecture, reliability, data integrity, robust features & extensibility. <sup>(2)</sup>
This provides great customization for making databases to cater to the exact needs of the developer/users. PostgreSQL can be accessed via python by using a connector library such as Psycopg2, allowing python scripts to perform UPDATES, INSERTS, DELETE etc. When combined with flask this gives the ability for users to perform these actions from the website. 

PostgreSQL is very well regarded due to its long-standing history of being a powerful & open-source with >35 years of development, is almost completely SQL compliant (with exceptions being intentional for better architectural decisions), processes complex datatypes (and highly expandable), has great language support (for example, python with flask -- supports JSON) and is cross-platform. The disadvantages are that most supporting documentation is available only in English and it has a low reading speed compared to other database management systems. 

These disadvantages do not keep it from being one of the most popular DBMS's availability as the power & flexibility of PostgreSQL is incredibly useful to developers. 

## Q3: Discuss the implementation of Agile project management methodology

An Agile workflow describes an approach to software development that allows for quick (read: agile) responses to changes in project scope, objective and requirements. Instead of having distinct sequential projects and phases Agile prefers work cycles that include customers, testers and evaluation/feedback at every phase.

Another benefit agile workflow gives is allowing the entire team to contribute all the way throughout the cycle instead of distinct from eachother giving flexibility, insight and understanding to the entire team, while also preventing "blockages" along the way causing the project to be held up in one 'stage' before proceeding to the next. Each person is able to do their work simultaneously. 

To implement an agile workflow you can follow the 6 steps no matter which methodology you wish to follow. Keep in mind the wording can change from user to user, but the ideas are similar.  

----

### **1. Ideation:**

The team should conceptualize the project, determine the product features needing to be developed and realize the minimum viable product. Tools such as user stories can be of assistance in this stage. This should output a business scope and product backlog.

----

### **2. Planning:**

Here sprint teams should be created & assigned tasks, with goals, timeframes and resources allocated. User stories can also be completed in this stage. 

----

### **3. Iteration:**

Sprint teams work on their first iteration of the project and product backlog is addressed. If it's not the first iteration, then customer / stakeholder feedback is taken into account in another sprint. 

----

### **4. Release:**

The current iteration is released to the customer, customer feedback can be obtained and the cycle is repeated until the final iteration is delivered meeting all stakeholder & customer requirements/expectations. 

----

### **5. Production:**

After all testing & documentation is complete, the product is now in the production phase. The Agile team oversees the successful launch and provides support where needed for its release. 

----

### **6. Retirement:**

The completion of the agile process is a successful product given to the customer. The Agile team then moves on to the next project/project development cycle. 

----

Within the umbrella Agile framework there are multiple approaches in methodology. The most common are: Scrum, Kanban, Extreme Programming (XP), Lean Development and Crystal. Scrum and Kanban used widely, and feature different approaches to the same framework, where scrum is usually more structures with regular sprints and a focus on learning loops to gain feedback and knowledge. Kanabn focuses on visualization of the work, usually through a Kanban board that focus on breakdowns of the project (usually in user stories) and focus on continuous improvement.

### Q4: Provide an overview and description of a standard source control workflow


### Q5: Provide an overview and description of a standard software testing process (e.g. manual testing)


### Q6: Discuss and analyse requirements related to information system security and how they relate to the project


### Q7: Discuss common methods of protecting information and data and how you would apply them to the project


### Q8: Research what your legal obligations are in relation to handling user data and how they can be met for the project


### Q9: Describe the structural aspects of the relational database model. Your description should include information about the structure in which data is stored and how relations are represented in that structure.


### Q10: Describe the integrity aspects of the relational database model. Your description should include information about the types of data integrity and how they can be enforced in a relational database.


### Q11: Describe the manipulative aspects of the relational database model. Your description should include information about the ways in which data is manipulated (added, removed, changed, and retrieved) in a relational database.


### Q12: Conduct research into a web application (app) and answer the following parts:
  a. List and describe the software used by the app.
  b. Describe the hardware used to host the app.
  c. Describe the interaction of technologies within the app
  d. Describe the way data is structured within the app
  e. Identify entities which must be tracked by the app
  f. Identify the relationships and associations between the entities you have identified in part (e)
  g. Design a schema using an Entity Relationship Diagram (ERD) appropriate for the database of this website (assuming a relational database model)




----

# References

(1) https://realpython.com/python-web-applications-with-flask-part-i/#what-we-are-building <br>
(2) https://www.postgresql.org/about/