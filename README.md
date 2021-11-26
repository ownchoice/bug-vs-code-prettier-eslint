# prettier-eslint highlights errors but doesn't fix them: There was trouble creating the ESLint CLIEngine

**Describe the bug**

I'm working with TSX files for a Next.js project with Yarn. I'm not having this problem with other projects, even with the same Prettier and ESLint configuration files.

The `prettier` and `eslint` commands work fine with `npx` and `yarn run` in the project's directory.

VS Code highlights the errors accordingly to my `.eslintrc` rules, but doesn't fix them. When trying to format a file (Shift+Alt+F), it fails with the following message:

`Error: r is not a constructor`

And the VS Code window's log says:

`[2021-11-25 12:17:44.403] [renderer1] [error] [Extension Host] prettier-eslint [ERROR]: There was trouble creating the ESLint CLIEngine.`

It only happens in this project and I don't know how to dig deeper in the extension logs, I have no information about the bug to work with. And since both Prettier and ESLint work fine from the console, the problem's source seems to be the extension.

Deleting `node_modules` and `yarn.lock` didn't fix it. Neither did restarting VS Code or my PC.

UPDATE: the command "fix all" works! VS Code is able to fix the ESLint problems with that commands. Yet "Format document" with the prettier-eslint extension still doesn't work.

**To Reproduce**

Steps to reproduce the behavior:
1. [Download this repository](https://github.com/ownchoice/bug-vs-code-prettier-eslint).
2. Run `yarn install`
3. Run `yarn run lint`
4. Run `yarn run format:check`
5. Open the project in VS Code.
4. Open any `.tsx` file (like `pages/index.tsx`) in the editor and wait for the linting to appear.
5. Errors should be highlighted now.
6. Try to fix it with the `Format document` command in VS Code (Shift+Alt+F).
7. The Prettier ESLint extension fails.

**Expected behavior**

The Prettier ESLint extension clearly highlights the errors, so it should be able to fix them without crashing.

**Example Project**

[This repository is an example project where it happens](https://github.com/ownchoice/bug-vs-code-prettier-eslint)

**Screenshots**

![image](https://user-images.githubusercontent.com/22414323/143471012-905f924a-6b6d-4f92-9e07-aa0e2c581e9b.png)
![image](https://user-images.githubusercontent.com/22414323/143471103-7dc45251-f3bf-4675-a5d0-7ee11c3bbfdb.png)
![image](https://user-images.githubusercontent.com/22414323/143471249-6851e7eb-49f5-4ce2-ad0b-95e0c5e6f164.png)


**Versions:**
- Visual Studio Code: 1.62.3
- VS Code Node: 14.16.0
- Node installed on system: 16.9.1
- Package Manager: npm 7.20.6, yarn 1.22.11
- prettier-eslint: 3.0.4
- prettier: 2.5.0
- eslint: 8.3.0

**System Specifications:**
- OS: Windows 10 Pro 21H1
- Processor: Intel(R) Pentium(R) CPU G4560 @ 3.50GHz   3.50 GHz
- RAM Size: 8,00 GB
 
