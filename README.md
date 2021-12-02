# Passing Thoughts

    This is a project made under Codecademy React 101 course for applying the knowledge of Hooks: useState and useEffect.

    In this place we will build a place for our passing thoughts which disappear just after 15 seconds.

Adding thoughts

## Task 1

    Run the app and take a look at what we have so far.

    The app's structure is there, but...well, it doesn't actually work! There are three major missing pieces right now:
    <ol>
        <li>If you try to add a new thought, it refreshes the whole page and doesn't do anything.</li>
        <li>If you try to delete a thought manually, it crashes!</li>
        <li>Thoughts never disappear, defeating the whole point of the app.</li>
    </ol>

    Before we start, let's talk about the main piece of state that the app stores: an array of thought objects. Each of those objects will have three properties:
    <ul>
        <li>id, a unique ID for this thought</li>
        <li>text, the thought's text</li>
        <li>expiresAt, the time that the thought expires, represented as a number</li>
    </ul>

    Take a look at App.js and you'll see that we're defining two starter thoughts like this,
        const [thoughts, setThoughts] = useState([

<br/> {
<br/> id: generateId(),
<br/> text: 'This is a place for your passing thoughts.',
<br/> expiresAt: getNewExpirationTime(),
<br/> },
<br/> {
<br/> id: generateId(),
<br/> text: "They'll be removed after 15 seconds.",
<br/> expiresAt: getNewExpirationTime(),
<br/> },
<br/> ]);

That will set the state to something like this:
<br/>[
<br/> {
<br/> id: 0,
<br/> text: 'This is a place for your passing thoughts.',
<br/> expiresAt: 1600624968405,
<br/> },
<br/> {
<br/> id: 1,
<br/> text: "They'll be removed after 15 seconds.",
<br/> expiresAt: 1600624968405,
<br/> },
<br/>]

When we create neww thought objects, we'll do something very similar to this. Let's get started!

## Task 2

Open the App component in App.js. You can see that we've already set up the array of thoughts in a variable called thoughts, using the useState() hook. We've also got setThoughts(), a function we can call to update the list of thoughts. Let's wire these things up so that users can add new thoughts.

First, we'll need to write a new function inside of App(), called addThought(). It will take a single argument, thought, and it will put itself of the thoughts array with setThoughts().

Inside of addThought(), we'll call setThoughts() with a function that returns a new state: the array with the new thought at the front.

Add this function between the end of the useState() call (the line ending with ]);) and the return.

## Task 3

Now we have a function that'll update the state, but we need to use it. Specifically, let's pass it to the AddThoughtForm component as a prop.

In App.js, find where AddThoughtForm is rendered. Pass a prop named addThought and give our newly created addThought() function as its value.

## Task 4

Now that we're passing addThought() into the AddThoughtForm component, it's time for us to make that component actually call this function.

AddThoughtForm will have some state. Specifically, it'll hold the value of the text input, and when the user submits the form, we'll take that input and use it in a call to addThought().

Open up AddThoughtForm.js.

On the first line, we'll need to import useState() and React. Update the import to import both React and useState().

Next, inside of AddThoughtForm, set up the intial state of the text input as an empty string.

After you have done that, you'll need to write a function called handleTextChange() that will be called when the input changes. It will take the event as an argument, and will call setText() to update the state.

Finally, you'll need to connect these two things to the input. Pass text in a prop called value, and pass handleTextChange() in a prop called onChange().

Now we're storing the state of the input!

## Task 5

Now that we have the input's state stored, we will need to create a new thought object when the form is submitted. Handling the form submission event is the first step of doing that.

Create a new function to handle the form submission called hadleSubmit(). It will take the event as an argument (just like how handleTextChange() does).

To prevent the form from refreshing the page, call event.preventDefault() inside handleSubmit(). This prevents the browser from performing its default behaviour when a form is submitted.

Finally, add the submit handler to the form by passing onSubmit={handleSubmit}.

Once you've done this, the form should no longer refresh the page. (Nothing else will happen either, but we'll fix that soon).

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
