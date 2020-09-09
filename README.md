## Tutorial
- [Get Started with KendoReact](https://www.telerik.com/kendo-react-ui/getting-started/)
- [KendoReact Docs & Demos](https://www.telerik.com/kendo-react-ui/components/charts/get-started/)

## Git
- [Get Started with KendoReact](https://github.com/telerik/kendo-react-getting-started/)

# install & setup

## create react-app
```
\dev\training> npx create-react-app mkr --use-npm
\dev\training> cd mkr
\dev\training\mkr>npm start
```

## git repository
- create repository(remote) : https://github.com/hopelife/mkr.git
- git init(local)
```
\dev\training\mkr>git init
\dev\training\mkr>git remote add origin https://github.com/hopelife/mkr.git
```

## visual studio code
### 파일 > 작업영역에 폴더 추가 : \dev\training\mkr

### create new file
- \dev\training\mkr\.gitignore
```
# dependencies
/node_modules
/.pnp
.pnp.js

# testing
/coverage

# production
/build

# misc
.DS_Store
.env.local
.env.development.local
.env.test.local
.env.production.local

npm-debug.log*
yarn-debug.log*
yarn-error.log*
```

### edit file
- \dev\training\mkr\README.md

- src/App.js
* Remove everything inside the App container div: <div className="App"> ... </div>
* Remove the logo.svg import
* Import {Component} in addition to React
```
import React, {Component} from 'react';
import './App.css';

class App extends Component {

  render() {
    return (
      <div className="App">
        <h1>Hello KendoReact!</h1>
      </div>
    );
  }
}

export default App;
```

- Remove the contents of src/App.css

- Delete src/logo.svg

```
import React, {Component} from 'react';
import './App.css';

class App extends Component {

  render() {
    return (
      <div className="App">
        <h1>Hello KendoReact!</h1>
      </div>
    );
  }
}

export default App;
```

### Add JSON Data
Let's create some dummy data for our components.

Create a *src/categories.json* file and copy-paste [this content from GitHub](https://github.com/telerik/kendo-react-getting-started/blob/master/src/categories.json) inside.

Create a *src/products.json* file and copy-paste [this content from GitHub](https://github.com/telerik/kendo-react-getting-started/blob/master/src/products.json) inside.

Finally, import them in **src/App.js**:

```
import categories from './categories.json';
import products from './products.json';
```

### Import KendoReact Components
KendoReact is distributed as multiple NPM packages, scoped to @progress. For example, the name of the Grid package is @progress/kendo-react-grid.

KendoReact is a rich suite of many modular components. For your dashboard example, you’ll use three of these components: the Grid, the Window and the DropDownList.

1. First, let's add these components’ packages and their dependencies:

For the Grid:
```
npm install --save @progress/kendo-react-grid @progress/kendo-data-query @progress/kendo-react-inputs @progress/kendo-react-intl @progress/kendo-react-dropdowns @progress/kendo-react-dateinputs @progress/kendo-drawing @progress/kendo-react-data-tools @progress/kendo-react-animation
```
or

```
yarn add @progress/kendo-react-grid @progress/kendo-data-query @progress/kendo-react-inputs @progress/kendo-react-intl @progress/kendo-react-dropdowns @progress/kendo-react-dateinputs @progress/kendo-drawing @progress/kendo-react-data-tools @progress/kendo-react-animation
```

For the Window:
```
npm install --save @progress/kendo-react-dialogs
```
or

```
yarn add @progress/kendo-react-dialogs
```

For the DropDownList, you’re all set because you installed its package as a Grid dependency. You also installed another important package: kendo-data-query. It contains useful functions for client-side data operations.

2. Next, import the installed components into your source code. Add the following to src/App.js:

```
import { process } from '@progress/kendo-data-query';
import { Grid, GridColumn } from '@progress/kendo-react-grid';
import { DropDownList } from '@progress/kendo-react-dropdowns';
import { Window } from '@progress/kendo-react-dialogs';
```

# kendo components

## Chart

### Installation

```
npm install --save @progress/kendo-react-charts @progress/kendo-drawing @progress/kendo-react-intl hammerjs
```