# Project Name

<br>



## Description

Project Module 2 is an online database of information related to video games content online – including, ratings, and fan and critical reviews.


<br>

## User Stories

- **404** - As a user I want to see a nice 404 page when I go to a page that doesn’t exist so that I know it was my fault
- **500** - As a user I want to see a nice error page when the super team screws it up so that I know that is not my fault
- **homepage** - As a user I want to be able to access the homepage and filter by type of restaurant, log in and sign up. 
- **sign up** - As a user I want to sign up on the web page so that I can add favorite restaurants to my list.
- **login** - As a user I want to be able to log in on the web page so that I can get back to my account
- **logout** - As a user I want to be able to log out from the web page so that I can make sure no one will access my account
- **favorite list** - As a user I want to see the list of my favorite and delete them.
- **edit user** - As a user I want to be able to edit my profile.
- **result** - As a user I want to see the list of restaurant filter by my preferences.
- **restaurant listing** - As a user I want to see more details of the restaurant, be able to call them and visit their website and save it as favorites.



<br>



## Server Routes (Back-end):



| **Method** | **Route**                          | **Description**                                              | Request  - Body                                          |
| ---------- | ---------------------------------- | ------------------------------------------------------------ | -------------------------------------------------------- |
| `GET`      | `/`                                | Main page route.  Renders home `index` view.                 |                                                          |
| `GET`      | `/login`                           | Renders `login` form view.                                   |                                                          |
| `POST`     | `/login`                           | Sends Login form data to the server.                         | { email, password }                                      |
| `GET`      | `/signup`                          | Renders `signup` form view.                                  |                                                          |
| `POST`     | `/signup`                          | Sends Sign Up info to the server and creates user in the DB. | {  email, password  }                                    |
| `GET`      | `/private/edit-profile`            | Private route. Renders `edit-profile` form view.             |                                                          |
| `PUT`      | `/private/edit-profile`            | Private route. Sends edit-profile info to server and updates user in DB. | { email, password, [firstName], [lastName], [imageUrl] } |
| `GET`      | `/private/favorites`               | Private route. Render the `favorites` view.                  |                                                          |
| `POST`     | `/private/favorites/`              | Private route. Adds a new favorite for the current user.     | { name, cuisine, city, }                                 |
| `DELETE`   | `/private/favorites/:restaurantId` | Private route. Deletes the existing favorite from the current user. |                                                          |
| `GET`      | `/restaurants`                     | Renders `restaurant-list` view.                              |                                                          |
| `GET`      | `/restaurants/details/:id`         | Renders `restaurant-details` view for the particular restaurant. |                                                          |







## Models

User

```javascript
{
  name: { type: String, require, unique},
  email: {type: String, requiere},
  password: {String, requiere},
  ID: Object_ID,
  image: String,
  Description: {type: String, maxlength: 280},
  Rol: {type: String},
  Gamelist:{Object_ID [] },
  Wishlist: {Object_ID [] },
  Social: {
  facebook: String,
  twitter: String,
  Steam: String
  },
  Genres:[],
  Location: String
}

```



Review

```javascript
{
  _id: Object_ID,
  User: { type: Schema.Types.ObjectId, ref:'User' },
  Game: {type: Schema.Types.ObjectId, ref: 'Game'},
  Comment: String,
  Timestamp: Date,
  Upvote: Number,
  Downvote: Number
}

```


Game

```javascript
{
  _id: Object_ID,
  Name: String,
  Released: String,
  Image: String,
  Metacritic: number,
  Genres: [],
  Api_id: String,
  Screenshoots: [''],
  Upvote: Number,
  Downvote: Number,
  GameSaved: Number
}

```




<br>



## Backlog

[See the Trello board.](https://trello.com/b/sdPDPIGx/module2-project)



<br>



## Links



### Git

The url to your repository and to your deployed project

[Repository Link](https://github.com/BeAvisP/M2-Project)

[Deploy Link]()



<br>



### Slides

The url to your presentation slides

[Slides Link](https://docs.google.com/presentation/d/1P5FIi0vHZBUcgUtmt1M4_lLCO5dwdJ4UOgtJa4ehGfk/edit?usp=sharing)