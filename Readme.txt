1- Create a components folder in the src Folder.
2- make sure that our app will have the following class components.
1-App.js
2-Header.js
3-Movie.js
4-AddMovie.js

the App Component will be the root of our component.
by nature should import all other components and the app css that is exist on the src folder.
also we need to import the initialMoviews and additionalMovies json object from the movies.js that is located in the src folder.


the App compontent is a class that is extended from a component that have the following method

constructor() {}
loadAdditionalMovies() {}
addMovieToGallery(movie) {}
render() {}

starting with the contructor



We need state to be initialized along with the component class, which we can do via the constructor function.

When using a constructor function in a React class, you need to call super() first as the Component object 
we're extending needs to be initialized before anything else. 
Plus, the this keyword will not be available inside the constructor until after super() has returned.

this.state = {
      movies: the initial movies that we important from the moviesjs
    };


in the render method that should return 

<div className="App">
        <!-- header component that have a props of text and a motivational value !>
        <p className="App-intro">Sharing a few of our favourite movies</p>
        <div className="movies">
<!-- creating a list by using the map methods of react -->
a hint as below
          {
            Object
            .keys(//the this state of the movie)
            .map(key => <Movie key={key} meta={//the this state dotmovie[key]} />)
          }
        </div>
        <div className="add-movies"><button onClick={the this initialiazed method to load additional movies}>Load more...</button></div>
        <!-- the Add Movie with a prop event addMovie that fire the addMovieToGallery method -->
      </div>

the following methods 
loadAdditionalMovies() {}
addMovieToGallery(movie) {}
are to set the the state of the movies , one to load and one to add (this is to figure out the behavior).


Header.js
===============

a class component that should render and return 
<div className="App-header">
        <h2>the text props</h2>
      </div>

Movie.js
==============
a class movie component that render and return 
<div className="movie">
        <h2>title</h2>
      	<div><img alt="movie-poster" width="200" src=poster /></div>
        <p>(year)</p>
        <p>description</p>
      </div>

be aware that the props is a class so a keyword must be added, aslo an object of meta is available before each object, since we are using the map react.


AddMovie.js
==================
a class component that have addNewMovie(e) {} method and a render() {} method.

the first is responsible to repventDefault and set a movie variable with all it's object and then to set the props.addMovie(thevariable).

the render method will return a form as this.

<form className="movie-form" onSubmit={(e) => this.addNewMovie(e)}>
        <h2>Add movie to gallery</h2>
        <input ref={(input) => this.title = input} type="text" placeholder="Title" />
        <input ref={(input) => this.year = input} type="text" placeholder="Year" />
        <input ref={(input) => this.poster = input} type="text" placeholder="Poster" />
        <textarea ref={(input) => this.description = input} placeholder="Description">
        </textarea>
        <button type="submit">Add Movie</button>
      </form>

===================================

Good Luck.