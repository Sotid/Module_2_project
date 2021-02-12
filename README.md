# ToCookOrNotToCook



## Description

Search platform for recipes based on the ingredients you have in your fridge. You have the possibility to post your own recipes and receive comments and ratings from other users.



## User Stories

- **404** - As a user I want to see a nice 404 page when I go to a page that doesn’t exist so that I know it was my fault

- **500** - As a user I want to see a nice error page when the cooking haters screws it up so that I know that is not my fault

- **homepage** - As a user I want to be able to access the homepage and search, log in and sign up.

- **sign up** - As a user I want to sign up on the web page so that I can add favorite recipes to my list and create my own.

- **login** - As a user I want to be able to log in on the web page so that I can get back to my account

- **logout** - As a user I want to be able to log out from the web page so that I can make sure no one will access my account

- **favorite list** - As a user I want to see the list of my favorite and delete them.

- **my recipes list** - As a user I want to see the list of the recipes I created and be able to delete them.

- **edit user** -  WE'LL SEE. You have facebook for that

- **result** - As a user I want to see the list of recipes filter by my preferences.

  



## Server Routes (Back-end):



| **Method** | **Route**                | **Description**                                              | Request - Bo                                                 |
| ---------- | ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `GET`      | `/`                      | Renders `login` form view.                                   |                                                              |
| `POST`     | /                        | Sends Login form data to the server.                         | { username, password }                                       |
| `GET`      | `/signup`                | Renders `signup` form view.                                  |                                                              |
| `POST`     | `/signup`                | Sends Signup info to the server and creates user in the DB.  | { username, email, password }                                |
| GET        | /recipes[?q=str]         | Renders the main view and search result page                 |                                                              |
|            |                          |                                                              |                                                              |
| GET        | /recipes/:id             | Renders the details of the recipe view                       |                                                              |
| `GET`      | `/private/favorites`     | Private route. Render the `favorites` view.                  |                                                              |
| `POST`     | `/private/favorites/`    | Private route. Adds a new favorite for the current user.     | { recipeId }                                                 |
| `P`OST     | /private/recipes/:id     | Adds new review and renders the same page with updated info. | {comments, rating}                                           |
| GET        | /private/profile         | Private route.Renders to personal profile                    |                                                              |
| `GET`      | `/private/edit-profile`  | Private route. Renders `edit-profile` form view.             |                                                              |
| POST       | /private/edit-profile    | Private route. Send updated data to the server.              | {name, email, password, image}                               |
|            |                          |                                                              |                                                              |
|            |                          |                                                              |                                                              |
| POST       | `/private/favorites/:id` | Private route. Deletes the existing favorite from the current user. |                                                              |
| GET        | /private/myrecipes       | Private route.Renders my recipes view.                       |                                                              |
| GET        | `/private/myrecipes/`add | Private route. The current user can add a new recipe.        |                                                              |
| `POST`     | /private/myrecipes/add   | Private route. Sends the data and renders  updated view.     | {name, ingredients { quantity,   name,  type  },  instructions,  imageURL} |
| POST       | /private/myrecipes/:id   | Private route.Deletes the recipe from the users profile.     |                                                              |
| GET        | /logout                  | Logout out user and redirect login view.                     |                                                              |
|            |                          |                                                              |                                                              |

## Models

User model

```
{
  _id: ObjectId
  username: String,
  email: String,
  password: String,
  image: String,
  favorites: [_id: ObjectId],
  myRecipes: [_id: ObjectId]
}
   
```

Recipe model

```
{
  _id: ObjectId  
   name: String,
   ingredients: [{
   		quantity: Number,
   		name: String,
   		type: String
  }],
  instructions:[String],
  imageURL: String, (default or require)
  reviews: [{
 		 comments: String,
 		 rating: Number
}]
}
```





## Backlog

- Rating

- In recipe ID page: name / pic of the creator that links to the other recipes created by that person
- Limit to one review per user
- Require all the fields for the creation of the recipe
- Inspire me button
- Cocktails



## Links

### Git

Github repository :https://github.com/Sotid/Module_2_project

Deployment: 

### Slides

The url to your presentation slides

### Trello

Link to Trello: https://trello.com/b/ougB7Pdg/2nd-project

