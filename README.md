# This is a Work In Progress (WIP)

# apollo-split-client

A simple TypeScript client implementation that enables Subscriptions alongside your Queries and Mutations when using Apollo's ApolloProvider.

# Usage

`apollo-split-client` is a package with a `client` property that exposes a configured ApolloProvider client. `apollo-split-client` accepts two arguments, an `httpUri` which is the path for your Queries and Mutations, and an optional `wsUri` which is the path for your WebSocket instance for Subscriptions.

You can use `apollo-split-client` to easily use Subscriptions within React Apollo. Alternatively, you can omit the WebSocket location and use `apollo-split-client` as an http only module.

### React

```javascript
// In App.js
import React, { Component } from 'react';
import ApolloSplitClient from 'apollo-split-client';

// Enabled with Subscription Support through a WebSocket
const { client } = new ApolloSplitClient('http://localhost:3000/graphql', 'ws://localhost:3000');

// Enabled as http-only
const { client } = new ApolloSplitClient('http://localhost:3000/graphql');

class App extends Component {
    // ...
    render() {
        return (
            <ApolloProvider client={client}>
                {/* Query, Mutation, or Subscription Modules */}
            </ApolloProvider>
        )
    }
}

export default App;
```


