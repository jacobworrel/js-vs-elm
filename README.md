# js-vs-elm
Side-by-side mappings comparing JavaScript and Elm. For basic syntax, check out the [official Elm documentation](http://elm-lang.org/docs/from-javascript).

#### Packages / Modules

| JavaScript     | Elm                    |
| -------------- | ---------------------- |
| `npm install`  | `elm-package install`  |
| `package.json` | `elm-package.json`     |
| `node-modules` | `elm-stuff/packages`   |

#### Comments

| JavaScript                 | Elm                        |
| -------------------------- | -------------------------- |
| `// single line comment`   | `-- single line comment`   |
| `/* multi line comment */` | `{- multi line comment -}` |

#### Destructuring / Pattern Matching

| JavaScript                | Elm                  |
| ------------------------- | -------------------- |
| `let {name, age} = user;` | `{name, age} = user` |
| `({prop}) => prop`        | `\{prop} -> prop`    |

#### If / Else Statements

* ##### JavaScript
```
if (true) {
  return "foo"
} else {
  return "bar";
}
```

* ##### Elm

```
if True then "foo" else "bar"

-- or

if True then \
 "foo"
else \
 "bar"
```
