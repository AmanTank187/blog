# Blog

Intro:

---

## Focus

- Back-end: Database associations, one to many, many to many.
- Front-end: Using bootstrap to make a good looking website.

## Approach

- Ensuring the fundamentals are done correctly
- Write the program from scratch and not rely on ruby magic / generators in order to get a good understanding of how rails work.

---

## Learnings

---

# Rails Console

- Can type 'rails c' to use the console and test assumptions between model and model table. You can do model_name.all to get all data from the table, you can also you model_name.create to add data to the table by the console.

- A more preferred to add data is by assigning a variable to the article model. "article = Article.new" . This then creates an object which has attributes of title and description, You can then assign title and other attributes like this: article.title = "My article title". This will not be inserted into the database on assignment so you will have to do article.save.

- A one liner: article = Article.new(title: "third article", description: "third description") which is followed by article.save

- Can find article by ID by using article = Article.find(2). Can also use article.first/last

- Can use .destroy to delete from the table. It also hits the database straight away without .save method.

- Clear way to see routes, rails routes --expanded

- byebug can be used to pause the application and show what part of the code it is at, use 'continue' to carry on.

# Model

- Adding a model to add validations so extra and uneeded information cannot be add to the database/table (Checkout active record validations, good resource)

# Form helpers

-

---

- Ruby version

- System dependencies

- Configuration

- Database creation

- Database initialization

- How to run the test suite

- Deployment instructions
