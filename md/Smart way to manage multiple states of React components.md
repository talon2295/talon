# Smart way to manage multiple states of React component

For example, let's say you have a form componenet with name, email and message as fields.
To make it work, you have to declare 3 different states, like this.

```typescript
const [name, setName] = useState("") ;
const [email, setEmail] = useState("") ;
const [message, setMessage] = useState("") ;
```

```tsx
<input type="text" value={name} onChange={(e) => {setName(e.target.value)}} />
```

The same result can be achieved by using the `useReducer` hook.

```typescript
const [state, updateState] = useReducer((prev: State, next: Partial<State>) => { return { ...prev, ...next } }, {
    name: "",
    email: "",
    message: ""
});
```

```tsx
<input type="text" value={state.name} onChange={(e) => updateState({name:e.target.value})} />
```

You can also add some logic before update the state.

```typescript
const [state, updateState] = useReducer((prev: State, next: Partial<State>) => {
    const newState = { ...next };
        
    if(newState.name) {
        newState.name = newState.name.toLocaleUpperCase() ;
    }

    return { ...prev, ...newState }
}, {
    name: "",
    email: "",
    message: ""
});


```
