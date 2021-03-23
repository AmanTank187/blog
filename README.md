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

- A more preferred to add data is by assigning a variable to the article model. `article = Article.new` . This then creates an object which has attributes of title and description, You can then assign title and other attributes like this: `article.title = "My article title"`. This will not be inserted into the database on assignment so you will have to do article.save.

- A one liner: `article = Article.new(title: "third article", description: "third description")` which is followed by article.save

- Can find article by ID by using `article = Article.find(2)`. Can also use `article.first` or `article.last`

- Can use .destroy to delete from the table. It also hits the database straight away without .save method.

- Clear way to see routes, rails routes --expanded

- byebug can be used to pause the application and show what part of the code it is at, use 'continue' to carry on.

# Model

# Article Model

- Adding a model to add validations so extra and uneeded information cannot be add to the database/table (Checkout active record validations, good resource)

- Show method is used to find one row from the database. example: `Article.find(params[:id])`

- An index method is used to get all data from table, example: `Article.all`

- The new method has nothing in there as it doesn't need to perform a action, just a get request to get the form on the screen and intialise the article with nothing in there. Once the form is filled it out in then follows a post request and peforms the creatr action.

- Create method can be used to make a new article on a website. This can be done with `Article.new`. Usually you have to provide params but rails allows an article key to be used which is from the params hash and since we have an article model, rails can save them in the correct places within the table. As a secruity feature you have to use strong params like this `@article = Article.new(params.require(:article).permit(:title, :description))` This line is saying to allow an article key and permit a title and description from there to be used to create the object.When you have created the object, you will need to save the object. In this case you will need to do `@article.save` and then redirect it the show path by doing `redirect_to @article`

- The edit method: This is similar to the show method, it finds the article using the ID. This is then taken the view which is edit.html.erb. Here we used `form_with(model: @article, local: true)` Which makes the form submit to the update route and automatically fills in the form with the existing data from the article you want to edit.

- Update method: You find the article you want to edit using the ID, you then do `article.update(params.require(:article).permit(:title, :description))` with the edited fields. In addition to this i added a IF statement to show a flash message and redirect the user if the updated is sucessful. If the update is not sucessful it will redirect you back to the edit page.

# Flash Messages

- Creating a flash message in order to show user if they have ran into errors whilst creating an article and creating a flash message to show they have created a article successfully.

# Extra learnings

- form_with helpers are very useful. Research them!

---

- Ruby version

- System dependencies

- Configuration

- Database creation

- Database initialization

- How to run the test suite

- Deployment instructions
