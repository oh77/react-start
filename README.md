## React Start

### `React Starter Kit`

[React Starter Kit](https://www.reactstarterkit.com) is an opinionated boilerplate for web
development built on top of [Node.js](https://nodejs.org/),
[Express](http://expressjs.com/), [GraphQL](http://graphql.org/) and
[React](https://facebook.github.io/react/), containing modern web development
tools such as [Webpack](http://webpack.github.io/), [Babel](http://babeljs.io/)
and [Browsersync](http://www.browsersync.io/). Helping you to stay productive
following the best practices. A solid starting point for both professionals
and newcomers to the industry.

[Documentation](https://github.com/kriasoft/react-starter-kit/tree/master/docs)

#### Setup

> `$` git clone -o react-starter-kit -b master --single-branch https://github.com/kriasoft/react-starter-kit.git react-start<br/> > `$` cd react-start<br/> > `$` yarn (install)<br/> > `$` yarn start

### `Storybook`

Storybook is a UI development environment and playground for UI components. The tool enables users to create components independently and showcase components interactively in an isolated development environment.

Storybook runs outside of the main app so users can develop UI components in isolation without worrying about app specific dependencies and requirements.

#### Setup

> `$` npm i --save-dev @storybook/react

Add the following to `package.json`

```javascript
"scripts": {
  {
    "storybook": "start-storybook -p 9001 -c .storybook"
  }
}
```

Create a config file, name it `.storybook/config.js` and fill it:

```javascript
import { configure } from '@storybook/react';

const req = require('../stories/index.js');

function loadStories() {
  req;
  // You can require as many stories as you need.
}

configure(loadStories, module);
```

Add stories in the referenced file above, `../stories/config.js`

```javascript
import React from 'react';
import { storiesOf } from '@storybook/react';
import { Button } from '@storybook/react/demo';

storiesOf('Button', module)
  .add('with text', () => <Button>Hello Button</Button>)
  .add('with some emoji', () => (
    <Button>
      <span role="img" aria-label="so cool">
        😀 😎 👍 💯
      </span>
    </Button>
  ));
```

> `$` yarn storybook

#### Source

[Storybook for React](https://storybook.js.org/basics/guide-react/)
