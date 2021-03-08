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
