# JS Guidelines

#### Lodash/Ramda

Lodash or Ramda is fine. Lodash has the benefit of a larger community, but it suffers
from its arguments being in the wrong order. Ramda resolves that issue.

Lodash FP is another option for solving the issue of arguments, but it introduces new
problems: fewer people have heard of it or used it, and its documentation is not
as readily available.

Lodash chaining is quite convenient, and I find it to be the best way to write
functional code using regular Lodash. However, it is not without its flaws. Refer
to [this post](https://medium.com/making-internets/why-using-chain-is-a-mistake-9bc1f80d51ba) for more.

That post encourages use of Lodash FP, but I would prefer Ramda for the reasons given above.

#### TypeScript

I'm new to TypeScript, so I don't have much to say about it. I'm hopeful that it will provide
benefits for projects that are intended to be maintained for long periods of time, which is why I am
interested in using it in my apps.

But I am still learning about it.
