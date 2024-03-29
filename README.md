# Web - Angular/ReactJS Test Assignment

[![codecov](https://codecov.io/gh/webcat12345/liu-zhang-web/branch/main/graph/badge.svg?token=V18YWQU9AU)](https://codecov.io/gh/webcat12345/liu-zhang-web)

URL: https://webcat12345.github.io/liu-zhang-web/

The goal is to create a simple web application which makes a request to an API, parses the response, and displays the result in the UI. The app will consist of **two major components** - one **search** component and one **results** component.

## Notes from Liu Zhang

### Problem

After the investigation, I found that GitHub user search API not allowing sort by `login` at the moment, so Server-Side-Sort is actually not implemented.

The desired method is already there, in the `user.service.ts` with `TODO` comment. But all functionalities from the front end side - table, pagination, sort actions are already done.

### Additions

- [Prettier](https://prettier.io/) for the code style check and cleanup
- [Tailwind CSS](https://tailwindcss.com/) for the CSS library
- [Angular Material & CDK](https://material.angular.io) for the general UI component library
- [GitHub Pages](https://pages.github.com) for the deployment
- [Codecov](https://about.codecov.io/) for the code coverage integration and pipelines

### Git workflows

- Every push will be tested via GitHub actions passing 3 steps - build, testing, code-coverage check.
- `main` branch is connected with the server(GitHub Page), whenever you push your code to `main` branch, that will be deployed to the hosting.
- Code coverage is listed on the README.md by default, you can click this [badge](#web---angularreactjs-test-assignment) to check the report more details.
- Following the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) for commits.

### Development guideline

After clone the repository, following steps will allow you to set up the project on the local environment. 

```bash
$ # Install packages
$ npm install
$
$ # Run project and check http://localhost:4200 from your browser
$ npm start
$
$ # Run unit test (single run - capable for CI)
$ npm run test
$
$ # Run unit test to generate code coverage
$ npm run test:cov
$
$ # Build the project in production mode
$ npm run build
$
$ # Other additional scripts can be found from the package.json - script section
```

## Original Requirements

### Search Component

This component should contain two elements:

- 'Login' Text input for entering a String value
- 'Submit' Button for initiating a request to
  `https://api.github.com/search/users?q={login} in:login`, where {login} is the input value

```bash
# Example curl GET request to search for for login `foo`
curl --request GET '[https://api.github.com/search/users?q=foo in:login](https://api.github.com/search/users?q=foo%20in:login)'
```

### Results Component

This component should contain a single element:

- Results Table for displaying the results of the User search

The results table has the following requirements:

- Display three columns from the response:
    - `avatar_url`
    - `login`
    - `type`
- Use [Pagination](https://docs.github.com/en/rest/guides/traversing-with-pagination#basics-of-pagination), with **9** items displayed Per_Page
- Allow Sorting, with the `login` column being sorted by default

## UI

The UI should appear modern and simple while following best practices around HTML + CSS/SCSS. Creativity is encouraged, so feel free design the UI in any way you wish. However, the app must be functionally complete.

## Use-Case

- After the app is launched, the **Search** component is displayed
- The user enters a random String value into to the 'Login' field and clicks the 'Submit' button
- The app sends a http request to `https://api.github.com/search/users?q={login} in:login`, where {login} is the String value entered by the user
- The app then parses the response from the server. If data is returned, the **Results** component should display the fetched values. If there is an issue with the request, then an error message should be displayed.

## Requirements

- The app should be written using TypeScript, with proper static typings applied wherever possible
- The app has to compile and run without issue. It should be stable and reasonably fool-proof, handling all obvious test cases.
- The overall code quality should be excellent, with the assumption the application would be deployed to a production environment.
- The app should contain basic tests, with  >50% code coverage.

## Deliverables

- The final deliverable should be a fully-functioning Angular/ReactJS project that compiles and runs without issue.
- Your code repository should be named `{firstName}-{lastName}-web`.
- A **private** GitHub repository is the preferred delivery method for code. Please invite the following GitHub users to allow access:
    - amoonfaber
    - m8ig
    - edkhachatryan
    - newlc
    - micahjlucas
- A public URL is the preferred delivery method for the application. Feel free to use [Netlify](https://www.netlify.com/), [StackBlitz](https://stackblitz.com/), [Glitz](https://glitch.com/), or any other simple deployment mechanism.
- Please include **both** your **GitHub repository** link and the **Application URL** in your email reply to HR.
