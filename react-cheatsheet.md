# Ultimate React Cheat Sheet

## 🌟 Fundamentals

### React Basics
- **What is React?**
  - A JavaScript library for building user interfaces
  - Developed by Facebook (Meta)
  - Component-based architecture
  - Uses declarative approach (ou describe WHAT you want to build, not HOW to build it)

- **Virtual DOM vs Real DOM**
  | Virtual DOM | Real DOM |
  |-------------|----------|
  | In-memory representation | Actual browser DOM |
  | Faster manipulation | Slower manipulation |
  | Batch updates | Direct updates |
  | No direct UI changes | Direct UI changes |

### Key Features
1. Virtual DOM
2. Component-Based Architecture
3. Unidirectional Data Flow
4. JSX Support
5. Rich Ecosystem
6. Cross-Platform Support

## 💻 Components & JSX

### JSX
- JavaScript XML
- Allows writing HTML-like code in JavaScript
- Must be transformed by tools like Babel
- Rules:
  - Single parent element
  - All tags must be closed
  - camelCase property naming

### Components
#### Class Components
```jsx
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

#### Functional Components
```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

#### Differences
| Class Components | Functional Components |
|-----------------|----------------------|
| Uses ES6 class syntax | Simple functions |
| Has lifecycle methods | Uses hooks |
| Can have state | Uses useState hook |
| More verbose | More concise |

## 🔄 State & Props

### State
- Mutable data
- Managed within component
- Updated using setState/useState
- Triggers re-render when changed

### Props
- Immutable data
- Passed from parent
- Read-only
- Used for component communication

### Data Flow
1. **Props Drilling**: Passing props through multiple levels
2. **Lifting State Up**: Moving state to common ancestor
3. **Context API**: Global state management

## 🪝 Hooks

### Common Hooks
- **useState**: State management
  ```jsx
  const [count, setCount] = useState(0);
  ```

- **useEffect**: Side effects
  ```jsx
  useEffect(() => {
    // Effect code
    return () => {
      // Cleanup code
    };
  }, [dependencies]);
  ```

- **useContext**: Context consumption
- **useRef**: DOM references
- **useMemo**: Value memoization
- **useCallback**: Function memoization

### Rules of Hooks
1. Only call hooks at top level
2. Only call hooks from React functions
3. Must be consistent in render calls

## 🚀 React 18 Features

### Concurrent Rendering
- Allows interrupting rendering
- Improves user interface responsiveness
- Enables new features like Suspense

### New Features
1. **Automatic Batching**
   - Automatically groups state updates
   - Improves performance

2. **useTransition**
   ```jsx
   const [isPending, startTransition] = useTransition();
   ```
   - Marks state updates as non-urgent
   - Helps prioritize updates

3. **Suspense Improvements**
   - Better streaming SSR support
   - Simplified data fetching
   - Improved error handling

4. **Server Components**
   - Zero bundle size components
   - Improved performance
   - Better SEO

## 🔧 Performance Optimization

### Techniques
1. **Memoization**
   ```jsx
   const MemoComponent = React.memo(MyComponent);
   ```

2. **Code Splitting**
   ```jsx
   const MyComponent = React.lazy(() => import('./MyComponent'));
   ```

3. **Error Boundaries**
   ```jsx
   class ErrorBoundary extends React.Component {
     componentDidCatch(error, errorInfo) {
       // Handle error
     }
   }
   ```

### Testing
1. **Jest**: Testing framework
2. **React Testing Library**: Component testing
3. **Shallow Rendering**: Unit tests
4. **Full Rendering**: Integration tests

## 🛠 Advanced Concepts

### Portals
- Render children outside DOM hierarchy
- Useful for modals, tooltips

### Fragments
```jsx
<React.Fragment>
  <ChildA />
  <ChildB />
</React.Fragment>
```

### Context API
```jsx
const MyContext = React.createContext(defaultValue);
```

### Higher-Order Components (HOC)
```jsx
const withLogger = (WrappedComponent) => {
  return class extends React.Component {
    // Enhanced component logic
  };
};
```

## 🎯 Best Practices

1. **Component Organization**
   - One component per file
   - Clear folder structure
   - Consistent naming

2. **Performance**
   - Use production builds
   - Implement lazy loading
   - Optimize re-renders

3. **State Management**
   - Keep state as local as possible
   - Use appropriate tools (Context, Redux)
   - Avoid prop drilling

4. **Error Handling**
   - Implement error boundaries
   - Use try-catch where needed
   - Proper error messaging
