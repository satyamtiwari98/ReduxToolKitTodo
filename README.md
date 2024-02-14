# Redux Toolkit

Redux Toolkit is an opinionated, batteries-included toolset for efficient Redux development.

## Features

- Simplified Redux setup with fewer lines of code
- Includes utilities like `createSlice`, `createAsyncThunk`, and `createEntityAdapter` for managing state and data
- Built-in middleware setup for common Redux middleware like Redux Thunk and Redux DevTools Extension
- Improves performance with memoized selectors and immutable updates

## Installation

To install Redux Toolkit, use npm or yarn:

```bash
npm install @reduxjs/toolkit
```
or

```bash
yarn add @reduxjs/toolkit
```

## Usage

1. Set up the store:

```javascript

import { configureStore } from '@reduxjs/toolkit';
import rootReducer from './reducers';

const store = configureStore({
  reducer: rootReducer,
  middleware: (getDefaultMiddleware) => getDefaultMiddleware(),
});

```

2. Create Slices

```javascript

import { createSlice } from '@reduxjs/toolkit';

const counterSlice = createSlice({
  name: 'counter',
  initialState: 0,
  reducers: {
    increment: (state) => state + 1,
    decrement: (state) => state - 1,
  },
});

export const { increment, decrement } = counterSlice.actions;
export default counterSlice.reducer;

```

3. Use in Components :

```javascript

import { useDispatch, useSelector } from 'react-redux';
import { increment, decrement } from './counterSlice';

function Counter() {
  const dispatch = useDispatch();
  const count = useSelector((state) => state.counter);

  return (
    <div>
      <button onClick={() => dispatch(increment())}>Increment</button>
      <span>{count}</span>
      <button onClick={() => dispatch(decrement())}>Decrement</button>
    </div>
  );
}

```

## Documentation

For detailed documentation and examples, visit the [Redux Toolkit documentation](https://redux-toolkit.js.org/).

