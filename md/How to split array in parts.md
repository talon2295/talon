# How to split array in parts

Given an array of numbers, create 2 arrays with even and odd

```typescript
const numberArray = [1, 2, 8, 9, 6, 310, 4, 52, 48, 52, 77, 15, 27] ;
const [even, odd] = numberArray.reduce((prev, curr) => {
    prev[curr % 2].push(curr) ;
    return prev ;
}, [[] as number[], [] as number[]])
```

```vega-lite

```
