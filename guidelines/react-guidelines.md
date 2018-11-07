# React Guidelines

I primarily develop using [React](https://reactjs.org/). Why React? It helps me create the user experiences that I want to build,
and rarely, if ever, gets in my way. In addition, it has an enormous community.

I have no doubt that other libraries and frameworks provide similar benefits. I just happen to know React the best right now, and so
does my team at work, which is why I choose to use it.

## Strict Mode

It's always a good idea to run React in Strict Mode. Remember, it's OK if you see warnings with Strict Mode enabled. It is better to know
about the warnings than to not know.

The Strict Mode component should wrap the entire application. That way, no warnings get past you.

As of Nov. 6, 2018, two important libraries still have errors in Strict Mode:

- React Router
- React Redux

Luckily, the prerelease versions of both of these libraries have the warnings removed.

[Read more about Strict Mode here](https://reactjs.org/docs/strict-mode.html)

## Top-level Error Boundary

React will unmount the entire component tree if an exception occurs during rendering that isn't caught by an
[Error Boundary](https://reactjs.org/docs/error-boundaries.html).

Of course, you should do everything that you can to ensure that this does not happen. However, it is difficult, if not impossible, to be
certain that you've caught everything. Even if you have Error Boundaries throughout your application (which you should have, by the way), it
is still possible that you might miss something.

The whole application unmounting provides a terrible user experience: the entire app is replaced with emptiness, and the user has
no indication of what has happened. It's important to ensure that this never happens. A better user experience is to let the user know what happened,
and a top-level Error Boundary provides you with that opportunity. The message that is displayed should be visually consistent with the rest of the app.

It is OK if your top-level error boundary doesn't let the user resolve the error and resume using the app. Its primary, simple goal is
to provide a better experience than the app completely unmounting.

I typically communicate the following pieces of information in a top-level error boundary:

1. an unexpected application error occurred
2. this is not the intended behavior of the application
3. who to contact regarding the error
4. what action the user can take right now to resolve the problem (which is typically refreshing the page)

> Heads up: be sure to track analytics on how frequently this Error Boundary is triggered. That way, you can see how often it
> occurs and prioritize fixing those problems!

## Error Boundaries

Aside from a top-level error boundary, individual "pieces" of your application should have an error boundary. For instance, if your
application has a side panel, then you might want to put an error boundary within that panel.

More granular error boundaries lets you scope errors to individual parts of your app, so that it doesn't bring down the whole
app. One of the benefits of this approach is that you can usually provide a better experience to the user. Another benefit is
that, if you track analytics for each error boundary individually, you can get a sense of what sections of your app are the most
stable.

## React Router

React Router is the de facto routing solution for React, and I believe that it's a fine solution for apps of all sizes. It lets
me build the user experiences that I want, and it rarely gets in my way.

Is it perfect? Perhaps not. But this is another situation where I believe that the pros outweigh any cons that there may be.

[React Router GitHub Repository](https://github.com/ReactTraining/react-router)

## History With Query

React Router doesn't provide a nice API for working with query parameters. Although this may initially seem like an annoying
omission, I think that is is appropriate given the different requirements that applications have when it comes to serializing
and deserializing query strings.

Luckily, it's possible to extend the history API with improved support for query strings. I prefer to use the library
[qhistory](https://github.com/pshrmn/qhistory).

> Note: I tend to copy and paste the code into my applications, rather than installing another npm dependency.

## Modals

Modals should be placed in a Portal. There should be a single root for all of the modals in an application.

[Read more about Portals](https://reactjs.org/docs/portals.html)