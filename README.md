# js-vs-elm
Side-by-side mappings comparing JavaScript / Redux / React vs. Elm.
This is intended to elaborate on the [official Elm documentation](http://elm-lang.org/docs/from-javascript)
so make sure you check that out first if you haven't already.

#### Operators

| JavaScript | Elm   |
| ---------- | ----- |
| `===`      | `==`   |
| `!==`      | `\=`  |
| `<`        | `<`   |
| `<=`       | `<=`  |
| `>`        | `>`   |
| `>=`       | `>=`  |

#### Comments

| JavaScript                 | Elm                        |
| -------------------------- | -------------------------- |
| `// single line comment`   | `-- single line comment`   |
| `/* multi line comment */` | `{- multi line comment -}` |

#### Packages / Modules

| JavaScript     | Elm                    |
| -------------- | ---------------------- |
| `npm install`  | `elm-package install`  |
| `package.json` | `elm-package.json`     |
| `node-modules` | `elm-stuff/packages`   |


#### Destructuring / Pattern Matching

| JavaScript                | Elm                  |
| ------------------------- | -------------------- |
| `let {name, age} = user;` | `{name, age} = user` |
| `({prop}) => prop`        | `\{prop} -> prop`    |

#### If / Else Statements

* ##### JavaScript
```javascript
if (true) {
  return "foo"
} else {
  return "bar";
}
```

* ##### Elm

```elm
if True then "foo" else "bar"

-- or

if True then \
 "foo"
else \
 "bar"
```

##### Redux vs. Elm

| Redux     | Elm      |
| --------- | -------- |
| `action`  | `msg`    |
| `reducer` | `update` |
| `state`   | `Model`  |

* ##### Redux Reducer Function

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

* ##### Elm Update Function

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

##### React vs. Elm

* ##### Toggling a boolean flag in React

```javascript
this.setState({ isLoading: !this.state.isLoading });
```

* ##### Toggling a boolean flag in Elm

```elm
{ model | isLoading = not model.isLoading }
```