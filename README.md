# React Component Hierarchy Viewer

This script uses a fork of [pretty-tree](https://github.com/mafintosh/pretty-tree) to build and display a visual representation of your React component hierarchy in the console. (The fork simply allows for colors of tree nodes to be depth-based)

![rch example](http://i.imgur.com/RbwB4PY.png)

## Usage

```
> rch

  Usage: rch [opts] <path/to/rootComponent>

  React component hierarchy viewer.

  Options:

    -h, --help             output usage information
    -V, --version          output the version number
    -c, --hide-containers  Hide redux container components
```

## Requirements

- One component per file
- Components can be created in any way (es6 class, functional stateless, or react.createClass)
- ..As long as they use JSX
- ES6 imports
- If you use Redux, you either wire it up by wrapping your components' export statement with Redux's connect function, or you use a separate file for your container which is formatted approximately like this:

```js
import { connect } from 'react-redux';

import SomeComponent from '../components/SomeComponent';

const SomeComponentContainer = connect(
  mapStateToProps,
  mapDispatchToProps,
)(SomeComponent);

export default SomeComponentContainer;
```
