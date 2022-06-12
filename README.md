- first create directory => mkdir
- After that initials the yarn modules
- yarn add -D webpack webpack-cli
  webpack => this is the library that will process our file
  webpack-cli => this is a common line interface for webpack
- src create directory => index.js
- "scripts": {"build": "webpack --mode production",} => when we run scripts webpack will process and the bundle our source code from the src directory into single file called main.js, and it will store this file in the folder called dist

- we had to add some configuration.
  these days webpack works out of the box it includes nice default for the configuration
  > > > yarn run build
- inside the dist folder create index.html > move src
  I will use the web based plugin called HTML webpack plugin => yarn add -D html-webpack-plugin
- create webpack.config.js =>
  const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
plugins: [
new HtmlWebpackPlugin({
template: "./src/index.html",
filename: "index.html",
}),
],
};

- remove script from index.html in src
  > > > yarn run build

Finally, I don't want to open this file manually every time I would like to check a change that they do to the source here. So I just add webpack-dev-server. this runs our app locally, and whenever we change a file in our project. it rebuilds our app. And we will be able to see the changes in the browser.

"scripts": {
"build": "webpack --mode production",
"start": "webpack-dev-server --open --mode development"
}

> > > yarn start
