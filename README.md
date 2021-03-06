# React Components for Alfresco

This project originally started out as a simple React client project bootstrapped with [Create React App](https://github.com/facebookincubator/create-react-app) (the original README can now be found in the Wiki) but it has now morphed into an experiement in creating re-usable Components for rapid development of custom React clients for Alfresco.

## TL;DR
To get this up and running you will need:
* An Alfresco Repository with the V1 REST APIs (e.g. 5.2 Community) running on localhost:8080
* Node.js (>= version 6) installed
* NPM (>= version 3) installed

Then...

1. Clone or fork this Repository
2. Change to the root of the project
3. Run `npm install`
4. Run `npm start`

A browser should open at http://localhost:3000 and you'll then be able to log into the application.

## Where to Start
The index.js file is the root of the application and defines a react-router that defines the entire application. If you want to build a new "route" then simply create a new React component and add it as a new route within the `MainLayout` component. To create a link to your new route you should add it to the list of links in the `Drawer` in `MainLayout`.

The idea is that you can compose the application by simply implementing a `render()` function that returns a hierarchy of nested components, like this:

``` JSX
render() {
   return (
      <Content>
         <Collection skipCount={0}
                     maxItems={10}
                     orderBy="firstName"
                     orderDirection="DESC">
            <CreateUserButton/>
            <Filter />
            <UserTableView />
         </Collection>

      </Content>
   );
}
```

You can mix and match HTML and React components and any component should be nestable within any other component (however some are clearly designed to be nested in a specific hierarchy).

If you need to add a component (very likely) then raise an issue with the use-case or simply add it and reference it.

## Documentation
I'm starting to document the components using [JSDoc](https://github.com/jsdoc3/jsdoc). To build documentation locally you can run:

```
npm run generate-docs
```

Then you can open the `docs/index.html` file in a browser to explore what has been documented so far (**please note that not all components are currently documented**). Please let me know if you spot any mistakes or have any suggestions.


## What's Next?
At the present time this project is simply and experiment to investigate a potential approach for building applications. None of the components will be stable and are subject to change. If this experiment meets with positive feedback then I will look to publish the Components as an NPM package to be consumed in other React applications.

If you have any feedback (good or bad) or if you'd like to contribute then please let me know!


