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
