# Project description
The task is to make a virtual record shelf where you can add albums. The UI should be responsive design and work with different screen sizes. You don't need to support legacy browsers, so UI needs to work only on modern desktop and mobile browsers. There is no need to implement any authentication and multiple users.

We also integrate the record shelf to the Last.fm API to get more info about each album. This includes:
* Album cover picture
* Track listing
* Track numbering
* Track length

Last.fm is used with personal API key, so consider how to store this key. 

https://www.last.fm/api

There are few libraries for the Last.fm you can use. You can use any HTTP client like Axios and implement the API calls you need.

For Node.js environment there is available https://www.npmjs.com/package/last-fm

## Mockdata for the project
The project's mock data is in [mockdata.js](mockdata.js) file in the project root directory. Please use this data when the application starts. UUID V4 is to be used as universally unique identifiers for id's.

### Artist
```
{
  id: "984ee0e0-1f01-4855-853a-ebc3a372653d", 
  name: "John Frusciante"
}
```

### Album
```
{
  id: "69fcea1a-d21b-4734-baa6-0285c44875fb",
  artistId: "984ee0e0-1f01-4855-853a-ebc3a372653d",
  name: "Niandra LaDes and Usually Just a T-Shirt"
}
```

## Part 1 - Frontend
Here you are going to make the front-end part for displaying and adding data to the virtual record shelf. For the initial state, you will use the mock data provided in this repository. You are not required to save the state permanently.

For the front-end you can choose between two options running in Node.js environment.

**a) Vue.js based stack**
- We'd love to see you using Vuex

**b) React based stack**
- We'd love to see you using React-Redux or new context-API

What we are looking is good coding practices and SoC/SRP principles when appropriate.

We expect that the project can be run by just using a single command after dependencies are installed. For example:

```
$ npm install
$ npm run demo-ui
```

### UI and features
![main_page](https://user-images.githubusercontent.com/39155036/141940668-7acc4875-9449-46ca-899f-f8e86d33d7ff.png)



_Example UI with modern web browser._

The UI should be responsive design and work with different screen sizes. You don't need to support legacy browsers, so UI needs to work only on modern desktop and mobile browsers.

#### Requirements
* Search box to filter results from your personal record shelf.
* Checkboxes to select where search filter applies.
  * When an artist is selected only artist matching the search term displayed.
  * When an album is selected only albums matching the search term displayed.
  * When both are set, and the search term matches the artist and album name
* A button to add a new album.
* Area where the albums added by the user are being displayed.
  * The initial state for the record collection is to show the mock data.
  * You get the album cover (size 300x300px), tracklisting and track lengths from the Last.fm API when available.
* ... menu will display a drop down menu with an option to remove album. You can use this to remove the album from you virtual record collection.

##### Adding new albums
It is up to you how you manage adding albums and artists to the database. For example, you could integrate it to show albums through Last.fm API. Adding an album that is not in Last.fm should be possible too. Do not allow adding the same artist or album with the same name multiple times.

## Part 2 - Backend
Here you are going to make Node.js back-end application and design API for it. It should provide all of the facilities that front-end application needs without any other front-end API calls. For the Node.js backend you can use libraries like Express.js.

You do not need to implement permanent storage. But if you wish to do so, then getting it running should be simple and instructions clear.

We expect that the project can be run by using a single command after dependencies have been installed. For example:

```
$ npm install
$ npm run demo-backend
```

For implementing the API you have two choices. You can choose between `GraphQL` and `REST`.

### API functionality
As we also ask you to design a simple API, we only give few general guidelines on what the API should do. The initial state is the mock data provided.

#### Requesting data
* Get all albums in the virtual record shelf.
* Proper filtering of the data where needed. For example get all albums by `artist name` or `artist id`.

#### Inserting / updating data
* Add an album.
* Remove an album.
* Decision on how adding an album when there is no artist yet works.

## Bonus assignment for frontend and backend
* We'd like to see that some software parts contain appropriate tests that can be run with a single command.


_**Please test your submission by cloning it into a new folder before sending it to us. Make sure it is working as intended, and for example, you are not relying on any files you have set into .gitignore.**_
