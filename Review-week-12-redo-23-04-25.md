# React Review 1

## Instructions

- You may refer to available documentation (online or personal notes) when creating solutions for this review.
- Please provide your answers directly in a single Markdown file named `review-week-12.md`. You do not need to submit a full React application; it is entirely possible to complete the entire test by simply writing your code snippets, answers, and explanations within this Markdown file. If you prefer to develop your solution in a React environment (eg `npm create vite@latest my-react-app --template react`) and then copy and paste the relevant code into the Markdown file, that is perfectly acceptable. Your final submission should consist solely of the `review-week-12.md` file.

## Questions

// ### 1. Create a Simple Component

Write the code for a component called `Welcome` that displays the text `<h1>Welcome to React!</h1>`

// Answer:/

function Welcome() {
return <h1>Welcome to React!</h1>;
}
export default Welcome;

// ### 2. Create a Bigger Component
// Write the code for a component called `HelloWorld` that displays `<p>Hello</p>`on one line and `<p>World</p>` on the next

// Answer:/

function HelloWorld() {
return (
<>
<p>Hello</p>
<p>World</p>
</>
);
}  
export default HelloWorld;

// ### 3. Create an Image Component

// Write the code for a component called `ProfilePicture`, it should:

// 1. Return an `<img/>` element
// 2. Set the value for the `src` attribute to `'../assets/images/profile-picture.jpg'`
// 3. Set the value of the `alt` attribute to `'The users profile picture'`

// Answer:/

function ProfilePicture() {
return (
<img
        src="../assets/images/profile-picture.jpg"
        alt="The users profile picture"
      />
);
}
export default ProfilePicture;

// ### 4. Create a Component that Uses Variables

// Answer:/

Create a component, it should:

1. Return a `<p>` element with the value of the `name` variable
2. Return a `<p>` element with the value of the `age` variable

Ensure that you use the variables directly in your code, **not** the string values that they point to

```js
const name = "John Doe";
const age = "30";
```

const name = "John Doe";
const age = "30";
function UserInfo() {
return (
<>
<p>{name}</p>
<p>{age}</p>
</>
);
}
export default UserInfo;

// ```js

// // ### 5. Is the Code Correct? Components

// // Is the code example below written correctly?

// // If you think it is, explain what HTML you expect the `ShoppingList` component to render

// // If not, explain why you think it's not written correctly

// Answer:/

Components are written in PascalCase, so the component name should be `Apple` instead of `apple`. Also, the component should be used as `<Apple />` instead of `<apple />`.

/_ Wrong Code: _/

const apple = () => {
return <li>Green Apple</li>;
};

const ShoppingList = () => {
return (
<section>
<h1>Apples</h1>
<apple />
<apple />
<apple />
</section>
);
};

// Correct Code:

const Apple = () => {
return <li>Green Apple</li>;
};
const ShoppingList = () => {
return (
<section>
<h1>Apples</h1>
<Apple />
<Apple />
<Apple />
</section>
);
};
export default ShoppingList;

// ### 6. Export a Component

// Write the code that would export a `TableOfContents` component

// Answer:/

export default TableOfContents;
const TableOfContents = () => {
return (
<div>
<h2>Table of Contents</h2>
<ul>
<li>Introduction</li>
<li>Chapter 1</li>
<li>Chapter 2</li>
</ul>
</div>
);
};

export default TableOfContents;

// ### 7. Import a Component

// Imagine you are writing code for a React project with a `components` directory.

// Inside the `components` directory there are two files:

// `// src
// └── components
//     ├── Profile.jsx
//     └── Gallery.jsx
//`

// Inside `Gallery.jsx` write the code that would import the `Profile` component from `Profile.jsx`

// Answer:/
// ```js
import Profile from './Profile.jsx';

// ### 8. Is the Code Correct? JSX

// Is the code example below written correctly?

// If you think it is, explain what HTML you expect the `ShoppingList` component to render

// If not, explain why you think it's not written correctly

// `js
// const ShoppingList = () => {
//   return (
//     <h2>Shopping List</h2>
//     <ul>
//       <li>Apples</li>
//       <li>Bananas</li>
//       <li>Oranges</li>
//     </ul>
//   );
// };
// `
// Answer:/

The code is not written correctly. The `return` statement should only return a single element. In this case, the `h2` and `ul` elements are siblings, which is not allowed in JSX. To fix this, you can wrap them in a single parent element, such as a `div` or a React fragment (`<>...</>`).

const ShoppingList = () => {
return (
<>
<h2>Shopping List</h2>
<ul>
<li>Apples</li>
<li>Bananas</li>
<li>Oranges</li>
</ul>
</>
);
}
export default ShoppingList;

// ### 9. Fix the JSX Bugs

// Fix the code below so that it doesn't break any JSX rules

// There are 4 bugs in the code.

// `js
// const Summary = () => {
//   return (
//       <div class="title">
//         <h1>My Site!</h1>
//       </div>
//       <p class="description">
//         You can find my thoughts here
//         <br><br>
//         <b>And <i>I</b></i> have plenty of them!
//       </p>
//   );
// }
// `

// Answer:/

const Summary = () => {
return (
<>
<div className="title">
<h1>My Site!</h1>
</div>
<p className="description">
You can find my thoughts here
<br />
<br />
<b>
And <i>I</i>
</b>{" "}
have plenty of them!
</p>
</>
);
}
export default Summary;

//Fixes made:
// 1. Changed `class` to `className`
// 2. Added a closing tag for the `br` elements
// 3. Changed the `b` and `i` tags to be properly nested
// 4. Wrapped the entire return statement in a React fragment (`<>...</>`)

// ### 10. Create a Component with a Prop

// Write the code to create a component called `Greeting`, it should:

// 1. Return a `<p>`
// 2. Receive a single prop called `name`
// 3. Render the word `Hello` followed by the value of the `name` prop

// Answer:/

function Greeting({ name }) {
return <p>Hello {name}</p>;
}
export default Greeting;
// ```

// ### 11. Pass a Prop to a Component

// Copy the `Greeting` component you created in the previous question. Pass the `name` prop to your component with any string value you like.
// You will nest your `Greeting` component inside the below `App` component:

// `js
// function App() {
//   return <></>;
// }
// export default App;
// `

// You have previously created a `Greeting` component that expects a prop called name. Copy the `Greeting` component you created in the previous question. Now, within the `App` component above, import the `Greeting` component and pass it the `name` prop with a string value of your choice. Nest the `Greeting` component within the `App` component. Write your updated `App` component code.

// Answer:/

import Greeting from './Greeting';
function App() {
return (
<>
<Greeting name="Mischa" />
</>
);
}
export default App;
