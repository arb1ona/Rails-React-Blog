# Creating the Recipe Controller and Model

    Now that you have set up a React frontend for your application, in this step you’ll create a Recipe model and controller. The recipe model will represent the database table that will hold information about the user’s recipes while the controller will receive and handle requests to create, read, update, or delete recipes. When a user requests a recipe, the recipe controller receives this request and passes it to the recipe model, which retrieves the requested data from the database. The model then returns the recipe data as a response to the controller.

1. `rails generate model Recipe name:string ingredients:text instruction:text image:string`
   => `recipe.rb`and `20190407161357_create_recipes.rb`
2. Edit the recipe model `app/models/recipe.rb`

   Add model validation which checks for the presence of a `name`, `ingredients`, and `instruction` field. Without the presence of these three fields, a recipe is invalid and won’t be saved to the database.

3. For Rails to create the recipes table in your database, you have to run a migration, which in Rails is a way to make changes to your database programmatically. To make sure that the migration works with the database you set up, it is necessary to make changes to the `20190407161357_create_recipes.rb` file.

   `NOT NULL` constraint on the `name`, `ingredients`, and `instruction` columns by adding `null: false`, ensuring that these columns have a value before changing the database.

   `rails db:migrate`

4. With your recipe model in place, create your recipes controller and add the logic for creating, reading, and deleting recipes.

   `rails generate controller api/v1/Recipes index create show destroy -j=false -y=false --skip-template-engine --no-helper`

   Running the command also updated the routes file with a route for each action in the Recipes controller. `config/routes.rb`=> `rails routes`

5. 1. To get all recipes, you’ll use ActiveRecord to query the recipes table and fetch all the recipes that exist in the database. `recipes_controller.rb`
6. 2. Add the logic for creating new recipes. As with fetching all recipes, you’ll rely on ActiveRecord to validate and save the provided recipe details. + Read + Delete + private
