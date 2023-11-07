

**Hard Exercise:**
Topic: React State Management and Forms

**Exercise:**
Create a React component for a simple "To-Do List" application. The component should allow users to add and remove tasks, mark tasks as completed, and filter tasks (all, completed, or incomplete). You should manage the state and logic for these operations within the component.



**Very Hard Exercise:**
Topic: React Performance Optimization and Memoization

**Exercise:**
Create a React component that displays a list of items with the ability to filter items by name, and add items to the list. Optimize the component to avoid unnecessary re-renders and ensure smooth performance even with a large number of items.

**Answer:**
```jsx
import React, { useState, useMemo } from 'react';

function ItemList({ items, filter, addItem }) {
  const filteredItems = useMemo(() => {
    return items.filter((item) => item.name.toLowerCase().includes(filter.toLowerCase()));
  }, [items, filter]);

  return (
    <div>
      <input
        type="text"
        placeholder="Filter items by name"
        value={filter}
        onChange={(e) => setFilter(e.target.value)}
      />
      <button onClick={() => addItem({ id: items.length + 1, name: `Item ${items.length + 1}` })}>
        Add Item
      </button>
      <ul>
        {filteredItems.map((item) => (
          <li key={item.id}>{item.name}</li>
        ))}
      </ul>
    </div>
  );
}

function App() {
  const [filter, setFilter] = useState('');
  const [items, setItems] = useState([
    { id: 1, name: 'Item 1' },
    { id: 2, name: 'Item 2' },
    // Add more items here
  ]);

  const addItem = (item) => {
    setItems([...items, item]);
  };

  return (
    <div>
      <h2>Item List</h2>
      <ItemList items={items} filter={filter} addItem={addItem} />
    </div>
  );
}

export default App;
```

**Extremely Hard Exercise:**
Topic: React Advanced State Management and Context API

**Exercise:**
Create a React component for a multi-step form. The form should consist of multiple steps, and users should be able to navigate between steps. Implement a global context to manage the state of the form across steps and provide a way to submit the form data.

