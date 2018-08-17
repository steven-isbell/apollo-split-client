# This is a Work In Progress (WIP)

# apollo-split-client

A zero config TypeScript client implementation to make http and subscriptions work with ApolloProvider.

# Usage

`apollo-split-client` is a class with a `client` property that exposes a configured ApolloProvider client. `apollo-split-client` accepts two arguments, an `httpUri` which is the path for your graphql instance, and a `wsUri` which is the path for your WebSocket instance.

### React

```javascript
// In App.js
import React, { Component } from 'react';
import ApolloSplitClient from 'apollo-split-client';

const { client } = new ApolloSplitClient('http://localhost:3000/graphql', 'ws://http://localhost:3000');

class App extends Component {
    // ...
    render() {
        return (
            <ApolloProvider client={client}>
                {/* Query, Mutation, or Subscription Code */}
            </ApolloProvider>
        )
    }
}

export default App;
```


