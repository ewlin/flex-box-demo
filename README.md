## Flexbox Demo 

The goal of this demo is to partially re-create the layout and functionality of the Slack native app. 

In `new.html`, you'll notice that the `<body>` is tagged with a class of 'flex'. The `<body>` of our HTML doc
will serve as our main Flexbox container. 

The important thing to notice here is: 
```html
<body class="flex">
....
</body>
```

```css  
.flex {
    display: flex;
    flex-direction: row;
}
```

Since `<body>` has a `class="flex"` on it, in the corresponding css file, you can 
select the `<body>` with `.flex` and set up our outer flexbox. To do that, recall
that all you need is to declare `display: flex`. 

**Note**: I called the class 'flex'. You can call it whatever you want. Best practice is 
to use a word/compound-word that describes what you are trying to style, or how you're 
trying to style, so you don't get confused. But for the computer/your browser, it doesn't care if 
you call your flexbox `class="superman"`. 

I also added a `flex-direction: row`, but this is redundant. The default direction of flex is horizontal. 

Now that my `<body>` is a flexbox, all child elements inside `<body>` are **flex items**. This includes
the two `<aside>`s and `<main>`. Each flex item will behave in certain ways. 

The most important pieces of css for the flex items to note are: 
```css  
.flex .menu {
    flex: 0 0 100px;
    /*.....*/
}

.flex .channels {
    flex: 0 0 200px;
    /*.....*/
}

.flex main {
    flex: auto;
    /*.....*/
}    
```

The `flex: ...` part tells the flex item how to behave when the window is resized. 
The first number is the flex-grow and the second number is flex-shrink. A zero for either turns off 
the growing and shrinking behavior, so a 0 on both tells the browser NOT to resized the item
when the window is resized. The width (since we're in horizontal--or column--layout) stays the same. 
The starting width is indicated by the third number--or the `flex-basis`. In this case, 
the menu (with all the icons) is set to `100px` while the channels column is set to `200px`. 
Since both grow and shrink are set to 0, the two columns will never change width. 

Here's a [great tutorial](https://medium.freecodecamp.com/understanding-flexbox-everything-you-need-to-know-b4013d4dc9af?imm_mid=0ec5a5) on Flexbox, though be warned, it's very detailed and meant for a developer audience.  
