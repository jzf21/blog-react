

# Setting up a React Project with Vite and Tailwind CSS

## Step 1: Create a React project with Vite

Open your command prompt (CMD) or use the terminal in Visual Studio Code and follow these steps:

1. Navigate to the desired folder where you want to create your project.
   ```
   cd path/to/your/folder
   ```

2. Run the following command to generate a new React project using Vite:
   ```
   npx create-vite@latest
   ```

3. When prompted, enter the name of your project.

4. Select the "react" template when asked to choose a template for your project.

## Step 2: Initialize Tailwind CSS

To set up Tailwind CSS in your project, refer to the official documentation for detailed instructions. Visit the Tailwind CSS documentation: [https://tailwindcss.com/docs/guides/vite](https://tailwindcss.com/docs/guides/vite)

## Step 3: Navigate to Your Project

Navigate into your project directory by running the following command in your command prompt or terminal:
```
cd my-project
```

Replace "my-project" with the actual name of your project.

## Step 4: Open the Project in Visual Studio Code

To open your project in Visual Studio Code, you have two options:

1. Open Visual Studio Code and click on "File" > "Open Folder." Select your project folder and click "Open."

2. Alternatively, from your command prompt or terminal, run the following command:
   ```
   code .
   ```

This will open the project in Visual Studio Code directly.

## Step 5: Study the Folder Structure

Inside your project, you will find a folder structure similar to the following:

```
- my-project
  - src
    - components
    - pages
    - styles
  - public
  - package.json
  - ...
```

- `src`: This folder contains your React components and application logic.
- `components`: This folder is where you can create reusable React components.
- `pages`: This folder contains the individual pages or views of your application.
- `styles`: This folder is used to store your custom CSS or styling files.

Feel free to explore and modify these folders to suit your project needs.

# Step 6: Identifying Components for a Todo App

As you start building your Todo app using Tailwind CSS, it's important to have a brief idea about the different components you would require. Let's explore the components commonly found in a Todo app:

## 1. Navbar/Sidebar

A navbar or sidebar provides navigation and easy access to different sections of the app. It typically includes links or buttons to switch between views, such as the Todo list, settings, or user profile.

## 2. Todo List

The Todo list component is the central part of the app that displays the list of todos. Each todo item usually includes a checkbox to mark it as completed, the task description, and an optional delete button.

## 3. Todo Item

A single todo item represents a task in the Todo list. It consists of the task description, a checkbox to mark it as completed, and a delete button to remove it from the list.

## 4. Todo Form

The Todo form component allows users to add new tasks to the Todo list. It typically includes an input field where users can enter the task description and a submit button to add the task.

## 5. Filters

Filters help users to view specific subsets of their Todo list based on criteria such as completed tasks, active tasks, or tasks with a specific label. These filters can be implemented using buttons or dropdown menus.

## 6. Label Component

Labels are optional features that allow users to categorize tasks. A label component can be used to display and assign labels to individual tasks in the Todo list.

## 7. Empty State

The empty state component is displayed when the Todo list is empty. It provides a message or prompt to guide users on how to get started by adding their first task.

These are the core components commonly used in a Todo app. Depending on your app's requirements, you may also consider additional features like task editing, due dates, prioritization, or user authentication.

By breaking down the app into these components, you can approach development in a modular and organized manner, focusing on one component at a time.

Remember, Tailwind CSS provides utility classes that can be used to style these components efficiently and achieve a consistent design throughout your app.

In the next steps, we will dive deeper into each component and implement them in your Todo app.

# Step 7: Creating Individual Components

Now that you have identified the components needed for your Todo app, it's time to create the individual components. Follow these steps to add files to your components folder and create the components:

1. Open your project in Visual Studio Code.

2. Inside the "src" directory, create a new folder named "components" if it doesn't already exist.

3. Create a new file for each component within the "components" folder. For example, create the following files:

   - `Navbar.jsx` (for the Navbar/Sidebar component)
   - `TodoList.jsx` (for the Todo List component)
   - `TodoItem.jsx` (for the Todo Item component)
   - `TodoForm.jsx` (for the Todo Form component)
   - `Filters.jsx` (for the Filters component)
   - `Label.jsx` (for the Label component)
   - `EmptyState.jsx` (for the Empty State component)

4. Open each component file and start implementing the respective component logic and JSX structure. You can use React functional components for simplicity.

   For example, in `Navbar.jsx`:
   ```jsx
   import React from 'react';

   const Navbar = () => {
     return (
       <nav>
         {/* Navbar content */}
       </nav>
     );
   };

   export default Navbar;
   ```

   Repeat this process for each component, customizing the content and structure as per your requirements.

5. Add the necessary Tailwind CSS classes to style each component. You can apply the classes directly within the JSX or create separate CSS files for each component.

   For example, in `TodoList.jsx`:
   ```jsx
   import React from 'react';

   const TodoList = () => {
     return (
       <div className="bg-white p-4 rounded-lg">
         {/* Todo List content */}
       </div>
     );
   };

   export default TodoList;
   ```

6. Repeat steps 4 and 5 for all the other components, ensuring that each component file is properly implemented and styled.

# Step 8: Putting Together All the Components in app.jsx

Now that you have created the individual components, it's time to integrate them into the main `app.jsx` file. Follow these steps:

1. Open the `app.jsx` file located in the root of the `src` directory.

2. Import the components you have created:
   ```jsx
   import Navbar from './components/Navbar';
   import TodoList from './components/TodoList';
   import TodoForm from './components/TodoForm';
   // Import other components as needed
   ```

3. Within the main `App` component, use the imported components to compose your Todo app's structure:
   ```jsx
   function App() {
     return (
       <div className="container mx-auto">
         <Navbar />
         <TodoList />
         <TodoForm />
         {/* Add other components here */}
       </div>
     );
   }
   ```

4. Customize and arrange the components based on your desired layout and structure.

5. Save the `app.jsx` file.

Congratulations! You have now created the individual components and assembled them in the main `app.jsx` file. You can continue working on each component to add functionality and styling as needed.
# Step 9: Adding Custom Todo Components with Props Drilling

To enhance the functionality of your Todo app, you can create custom components that accept props to handle specific tasks or display data. Let's explore how to add custom Todo components and utilize props drilling:

1. Identify the functionality or data that you want to handle with a custom component. For example, you might want to create a `TodoItem` component to render individual todo items.

2. Create a new file in the `components` folder for your custom component. For example, create a file named `TodoItem.jsx`.

3. Open the `TodoItem.jsx` file and define a functional component that accepts props. For instance:
   ```jsx
   import React from 'react';

   const TodoItem = ({ todo }) => {
     return (
       <div>
         <input type="checkbox" checked={todo.completed} />
         <span>{todo.description}</span>
         <button>Delete</button>
       </div>
     );
   };

   export default TodoItem;
   ```

4. Customize the JSX structure and styling within the component based on your requirements. In this example, we're rendering a checkbox, the todo description, and a delete button.

5. Save the `TodoItem.jsx` file.

6. In your `TodoList` component, import the `TodoItem` component.
   ```jsx
   import TodoItem from './TodoItem';
   ```

7. Within the `TodoList` component's JSX, map over the todos and render a `TodoItem` component for each todo:
   ```jsx
   const TodoList = ({ todos }) => {
     return (
       <div>
         {todos.map((todo) => (
           <TodoItem key={todo.id} todo={todo} />
         ))}
       </div>
     );
   };
   ```

8. Pass the necessary props from the parent component (in this case, `TodoList`) to the `TodoItem` component. In this example, we're passing the `todo` object as a prop.

9. Customize the component rendering based on the data passed through props. For example, you can access the `todo` prop within the `TodoItem` component to display the appropriate data.

By using props drilling, you can pass data and handle functionality between parent and child components, allowing for reusable and modular code. Repeat these steps to create and integrate additional custom components for different features of your Todo app.

Remember to consider the necessary styling using Tailwind CSS utility classes within each component's JSX to achieve the desired look and feel.

In the next steps, we will explore how to add interactivity to your Todo app, such as handling user input and updating the Todo list.
