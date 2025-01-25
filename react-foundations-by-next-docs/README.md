# React Foundations By Next Docs

this is my journey to learn and understand React

## Question & Answer

**Q1- what is building blocks of a web applications ?** <br />
**A1-** there are few things you need to consider while building a modern applications. such as:
- **User Interface:** how user will consume and interact with the application.
- **Routing:** how users navigate between different parts of your application.
- **Data Fetching:** where your data lives and how to get it.
- **Rendering:** when and where you render static or dynamic content.
- **Integrations:** what third-party services you use (for CMS, auth, payments, etc.) and how you connect to them.
- **Infrastructure:** where you deploy, store, and run your application code (serverless, CDN, edge, etc.).
- **Performance:** how to optimize your application for end-users.
- **Scalability:** how your application adapts as your team, data, and traffic grow.
- **Developer Experience:** your team's experience building and maintaining your application. <br />

**Q2- What is React ?** <br />
**A2- React** is a JavaScript library for building interactive user interfaces. It's particularly well-suited for creating *8single-page applications (SPAs)** and **dynamic UIs**.

**Q001- What is Next.js ?** <br />
**A001 - Next.js** is a **React framework** that provides additional features and tools to simplify the development of web applications. It includes features like **server-side rendering**, **automatic code splitting**, and **file-system routing**, making it easier to build fast and scalable web applications.


**Q002- How does Next.js help with building web applications ?** <br />
**A002- Next.js** offers several features that streamline the development process, including:
- **Server-side rendering (SSR):** Renders pages on the server, improving initial load times and SEO.
- **Automatic code splitting:** Optimizes page loading by only loading the necessary JavaScript4code for each page.
- **File-system routing:** Creates routes based on the file and folder structure of your project, simplifying routing configuration.
- **API routes:** Allows you to create serverless functions within your Next.js application, making it easier to handle data fetching and other server-side tasks.

**Q003- What are the benefits of using React and Next.js ?** <br />
**A003-** Some of the benefits of using React and Next.js include:
- **Improved performance:** Features like SSR and code splitting can significantly improve page load times.
- **Enhanced user experience:** React's component-based architecture and virtual DOM make it easier to build dynamic and interactive UIs.
- **Increased developer productivity:** Next.js provides a range of features and tools that can speed up development and make it more efficient.
- **Better SEO:** SSR can help improve your application's search engine ranking.
- **Strong community and ecosystem:** React and Next.js have large and active communities, providing access to a wealth of resources, tutorials, and libraries.

**Q3- What is DOM ?** <br />
**A3-** The **Document Object Model (DOM)** is an object representation of the HTML elements on a web page.

**Q004- How does the browser render a web page ?** <br />
**A004-** When a user visits a web page, the server returns an HTML file to the **browser**. The **browser** then reads the HTML and constructs the **DOM**. The **DOM** is an object representation of the HTML elements.  

## Folder Structure:

```
|- chapter-03
    |- index.html
|- chapter-04
    |- index.html
|- chapter-05
    |- index.html
|- chapter-06
    |- index.html
|- chapter-07
    |- index.html
|- README.md
```

## Code Explaining

- chapter-03/index.html
```html
<html>
	<body>
		<div
			id="app"
		>			
		</div>
		<script
			type="text/javascript"
		>
			// Select the div element with 'app' id
			const app = document.getElementById('app');
		
			// Create a new H1 element
			const header = document.createElement('h1');

			// Create a new text node for the H1 Element
			const text = 'Develop. Preview. Ship.';
			const headerContent = document.createTextNode(text);

			// Append the text to H1 element
			header.appendChild(headerContent);

			// Place the H1 element inside the div
			app.appendChild(header);			
		</script>
	</body>
</html>
```

- chapter-04/index.html
```html
<html>
	<body>
		<div
			id="app"
		></div>
		<!-- adding react -->
		<script 
			src="https://unpkg.com/react@18/umd/react.development.js"
		></script>
		<!-- adding react dom -->
		<script 
			src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
		></script>
		<!-- adding babel -->
		<script 
			src="https://unpkg.com/@babel/standalone/babel.min.js"
		></script>
		<!-- react use jsx -->
		<script
			type="text/jsx"
		> 
				// Select the div element with 'app' id
				const app = document.getElementById('app');

				// react root using reactDOM
				const root = ReactDOM.createRoot(app);

				// you can render any jsx inside the render 
				root.render(<h1>Develop. Preview. Ship.</h1>);
		</script>
	</body>
</html>
```

