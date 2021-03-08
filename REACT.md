# Anthony JEAMME React/JSX Style Guide

## Basic Rules

- One file = One Component
  - only stateless or pure Components are allowed

## Naming

- PascalCase for filenames and Components
- no components stuff name in camelCase
- filename = name of the component
- Root element of a Component has a component name has className. Other classes don't use CamelCase.

```jsx
const MySuperComponent = () => {
  // none component variables in camelCase.
  const sayMyName = "Heisenberg";

  return (
    // Root element has the name of the component.
    <div className="MySuperComponent">{sayMyName}</div>
  );
};
```

_MySuperComponent.jsx_

> Why ? The developer can easily find the file of where the Component is implemented.

## Hooks

- Use Custom React hooks every time you can.

```jsx
// Bad
const MyComponent = () => {
  const [isOpen, setIsOpen] = useState(false);

  const handleClick = () => {
    setIsOpen(true);
  };

  return (
    <div className="MyComponent">
      <button onClick={handleClick}>open</button>
      <Modal isOpen={isOpen} setIsOpen={setIsOpen} />
    </div>
  );
};

// Good
const MyComponent = () => {
  const myModal = useModal();

  const handleClick = () => {
    myModal.setIsOpen(true);
  };

  return (
    <div className="MyComponent">
      <button onClick={handleClick}>open</button>
      <Modal {...myModal} />
    </div>
  );
};
```

- Put logic in custom hooks

```jsx
const MyComponent = () => {
  const textEditor = useTextEditor();

  return (
    <div className="MyComponent">
      <div className="buttons">
        <button
          onClick={() => {
            textEditor.setBold();
          }}
        >
          bold
        </button>
      </div>
      <EditorContent {...textEditor} />
    </div>
  );
};
```

## Tags

- Alwas self-close tags that have no children.

```jsx
// bad
<MyComponent></MyComponent>

// good
<MyComponent />
```
