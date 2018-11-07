# Creating a New App

## Create React App

I begin new projects using [Create React App](https://github.com/facebook/create-react-app) (CRA for short), and I do
not [eject](https://facebook.github.io/create-react-app/docs/available-scripts#npm-run-eject).

Is CRA perfect? Perhaps not. Does it have all of the decisions that I would make if I created my own build system? Perhaps not.

But it works really well. Additionally, it transfers the reponsibility of managing important code to the Facebook and React
community, so that I don't need to spend time on it. Lastly, it is so widely used that it potentially lowers the onboarding cost of
new developers to apps that use it.

For me, the pros of CRA outweigh any cons.

### Changes to CRA

#### Disable inline chunks

By default, Create React App inlines a small runtime script into `index.html`. This script does not have a nonce,
so it requires that you allow unsafe-inline in your JavaScript CSP. For this reason, I disable it by using the
`INLINE_RUNTIME_CHUNK` option.

You can learn more about this option on the
[Advanced Configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration) page of CRA.