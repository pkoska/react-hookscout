## React Hookscout Router

The modern alternative to react-router.

Tested from `React 16.8.1` upwards.

## How to install
Well, this is straightforward:

    npm i react-hookscout

## Documentation
Detailed documentation about how to use the Rosetta router can be [found here](https://github.com/pkoska/react-hookscout/blob/master/src-docs/pages/en/README.md)

## A quick example
```jsx harmony
import {useRoutes} from 'react-hookscout';

const routes = {
    '/': () => <HomePage />,
    '/about': () => <AboutPage />,
    '/products': () => <ProductOverview />,
    '/products/:id': ({id}) => <ProductDetails id={id} />
};
	
const MyApp = () => {
    const routeResult = useRoutes(routes);
    
    return routeResult || <NotFoundPage />;
}
```
Routes are defined as an object. Keys are the routes, which are matched
against the URL, the values need to be functions that are called when a route
matches. You may define placeholders in your routes with `:something` which
will be forwarded as props to your function calls so you can distribute them
to your components.

The hook will return whatever the route function returned, so you may also return
strings, arrays, React fragments, null - whatever you like.
