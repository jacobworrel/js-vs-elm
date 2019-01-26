# js-vs-elm
Side-by-side mappings comparing JavaScript  vs. Elm.

This is intended to elaborate on the official Elm documentation [From JavaScript?](http://elm-lang.org/docs/from-javascript) page
so make sure you check that out first if you haven't already.

## JavaScript vs. Elm

### Operators

| JavaScript | Elm   |
| ---------- | ----- |
| `===`      | `==`  |
| `!==`      | `\=`  |
| `<`        | `<`   |
| `<=`       | `<=`  |
| `>`        | `>`   |
| `>=`       | `>=`  |

### Functions

| JavaScript                    | Elm               |
| ----------------------------- | ----------------- |
| `const add = (a, b) => a + b` | `add a b = a + b` |
| `add(1, add(1,2)`             | `add 1 (add 1 2)` |


### Arrays / Lists

#### Concatenation

##### JavaScript

```javascript
const a = [1,2];
const b = [3,4];

const c = a.concat(b);

// or

const c = [...a , ...b];
```

##### Elm

```javascript
a = [1,2]
b = [3,4]

c = a ++ b;
```


### Comments

| JavaScript                 | Elm                        |
| -------------------------- | -------------------------- |
| `// single line comment`   | `-- single line comment`   |
| `/* multi line comment */` | `{- multi line comment -}` |

### Packages / Modules

| JavaScript     | Elm                    |
| -------------- | ---------------------- |
| `npm install`  | `elm-package install`  |
| `package.json` | `elm-package.json`     |
| `node-modules` | `elm-stuff/packages`   |


### Destructuring / Pattern Matching

| JavaScript                | Elm                  |
| ------------------------- | -------------------- |
| `let {name, age} = user;` | `{name, age} = user` |
| `({prop}) => prop`        | `\{prop} -> prop`    |

### If / Else Statements

##### JavaScript
```javascript
if (true) {
  return "foo"
} else {
  return "bar";
}
```

##### Elm

```elm
if True then "foo" else "bar"

-- or

if True then \
 "foo"
else \
 "bar"
```

## Redux vs. Elm

### Architecture

| Redux     | Elm      |
| --------- | -------- |
| `action`  | `msg`    |
| `reducer` | `update` |
| `state`   | `Model`  |

### State Updater Functions

##### Redux Reducer

```javascript
function reducer(state = 0, action) {
  switch (action.type)
    case 'INCREMENT':
      return state + 1;
    case 'DECREMENT':
      return state - 1;
    default:
      return state;
}
```

##### Elm Update

```elm

-- MODEL

type alias Model = Int

model : Model
model = 0

-- UPDATE

type Msg = Increment | Decrement

update : Msg -> Model -> Model
update msg model =
  case msg of
    Increment ->
      model + 1
      
    Decrement ->
      model - 1
```

## React vs. Elm

### Setting State

##### React

```javascript
this.setState({ counter: 0 });
```

##### Elm

```elm
{ model | counter = 0 }
```