- chapter-05/index.html
```html
<html>
	<body>
		<div
			id="app"
		></div>
		<!-- adding react -->
		<script 
			src="https://unpkg.com/react@18/umd/react.development.js"
		></script>
		<!-- adding react dom -->
		<script 
			src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
		></script>
		<!-- adding babel -->
		<script 
			src="https://unpkg.com/@babel/standalone/babel.min.js"
		></script>
		<!-- react use jsx -->
		<script
			type="text/jsx"
		> 
				// Select the div element with 'app' id
				const app = document.getElementById('app');

				function Header() { // component name should be in capatilized
					return <h1>Develop. Preview. Ship.</h1>;
				}

				function HomePage() {
					return (
						<div>
							<Header /> {/*  you can call other component inside a component */}
							<p>
								Welcome to home page.
							</p>
						</div>
					)
				}

				// react root using reactDOM
				const root = ReactDOM.createRoot(app);

				// you can render any jsx inside the render 
				root.render(<HomePage />);
		</script>
	</body>
</html>
```

- chapter-06/index.html
```html
<html>
	<body>
		<div
			id="app"
		></div>
		<!-- adding react -->
		<script 
			src="https://unpkg.com/react@18/umd/react.development.js"
		></script>
		<!-- adding react dom -->
		<script 
			src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
		></script>
		<!-- adding babel -->
		<script 
			src="https://unpkg.com/@babel/standalone/babel.min.js"
		></script>
		<!-- react use jsx -->
		<script
			type="text/jsx"
		> 
				// Select the div element with 'app' id
				const app = document.getElementById('app');

				function Header({ title }) { // component name should be in capatilized - you can assign all the props as function parameters
					return <h1>{title}</h1>;
				}

				function HomePage() {
					const names = ['Ada Lovelace', 'Grace Hopper', 'Margaret Hamilton'];
					return (
						<div>
							<Header title="Develop. Preview. Ship." /> {/*  you can call other component inside a component - you can use props in the component by passing the then utilize then inside the component as dynamic data */}
							{/*<p>
								Welcome to home page.
							</p>*/}
							{names.map((name) => ( // JSX only return in round brackets
								<li key={name}>{name}</li>
							))}
						</div>
					)
				}

				// react root using reactDOM
				const root = ReactDOM.createRoot(app);

				// you can render any jsx inside the render 
				root.render(<HomePage />);
		</script>
	</body>
</html>
```

- chapter-07/index.html
```html
<html>
	<body>
		<div
			id="app"
		></div>
		<!-- adding react -->
		<script 
			src="https://unpkg.com/react@18/umd/react.development.js"
		></script>
		<!-- adding react dom -->
		<script 
			src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
		></script>
		<!-- adding babel -->
		<script 
			src="https://unpkg.com/@babel/standalone/babel.min.js"
		></script>
		<!-- react use jsx -->
		<script
			type="text/jsx"
		> 
				// Select the div element with 'app' id
				const app = document.getElementById('app');

				function Header({ title }) { // component name should be in capatilized - you can assign all the props as function parameters
					return <h1>{title}</h1>;
				}

				function HomePage() {
					const names = ['Ada Lovelace', 'Grace Hopper', 'Margaret Hamilton'];
					const [like, setLike] = React.useState(0); // useState is a hook to manage state in functional component
					const handleClick = () => {
						setLike(like + 1); // set the state value
					}
					return (
						<div>
							<Header title="Develop. Preview. Ship." /> {/*  you can call other component inside a component - you can use props in the component by passing the then utilize then inside the component as dynamic data */}
							{/*<p>
								Welcome to home page.
							</p>*/}
							<ul>
								{names.map((name) => ( // JSX only return in round brackets
									<li key={name}>{name}</li>
								))}
							</ul>
							<button onClick={handleClick}>Like({like})</button> {/* you can add event listener in JSX */}
						</div>
					)
				}

				// react root using reactDOM
				const root = ReactDOM.createRoot(app);

				// you can render any jsx inside the render 
				root.render(<HomePage />);
		</script>
	</body>
</html>
```