# Example Rush Monorepo

This template is part of the documentation of the [Rush](https://rushjs.io/) tool.
It contains documented templates for all the standard Rush configuration files.
It also includes three barebones projects that illustrate some dependency
relationships in a Rush repo:

- **apps/my-app**: The web application
- **libraries/my-controls**: A control library used by the application
- **tools/my-toolchain**: A NodeJS build tool used to compile the other projects

(These projects are NOT meant to provide a realistic toolchain.)


# Building this repo

To build the projects in this repo, try these shell commands:

```
npm install -g @microsoft/rush
rush install
rush build
```

For more information, see the documentation at:  https://rushjs.io/


# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.


# Adding in Next.Js app
1. `cd apps && pnpm create next-app`
2. `cd ../../ && rush install` You don't have to cd back to the top level to run any rush command but I did to just make sure I knew where I was.
3. I got the error `The shrinkwrap file is out of date. You need to run "rush update".` so my next step was `rush update`
4. I got the error `ERROR  eslint-config-next > @typescript-eslint/parser > @typescript-eslint/typescript-estree: tsutils@3.21.0 requires a peer of typescript@>=2.8.0 || >= 3.2.0-dev || >= 3.3.0-dev || >= 3.4.0-dev || >= 3.5.0-dev || >= 3.6.0-dev || >= 3.6.0-beta || >= 3.7.0-dev || >= 3.7.0-beta but none was installed` so then I did `cd apps/next-app && pnpm install typescript && cd ../../ && rush update`
5. `rush build` or `rush build --to next-app` to specifically run the next-app created