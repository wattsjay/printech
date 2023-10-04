https://github.com/sudheerj/javascript-interview-questions
https://www.frontendinterviewhandbook.com/javascript-questions

1. ## Explain Event Delegation
- Add event listeners to a parent element instead of descendants.
- Children will fire parent listener because of event bubbling.
- Decreases memory footprint.
- No need to bind or unbind based on children addition or removal.

```
  function handleClick(event) {
    const id = event.target?.id;
    id && onClick?();
  }

  document.getElemlentById("parent")
    .addEventListener("click", handleClick)
 
  <ul id="parent">
    <li id="child-1" />
    <li id="child-2" />
    <li id="child-3" />
    <li id="child-4" />
    <li id="child-5" />
  </ul>;
```

2. ## Explain `this`

If the `new` keyword is used, it's inside the object.
```
  function Constructor() {
    console.log(this);
  }
  new Constructor();
```