# react-app-guidelines

> Last updated: Nov. 5th, 2018

I frequently find myself creating new React apps, both professionally for Netflix and for side projects. There's a
considerable amount of  set up that goes into building new apps, and sometimes I forget my preferences.

That's where this guide comes in. It's a list of libraries, configuration, and settings that I follow when building
React apps.

### Creating a New App

I begin new projects using [Create React App](https://github.com/facebook/create-react-app) (CRA for short), and I do
not [eject](https://facebook.github.io/create-react-app/docs/available-scripts#npm-run-eject).

Is CRA perfect? Perhaps not. Does it have all of the decisions that I would make if I created my own build system? Perhaps not.

But it works really well. Additionally, it transfers the reponsibility of managing important code to the Facebook and React
community, so that I don't need to spend time on it. Lastly, it is so widely used that it potentially lowers the onboarding cost of
new developers to apps that use it.

For me, the pros of CRA outweigh any cons.

### React Guidelines

I primarily develop using [React](https://reactjs.org/). Why React? It helps me create the user experiences that I want to build,
and rarely, if ever, gets in my way. In addition, it has an enormous community.

I have no doubt that other libraries and frameworks provide similar benefits. I just happen to know React the best right now, and so
does my team at work, which is why I choose to use it.

#### React: Strict Mode

It's always a good idea to run React in Strict Mode. Remember, it's OK if you see warnings with Strict Mode enabled. It is better to know
about the warnings than to not know.

The Strict Mode component should wrap the entire application. That way, no warnings get past you.

[Read more here](https://reactjs.org/docs/strict-mode.html)

#### React: Top-level Error Boundary

React will unmount the entire component tree if an exception occurs during rendering that isn't caught by an
[Error Boundary](https://reactjs.org/docs/error-boundaries.html).

Of course, you should do everything that you can to ensure that this does not happen. However, it is difficult, if not impossible, to be
certain that you've caught everything. Even if you have Error Boundaries throughout your application (which you should have, by the way), it
is still possible that you might miss something.

The application unmounting provides a terrible user experience: the entire app is replaced with emptiness, and the user has no idea
what happened. This must be avoided at all costs. A better user experience is to let the user know what happened, and a top-level Error Boundary
affords you that opportunity. The message that is displayed should be visually consistent with the rest of the app.

It is OK if your top-level error boundary doesn't let the user resolve the error and resume using the app. Its primary, simple goal is
to provide a better experience than the app unmounting. If you believe that your top-level Error Boundary accomplishes that goal, then it is
a good top-level Error Boundary.

I typically communicate the following pieces of information in a top-level error boundary:

1. an unexpected application error occurred
2. this is not the intended behavior of the application
3. who to contact regarding the error
4. what actions they can take right now to resolve the problem (which is refreshing the page)

> Heads up: be sure to track analytics on how frequently this Error Boundary is triggered. It is your responsibility to ensure that users never
> encounter it, and when they do, the source of the error should be fixed.

#### React: Other Error Boundaries

...

#### React Router

...

(compare against other options, like Reach Router)

#### History With Query

...

(show usage API)

#### Modals

...

[Read more about Portals](https://reactjs.org/docs/portals.html)

### JS Guidelines

#### Lodash FP

...

[Ref](https://medium.com/making-internets/why-using-chain-is-a-mistake-9bc1f80d51ba)

#### TypeScript

...

### CSS Guidelines

#### BEM

...explain why. Note to self: perhaps consider CSS Modules, since it's now built into CRA?

...also explain the why _not_ CSS-in-JS

#### Support the Notch

...

#### Small screens-first CSS

...

### UX Guidelines

#### Accessibility

...

#### Keyboard support

...Quick guide on keyboard support

### Developer Experience

#### Prettier

...Describe why, include link to CRA README guides

#### ESLint

...Contrast it with Prettier

#### TypeScript

...say why

#### Disable inline chunks

CRA default; no good for CSP

### Server

...Coming soon