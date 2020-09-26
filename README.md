# react-football-app

Create Rails app from scratch:



1. mkdir react-football-app
2. cd react-football-app
3. npm init
4. npm install required packages
	1. npm i -D babel-core babel-cli babel-preset-env babel-preset-react
	2. npm i -D webpack webpack-cli webpack-dev-server babel-loader
	3. npm i -D browser-sync browser-sync-webpack-plugin
	4. npm i -s react react-dom
	5. npm i -s axios

5. Create folders and required paths


6. .gitignore
	node_modules
	dist

7. .balelrc
	{
	  "presets": ["env", "react"]
	}

8. webpack.config.js
	
	const path = require('path');
	const webpack = require('webpack');
	const BrowserSyncPlugin = require('browser-sync-webpack-plugin');

	module.exports = {
	  entry: './src/index.js',
	  mode: 'development',
	  module: {
	    rules: [
	      {
		test: /\.(js|jsx)$/,
		exclude: /(node_modules|bower_components)/,
		loader: 'babel-loader',
		options: { presets: ['env'] },
	      },
	    ],
	  },
	  resolve: { extensions: ['*', '.js', '.jsx'] },
	  output: {
	    path: path.resolve(__dirname, 'dist/'),
	    publicPath: '/dist/',
	    filename: 'bundle.js',
	  },
	  devServer: {
	    contentBase: path.join(__dirname, 'public/'),
	    port: 3000,
	    publicPath: 'http://localhost:3000/dist/',
	    hotOnly: true,
	  },
	  plugins: [
	    new webpack.HotModuleReplacementPlugin(),
	    new BrowserSyncPlugin({
		host: 'localhost',
		port: 8080,
		proxy: 'http://localhost:3000/',
	    }),
	  ],
	};




9.other plugins
 npm i -s  react-hot-loader css-loader style-loader html-webpack-plugin 
 npm i -s @babel/core @babel/plugin-syntax-dynamic-import @babel/plugin-transform-runtime @babel/plugin-transform-async-to-generator @babel/preset-env @babel/preset-react
 npm i -s extract-text-webpack-plugin css-loader style-loader html-loader
 npm i -s extract-text-webpack-plugin
npm install extract-text-webpack-plugin@next --save-dev



to start 
webpack-dev-server 

