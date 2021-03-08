
Notes on the build and each thing i did

App.js

changed function to a class
add constructer for components, initualize the state(props)

in the state add empty array[]  users and page numbers by default will be 1
added Component in line 1
created a User List
it renders...yaa

componentDidMount() add a const for url we want to make a page variable. taken from 
the stage right now  page=${this.state.pageNum}` use ``nest link in backticks
took out the 2 and added = ...
    use fetch(url) to get data from this url
        .then convert response to json 
        .then save users to the state using setState()method

https://reqres.in/

check to see what displays from data
create a conts (constituent) user from this . state inside the render method, map method to display users 
under return 
each element in our component has to have one element so 
wrap > Users List:< in div
map method to display users
add user.id and user.email
don’t forget the key to be users ID or can map with index

it works...

using bootstrap to style
html
found link under css here
https://getbootstrap.com/docs/4.3/getting-started/introduction/

says to load <link> into <head> before all other style sheets to load css

back to 
App.js
add a className with container to our return div

https://getbootstrap.com/docs/4.3/components/jumbotron/
text for header

cut out most except the H1 tag
in react we need to have className instead of class so fix that

the view has user list in a sort of header and a list called of emails

to the cards
https://getbootstrap.com/docs/4.3/components/card/
picked simplest can change later
put inside map method
change every class to className
in image src add {user.avatar} for source in the empty string spot
add key on end of <div className='card ......set to user.id
cut out    <p key = {user.id}>{user.email} </p> from last line
make sure to close img, must for react
in img line using avatar 
ass user.email and make sure to use backtics  <img src={user.avatar} className="card-img-top" alt={`${user.email} avatar`}/> how it has in the json
remove Card Title and ass {user,first_name}{user,last_name}
remove the button uless you want to do something with it...but i cant think of anything
remove all the paragraph stuff and add {user,email}
remove style  on cars ass some in css later

it works , yaaa

pics are screen width so need to resize cards

add a container called users. div wrapped about the map method inside parent div 


App.css
removed all old styling

add a couple lines to row wrap

looking for other pages
bootstrap button group
pick a grouping of buttons and add them to the bottom of the div we just made in 
App.js
remember to change to className
renamed buttons for previous, the current page with page number and next

add style to container to center the buttons
changed previous to prev so the buttons were even

have to create a function that will change the pages 
need an API call for this...i have not done this correctly as of yet
under fetch code block make an api call function

changePage
COPY line 15 - 18 under codeDidMount code block with the Api and put in you new changePage function 
will use pageNum which will be parameter of the function
remove this.state and leave pageNum
can remove code under componentDidMount and use the new changePage name you just made and do this,changePage to call the function.
add page num from the state with this.state.pagNum

add change page function to the buttons
add onClick to both prev and next
the prev page will be current page -1
next will be current page +1
removed button feature from the center button for pageNum
in change page add pageNum to pull from the parameter

disable prev button if page num is less then 1
under first type button 
add disabled= the condition
will not have less then 1 page

add 1 more property to the state totalPages set to 0 at begining
then in fetch set totaly of pages when we get a response

add a conditoin in the last button to check if our current page is the last one
if it is disable button
add a little css 
























# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
