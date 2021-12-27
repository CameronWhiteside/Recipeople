# Recipeople

<a href="https://recipeople.herokuapp.com/">Live Site</a>  |  <a href="https://github.com/MeiMeiYS/group-9-best-group/wiki"> Project Wiki</a> | <a href="https://github.com/MeiMeiYS/group-9-best-group/issue">Report Bug</a>

Recipeople is a website where users can sign up, post recipes, and curate collections of recipes published by other users. This website was designed as a Week 13 midterm project as part of App Academy's 24-week Full Stack Software Engineering Bootcamp.

## Technologies Used
[Javascript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)  | [Node.js](https://nodejs.org/en/)  | [Express](https://expressjs.com/)   |   [Pug](https://pugjs.org/api/getting-started.html) |   [Sequelize](sequelize.org)   |  [PostgreSQL](https://www.postgresql.org/)   |  [Bcrypt.js](https://www.npmjs.com/package/bcryptjs)

## Launching Locally

### Prerequisites
 - [Node.js 16.13.1](https://nodejs.org/en/)

### Getting Started

1. Clone the project repository
```
   git clone https://github.com/andrewscohen/2020.11.badReads.git
```
2. Install dependencies
```
    npm install
```

3.  Create a local .env file modeled after the .env.example file in the root directory
```
   PORT=8080
   DB_USERNAME=recipeople_admin
   DB_PASSWORD=your_unique_password
   DB_DATABASE=recipeople
   DB_HOST=localhost
   SESSION_SECRET=your_session_secret
```
4. Migrate and seed the database
 ```
   npx sequelize-cli db:create
   npx sequelize-cli db:migrate
   npx sequelize-cli db:seed:all
```

5. Run the project with a starting script
 ```
    npm start
 ```

## Recipeople In Action
Full user stories for the initial development phase are available on the [User Stories](https://github.com/MeiMeiYS/group-9-best-group/wiki/User-Stories) section of the project wiki. A feature list for the initial development phase is available on the MVP Feature List section of the project wiki.

### User Registration and Authentication
New users can register for an account by entering a unique email address, a username, and a secure password.

<div align="center">
<br/>
<img src="https://i.ibb.co/7ybwmS4/sample123-register.gif" alt="Explore Recent Recipes" height="300" align="center"/>
<br/>
<br/>
</div>


Existing users can log in to their account by submitting their credentials via the login form.

<div align="center">
<br/>
<img src="https://i.ibb.co/mN1vsht/sample123-login.gif" alt="Explore Recent Recipes" height="300" align="center"/>
<br/>
<br/>
</div>

Users may log out of their account by clicking the **LOGOUT** button on the sitewide header.

<div align="center">
<br/>
<img src="https://i.ibb.co/3fCRrM2/Logout-Click.gif" alt="Logout" height="300" align="center"/>
<br/>
<br/>
</div>

### Creating and Modifying A Recipe

Logged-in users can create a new recipe with a name, description, an optional image, a list of ingredients, and cooking instructions.

<div align="center">
<br/>
<img src="https://i.ibb.co/4YVPbqF/Create-Recipe.gif" alt="Add A Recipe" height="450" align="center"/>
<br/>
<br/>
</div>

When a new recipe is added, a new page is created for the recipe. All users can view the recipe information. Logged in users can add a review, add the recipe to a collection, or add a status. Recipe owners can edit or delete their own recipes.

<div align="center">
<br/>
<img src="https://i.ibb.co/yfb6Ht8/Edit-Hover.gif" alt="Add A Recipe" height="450" align="center"/>
<br/>
<br/>
</div>

When modifying a recipe, an "Edit" form will populate with the recipe's current information. A user may add, edit, or delete ingredients, and can edit the name, description, image, and instructions. If a user would like to delete the recipe, or discard their changes, they may do so from the edit form.

<div align="center">
<br/>
<img src="https://i.ibb.co/pr7Qry0/Edit-Recipe.gif" alt="Add A Recipe" height="450" align="center"/>
<br/>
<br/>
</div>

### Creating and Modifying A Collection

Users can create personalized collections in order to organize groups of curated recipes.

Users can add and remove recipes from their collections.

Users can edit and delete their collections.

### Creating and Modifying A Review

Users can add a rating, an image, and a public review on any recipes, and view the reviews that others have posted.


Users can modify and delete their reviews.


A recipe's average rating is visible on the Homepage, the Recipes page, and each recipe's detail page as indicated by a scale ranging from 1 to 5 whisks.

Users can edit and delete their collections.

### Assigning A Recipe Status
A user can create, view, update, and remove a personalized status on any recipe in to indicating whether they "Will Cook" the recipe in the future, or whether they already "Cooked" the recipe.

After assigning a status to a recipe, the user can view the recipe on the Status section of their user page.

### Search For Recipes
The most recent publicly-visible recipes are visible both on the site Homepage and the Recipes page.

<div align="center">
<br/>
<img src="https://i.ibb.co/RgCdkP7/Explore-Recent-Recipes.gif" alt="Explore Recent Recipes" height="300" align="center" />
<br/>
<br/>
</div>

The Recipes page also includes a case-insensitive search where users can search for any recipe by a case-insensitive substring of the recipe title.

<div align="center">
<br/>
<img src="https://i.ibb.co/GHdVMJJ/Search-Functionality.gif" alt="Explore Recent Recipes" height="300" align="center"/>
<br/>
<br/>
</div>

## Technical Implementation
### Database Design
The full database schema is available to view as a [linked chart on dbdiagram.io](https://dbdiagram.io/d/61afe26a8c901501c0e5914b), or as a [list of tables on the Database Schema page](https://github.com/MeiMeiYS/group-9-best-group/wiki/Database-Schema) of the wiki.

![Full Database Schema](https://i.ibb.co/4S9bs3p/Recipeople.png)

Some tables, such as Roles are reserved for such as creation of an Administrator frontend, where certain users can have access to edit and delete content posted by other users. The Tags table is reserved for creation of recipe tags that a recipe creator can assign to their recipes, or for other users to include in search criteria. Tag categories are intended for the future development of tag grouping, such a *Cuisine* tag category that may have tags such as *Japanese*, *French*, or *Mediterranean*, which can useful to organize tags as the number and diversity of recipes continues to grow.

### Frontend Routes
All frontend routes are covered in detail on the [Fronted Routes section of our project wiki](https://github.com/MeiMeiYS/group-9-best-group/wiki/Frontend-Routes). Frontend routes were designed to enable users access to basic functionality such as registration, authentication, viewing groups of recipes, accessing recipe details, and viewing profile page where users can manage their personal collections.

### API Routes
All frontend routes are covered in detail on the [API Routes section of our project wiki](https://github.com/MeiMeiYS/group-9-best-group/wiki/Frontend-Routes). API routes were designed for users to interact with a page without being redirected.

### Developmental Challenges
#### Considering Sitewide


## Future Development
As we further develop our programming skills, we will continue to improve the maintainability and user experience of Recipeople.

### Improved User Experience
#### Recipe Reviews and Recipe Status CRUD from Badge View

 - Recipe badges are visible on many parts of the website, including the
   Homepage, the Recipe page, and User pages. However, these badges
   contain limited information, and users must click to navigate to the
   Recipe Detail page in order to add it to a collection, change its
   status, or add a review. In the future, the recipe badges will be
   re-designed to allow users more functionality without requiring an
   additional click to the Recipe Detail page.

#### Sitewide Responsiveness

 - The website is currently functional on all screen sizes, but is
   styled for screens greater than 900 px in width. New smaller-scale
   layouts will be implemented so that the user experience on mobile or
   tablet devices is comparable to the desktop user experience.

### Improved Maintainability

#### Administrator Interface

 - In order for an site administrator to moderate content on the
   website, all modifications must be done via SQL queries to a
   centralized database. To mitigate this, a new *administrator* role
   will be added that will enable that user to edit or delete any recipe
   or review posted on the website.

#### Normalization of Ingredient Names

 - Currently, all ingredients are stored as rows on a database. If a
   user types in a new ingredient for a recipe that is not already in
   the database, a new ingredient is created. However, the addition of
   new ingredients does not currently account for spelling or
   capitalization variations. For example, Tomato, tomatoes, and tomato
   would all be stored in the database as separate ingredients. In order
   to support future functionality, ingredient names may undergo a
   pattern-matching normalization process or third-party food-name API
   validation to prevent duplicate entries within our database.

### New Features

#### Detailed Recipe Features

 - Currently, the description and instructions for each ingredient are
   stored as strings. Adding additional fields such as serving size,
   cook time, cook temperature, and individual recipe steps can
   compartmentalize information for users, and allow for improved search
   functionality.

#### Implementation of Recipe Tags

 - The database is already configured to support the addition of "Tags"
   for each recipe. A user will be able to add, view, edit, and delete
   tags from recipes that they have submitted, and a user can use tags
   as search criteria to find new recipes. Once an admin role is
   implemented, an admin will be able to add, edit and delete tags.

#### Shopping Lists

 - Users will be able to generate a shopping list from a collection that
   aggregates the ingredients from all recipes and combines them into an
   organized list. Normalization of Ingredient Names must be completed
   before implementation of this feature.
