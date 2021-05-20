# Viewing Recipes

    Creating a page to view all recipes and individual recipe. However, before you can do this, you need recipes to work with, since your database is currently empty. Rails affords us the opportunity to create seed data for your application.

1. Open up the seed file `seeds.rb`
   In this code, you are using a loop to instruct Rails to create nine recipes with a `name`, `ingredients`, and `instruction`.

2. The component to view all recipes will make a HTTP request to the index action in the RecipesController to get a list of all recipes. These recipes will then be displayed in cards on the page.

   Create a `Recipes.jsx` file in the `app/javascript/components` directory:

3. The next step is to create a route for it to display all the recipes,. Open the front-end route file located at `app/javascript/routes/Index.jsx`

4. Create a second component to view individual recipes. Create a `Recipe.jsx` file in the `app/javascript/components` directory

5. To view the Recipe component on a page, add it to your routes file. Open your route file to edit: `app/javascript/routes/Index.jsx`
