# github-scraper

"Scrapes" data from github, like private and public repositories, profiles, commits, etc... It will do this once per hour by default, store the values, and add that information to express's `req.github_data` object.

This is a JavaScript module, created for use with NodeJS and the [express](https://github.com/expressjs/express) module.

## TODO
 - [ ] code comments / jdoc
 - [ ] allow other usernames
 - [ ] access private repositories
 - [ ] access profile data
 - [ ] access commit data
 - [ ] allow public GitLab accounts

## Usage
```js
const GitHubScraper = require("./modules/github-scraper/github-scraper");
const express = require("express");

let app = express();

app.use(GitHubScraper({ username: "ThomasvanBommel" }));

app.all("*", (req, res) => {
  console.log(req.github_data);
});
```
