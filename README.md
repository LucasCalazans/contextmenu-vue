# vue

> Contextmenu component made with vue.js

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

## Usage

``` html
<!-- call the context-menu component -->
<context-menu></context-menu>

<!-- put some context-menu-item inside, they may have any content, for example, a image and a text -->
<context-menu>
	<context-menu-item>New register</context-menu-item>
	<context-menu-item>
		<img src="../assets/new.png">
		New register
	</context-menu-item>
	<context-menu-item>Remove</context-menu-item>
	<context-menu-item>Edit</context-menu-item>
</context-menu>
```