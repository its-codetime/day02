# day02

link: https://docs.google.com/document/d/1v0lcqV9v0QAZfjEIKKc5eRDC_mEJkl4f2cH1QuiXi3c/edit?usp=sharing

- List 5 difference between Browser JS(console) v Nodejs
- watch & summary 5 points
  - https://www.youtube.com/watch?v=SmE4OwHztCc&ab_channel=JSConf
- To read
  - https://stackoverflow.com/questions/5641997/is-it-necessary-to-write-head-body-and-html-tags
- Execute the below code and write your description in txt file
  - typeof(1)
  - typeof(1.1)
  - typeof('1.1')
  - typeof(true)
  - typeof(null)
  - typeof(undefined)
  - typeof([])
  - typeof({})
  - typeof(NaN)
- Read what is prototype

# List 5 difference between Browser JS(console) v Nodejs

| Browser JS | Node Js |
|---|---|
| JavaScript is a programming language. It is running in any web browser with a proper browser engine.  	| It is an interpreter and environment for JavaScript with some specific useful libraries which JavaScript programming can use separately.  	|
| This is basically used on the client side | This is mostly used on the server side|
| Javascript can run in any browser engine as like v8 in chrome and Spider monkey in Firefox.	| V8 is the Javascript engine inside of node.js that parses and runs Javascript.  |
| Javascript is capable enough to add HTML and play with the DOM. | Nodejs does not have the capability to add HTML tags.  |
| browsers come with a gui | Nodejs doesn't. It is headless  |
| has 'window' and 'document' objects | has 'global' object|


# watch & summary
	
[link to video](https://www.youtube.com/watch?v=SmE4OwHztCc&ab_channel=JSConf)

summary:
- high level overview
  - Bindings
  - Rendering: Parsing,Layout,painting etc
  - Platform and Javascript VM
- high level flow of rendering part
  - parse HTML / parse CSS
  - render tree
  - layout
  - paint
- parsing html
	- html is forgiving by nature (close tags, add quotes to attributes etc)
	- can be halted (link, js dom updates) 
	- speculative parsing (looks ahead)
	- reentrant (means it can be interrupted)
- render tree
  - dom + cssom
  - combines two object models
  - actual representation of what shows on the screen
  - not 1-to-1 mapping of html
  - not in render tree
    - non visual elements like head, script, title etc
    - nodes hidden via "display:none"
  - DOM node to render object
    - visual output, layout and paint, holds style and computed metrics
- calculating visual properties
  - combine all styles -> defaults, external, style elements and inline styles
  - matching rules and style computation
- render
  - recursive process
  - traverse render tree
  - nodes position and size
  - layout its children
- layout
  - will batch layouts which is asynchronous
  - immediate layout
  	- font-size change or browser resize will re layout the entire html document 
    - accessing certain properties via javascript eg. 'node.offsetHeight'
- paint
  - will take the layed out render trees
  - creates layers, incremental process, builds up over 12 phases(bg, img, border etc)
  - produces a bitmap from each layer and uploaded to GPU as a texture
  - composite the textures into final image to render to the screen
- Performance insights
  - always put script at the end or use defer or async
  - do all your reads in one pass and then followed by writes
  - inline critical CSS
  
# data type

```js
console.log(typeof 1); // output : number
// 1 is of type number

console.log(typeof 1.1); // output : number
// even float numbers are of type number in javascript

console.log(typeof "1.1"); // output : string
// This is of type string as it has double quotes around it which is how strings are represented in javascript

console.log(typeof true); // output : boolean
// true or false is of type boolean

console.log(typeof null); // output : object
// null is of type object(weird?)

console.log(typeof undefined); // output : undefined
// There is a separate data type called undefined in javascript

console.log(typeof []); // output : object
// arrays are of type object in javascript

console.log(typeof {}); // output : object
// {} represents an object in javascript which is why it is of that type

console.log(typeof NaN); // output : number
// type of NaN is a number in javascript
```