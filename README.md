### To-Do-List

## Building a To-Do List.

1. Create a repo and clone it.

2. Setup webpack environment:

   1. `npm init -y` to _inintialize npm_.
   2. `npm install webpack webpack-cli --save-dev`, to install webpack locally, and install the webpack-cli (the tool used to run webpack on the command line).
   3. Creating **src**, **dist** and **index.html**. (Also create appropriate folders in _src_ for css, js, and other **assets**)
   4. Add `"private": true,` to _package.json_.
   5. Creage **webpack.config.js** and add:

      ```
      const path = require('path');

      module.exports = {
          entry: './src/index.js',
          output: {
              filename: 'main.js',
              path: path.resolve(__dirname, 'dist'),
          },
      };
      ```

   6. `npm install --save-dev html-webpack-plugin`, to install the **HtmlWebpackPlugin** plugin, and add:
      ```
        plugins: [
          new HtmlWebpackPlugin({
          title: 'Output Management',
          }),
      ],
      ```
   7. `clean: true,`, in _output_ in _webpack.config.js_.

   8. `mode: 'development',` in _module.exports_, _webpack.config.js_, to set development mode.
   9. `npm install --save-dev webpack-dev-server`, to install _webpack-dev-server_.
   10. In _module.exports_, _webpack.config.js_, add:
       ```
        devServer: {
            static: './dist',
        },
        ```
        and, 
        ```
        optimization: {
            runtimeChunk: 'single',
        },
        ```
        to tell the _webpack dev server_ to *serve* the files from the _dist directory_ on _localhost:8080_.

    11. `"watch": "webpack --watch"` and `"start": "webpack serve --open",`, to add a script to easily run the dev server as well, in _scripts_, _package.json_.

    **Running _npm start_ from the command line will automatically load up our page** 

