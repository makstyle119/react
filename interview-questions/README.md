# Interview Questions

here you can find all questions for react (unsorted - and maybe in future i will sort them and keep adding them)

**Q1- What is React ?**  <br />
**A1- React** is a well known JavaScript Framework. use to build Frontend Websites ( Start populating for Single Page Web App - and now you can create almost anything).

---

**Q2- What are the main features of React ?**  <br />
**A2- React** have a bunch of feature to offer includes:
1. Virtual DOM
2. Component-Based Architecture
3. Unidirectional Data flow
4. JSX syntax

---

**Q3- What is Virtual DOM ?** <br />
**A3- Virtual DOM** is the lightweight copy of actual DOM. <br />
**How it's works: React** create a virtual DOM when on the first render and after every change in the page it will create a new **virtual DOM** and compare it with the previous one and update the changes on the real DOM for efficient rendering

---

**Q4- What is DOM (Actual DOM) ?** <br />
**A4- DOM (Document Object Model)** is the render frontend you can see on a web browser (including html, css and JavaScript). rerendering **Actual DOM** is quite expensive because it will reload the complete page.

---

**Q5- What are hooks in React ?**  <br />
**A5-** If you want to manage state or life cycle in function base component you can achieved it using hooks inside the React. <br />
few most common **hooks** are:
- **useState**
- **useEffect**
- **useRef**
- **useContext**
- **useReducer**
- **useMemo**

---

**Q6- How many type of component are in React ?**  <br />
**A6-** Inside **React** we have 2 types of components
- **Class Base Component:**
    - class base component use class and use life cycle method and this.state
    - **eg:**
        - componentDidMount
        - componentDidUnMount
        - componentDidUpdate
        - etc...
- **Function Base Component**
    - function base component use functions and use hooks for life cycle methods.  <br />
**note:** in new and last 3 year project you will only see function base component and class base are now only legacy codebase

---

**Q7- What useEffect do ?**   <br />
**A7- useEffect** is like a event trigger and you put come code inside a useEffect and in the end you put dependency state and the inside code will run every time code state update and if there is not state it will only run one on first render ( just like window.onload() ) - inside you can do anything like fetching data or doing something (i don't know - do whatever you like)
```
useEffect(() => {
    console.log('component render')
}, []) // one time only
useEffect(() => {
    console.log('state update')
}, [someState]) // every time state change
```

---

**Q8- What useState do ?**  <br />
**A8- useState** use to create state (state is same as a variable - it have extra power that if it's value change it will effect in virtual DOM then in real DOM as well.)
```
const [someState, setSomeState] = useState("some cool value");
```
state work in getter and setter mode, as you can see first value is a getter and second value is a setter which will update the state

---

**Q9- is there any other way to manage the state ?**  <br />
**A9** In **React** (class base component) you have to use `this.setState` to set state value. and we have bunch of libraries for state management,
- below are listed global state management tools (we can share data from one component to another by wrapping everything inside their store )
- **Redux:**
    - **Redux** is a third party and most popular tool for state management
    - there are multiple variants of **redux** (my personal favorite is **redux-toolkit**)
    - **Recommendation:** use **Redux** only for big project because it will increase complexity in the project
- **Context API**
    - **Context API** us React Built-in Global State management Solution
    - I personally use it for small project otherwise go with **Redux**
- and few more (maybe I will add more in future)

---

**Q10- What is Prop Drilling ?**  <br />
**A10- Prop Drilling** is the art of sending/passing variables and function from one component to another component
```
const Home ({name}) => {
    return (
        <>
            Hello {name},
        <>
    )
}

const layout () => {
    return (
        <Home name="Moiz" />
    )
}
```
- do we need to avoid it ?
    - we in simple it it's about 1 to 2 do it - it's not a bad thing and we definitely need it 
- and if we need to avoid then ?
    - use state management tools like **redux** or **context api**

---

**Q11- What is JSX ?**  <br />
**A11- JSX** is HTML for of React, in simple words you can't render html inside react component so we use JSX, and JSX have few simple rules
- all component either self closing or should have a closing tag
- use curly bracket `{}` for state or variables

---

**Q12- What is HOC (High-Order Component) ?**  <br />
**A12- HOC (High-Order Component)** takes a component and return a new component - common example is a layout component - use to add reusability and more logic to existing components.

---

**Q13- Can we make multiple stores in a single react app ?**  <br />
**A13-** Yes you can, you just have to add more provider as you add more stores in your app 
```
const ThemeContext = React.createContext();
const UserContext = React.createContext();

function App() {
  return (
    <ThemeContext.Provider value={{ theme: 'dark', toggleTheme: /* ... */ }}>
      <UserContext.Provider value={{ user: /* ... */, updateUser: /* ... */ }}>
        {/* Your application components */}
      </UserContext.Provider>
    </ThemeContext.Provider>
  );
}
```
yes this how you can do this.

---

**Q14- why map asked you to add a key in your map inside JSX ?**  <br />
**A14-** If you are dynamically rendering anything in **react**, **React** needs a unique identifier so it can update it later if required.

---

**Q15- give me a ideal React Folder Structure ?** <br />
**A15-** well here it's a decent folder structure for **React** App
```
📂 my-react-app
├── 📂 public
│   ├── 📄 index.html 
│   └── 📄 favicon.ico 
├── 📂 src/
│   ├── 📂 components/ 
│   │   ├── 📄 Button.js
│   │   ├── 📄 Input.js
│   │   ├── 📄 Header.js
│   │   ├── 📄 Footer.js
│   │   ├── 📄 Card.js 
│   │   └── ... 
│   ├── 📂 pages/
│   │   ├── 📄 Home.js
│   │   ├── 📄 About.js
│   │   ├── 📄 Contact.js
│   │   └── ...
│   ├── 📂 styles/
│   │   ├── 📄 GlobalStyles.css 
│   │   ├── 📄 Home.css
│   │   ├── 📄 About.css
│   │   └── ...
│   ├── 📂 utils/
│   │   ├── 📄 helpers.js
│   │   ├── 📄 api.js 
│   │   └── ... 
│   ├── 📂 assets/
│   │   ├── 📄 images/
│   │   │   ├── 📄 logo.png
│   │   │   ├── 📄 background.jpg
│   │   │   └── ...
│   │   ├── 📄 fonts/
│   │   │   ├── 📄 font-awesome.ttf 
│   │   │   └── ...
│   ├── 📄 App.js
│   ├── 📄 index.js
│   └── ...
├── 📄 package.json
├── 📄 README.md
└── ... (other configuration files like .gitignore, etc.)
```

---

**Q16- how can you create a custom hook in react ?**  <br />
**A16-** In **React** you can create a custom hook as any function (either calling an API or doing certain work).
- custom hooks good for reusable code
- a custom hook always start with the word `use` then whatever it do
```
function useCounter(initialValue = 0) {
  const [count, setCount] = useState(initialValue);

  const increment = () => {
    setCount(count + 1);
  };

  const decrement = () => {
    setCount(count - 1);
  };

  return { count, increment, decrement };
}

function MyComponent() {
  const { count, increment, decrement } = useCounter(5); 

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
    </div>
  );
}
```

---

## Resources
I start my journey using this cool stuff so shout to them:
- **[Abdullah Motiwala](https://pk.linkedin.com/in/abdullahmotiwala)** - special thanks to him, he guide me in almost all question and if you are looking for a great Software Engineer he is a great choice
- [Q1 - Q12](https://www.youtube.com/watch?v=eWRfhZUzrAc&t=12581s)