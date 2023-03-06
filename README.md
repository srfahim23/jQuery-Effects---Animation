# jQuery-Effects---Animation
With jQuery, you can create custom animations.

# jQuery Animations - The animate() Method
The jQuery animate() method is used to create custom animations.

Syntax:

    $(selector).animate({params},speed,callback);

The required params parameter defines the CSS properties to be animated.

The optional speed parameter specifies the duration of the effect. It can take the following values: "slow", "fast", or miliseconds.

The optional callback parameter is a fuction to be executed after the animation completes.

The following example demonstrates a simple use of the animate() method; it moves a <div> element to the right, until it has reached a left propery of 250px:

    $("button").click(function(){
        $("div").animate({left: '250px'});
    });

Note: By default, all HTML elements have a static position, and cannot moved, To manipulate the position, remember to first set the CSS position property of the element to relative, fixed, or absolute!

# jQuery animate() - Manipulate Multiple Properties
Notice that multiple properites can be animated at the same time:

Example

    $("button").click(function(){
        $("div").animate({
            left: '250px',
            opacity: '0.5',
            height: '150px',
            width: '150px'
        });
    });

# It is possible to manipulate ALL CSS properties with the animate() method?
Yes, almost! However, there is one important thing to remember: all property names must be camel-case when used with the animate() method: You will need to write paddingLeft instead of padding-left, marginRight instead of margin-right, and so on.

Also, color animation is not included in the core jQuery library.If you want to animate color, you need to download the Color Animation pugin from jQuery.com.

# jQuery animate() - Using Relative Values
It is also possible to define relative values (the value is then reletive to the element's current value). Ths is done by putting += or -= in front of the value:

Example

    $("button").click(function(){
        $("div").animate({
            left: '250px',
            height: '+=150px',
            width: '+=150px'
        });
    });

# jQuery animate() - Using Pre-defined values
You can even specify a property's animation value as "slow", "hide", or "toggle":

Example

    $("button").click(function(){
        $("div").animate({
            height: 'toggle'
        });
    });

# jQuery animate() - Uses Queue Functionality
By default, jQuery comes with queue functionality for animations.

This means that if you write multiple animate() callas after each other, jQuery creates an "internal" queue with these method call. Then it runs the animate calls ONE by ONE.

So, if you want to perform different animations after each other, we take advantage of the queue functionality:

Example1

    $("button").click(function({
        var div = $("div");
        div.animate({height: '300px', opacity: '0.4'}, "slow");
        div.animate({width: '300px', opacity: '0.8'}, "slow");
        div.animate({height: '100px', opacity: 0.4'}, "slow");
        div.animate({widht: '100px", opacity: '0.8'}, "slow");
    }));

The example below first moves the <div> element to the right, and then increses the font size of the text:

Example2

    $("button").click(function(){
        var div = $("div");
        div.animate({left: '100px'}, "slow");
        div.animate({fontSize: '3rem'}, "slow");
    });

    