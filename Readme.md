
# react-enroute

 Simple React router with a small footprint for modern browsers.

 Roughly ~1300% smaller than react-router, however this package does not attempt to be a drop-in replacement. The react-router package provides legacy browser support and transitions, so you'll want to choose accordingly!

 See [path-to-regexp](https://github.com/pillarjs/path-to-regexp) for path matching, this is the same library used by Express.

## Installation

 ```
 $ npm install react-enroute
 ```

## Size Comparison

react-enroute:

- regular: 8kb
- gzipped: 1.6kb

react-router:

- regular: 104kb
- gzipped: 21kb

## Examples

No nesting:

```js
ReactDOM.render(<Router {...state}>
  <Route path="/" component={Index} />
  <Route path="/users" component={Users} />
  <Route path="/users/:id" component={User} />
  <Route path="/pets" component={Pets} />
  <Route path="/pets/:id" component={Pet} />
  <Route path="*" component={NotFound} />
</Router>, document.querySelector('#app'))
```

Some nesting:

```js
ReactDOM.render(<Router {...state}>
  <Route path="/" component={Index} />

  <Route path="/users" component={Users}>
    <Route path=":id" component={User} />
  </Route>

  <Route path="/pets" component={Pets}>
    <Route path=":id" component={Pet} />
  </Route>

  <Route path="*" component={NotFound} />
</Router>, document.querySelector('#app'))
```

Moar nesting:

```js
ReactDOM.render(<Router {...state}>
  <Route path="/" component={Index}>
    <Route path="users" component={Users}>
      <Route path=":id" component={User} />
    </Route>

    <Route path="pets" component={Pets}>
      <Route path=":id" component={Pet} />
    </Route>
  </Route>

  <Route path="*" component={NotFound} />
</Router>, document.querySelector('#app'))
```

## Debugging

To view a list of the routes generated toggle the following:

```js
localStorage.debugRoutes = 'yep'
```

## Developing

Build:

```
$ make build
```

Start dev server:

```
$ make start
```

## Badges

![](https://img.shields.io/badge/license-MIT-blue.svg)
![](https://img.shields.io/badge/status-unstable-yellow.svg)
[![](http://apex.sh/images/badge.svg)](https://apex.sh/ping/)

---

> [tjholowaychuk.com](http://tjholowaychuk.com) &nbsp;&middot;&nbsp;
> GitHub [@tj](https://github.com/tj) &nbsp;&middot;&nbsp;
> Twitter [@tjholowaychuk](https://twitter.com/tjholowaychuk)
