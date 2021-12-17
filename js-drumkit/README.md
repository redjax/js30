# js-drumkit recap

## Overview
A webpage with homerow keys (besides ;), which correspond to a sound (listed on the button). When a user presses a homerow key, JavaScript animates the button on the page by adding/removing CSS classes, using the keypress's [key code](https://keycode.info) as a selector for `<div data-key=keypress>` and `<audio data-key=keypress>`.

Term/Defition: [data attributes](https://www.w3schools.com/tags/att_data-.asp)
    
    The data-* attribute is used to store custom data private to the page or application.

    The data-* attribute gives us the ability to embed custom data attributes on all HTML elements.

    The stored (custom) data can then be used in the page's JavaScript to create a more engaging user experience (without any Ajax calls or server-side database queries).

    The data-* attribute consist of two parts:

    The attribute name should not contain any uppercase letters, and must be at least one character long after the prefix "data-"
    The attribute value can be any string
    Note: Custom attributes prefixed with "data-" will be completely ignored by the user agent.



*Example:*
    "a" key = keycode "65"
    
    "65" will be used to select div (and add/remove class .playing)
      | <div data-key="65" class="key">
  
    "65" will be used to select audio tag (and playSound(audio))
    - <audio data-key="65" src="sounds/clap.wav">

## New JavaScript I learned

**Substitution in JavaScript**
    
    Snippet: 
    const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);

    Backtick ` allows for string substitution. audio[data-key=""] finds a tag with a data-key element matching the keycode.
    
    The keycode is substituted into the data-key quotes by evaluating it. Surround the eval in double quotes. "${evaluation}"

    In this example, "e" is a value passed into the playSound() function. To get the value of e and substitute it into the querySelector for data-key="", surround the expression in quotes, and use JavaScript's variable substitution syntax: "${substring}" (note again: don't forget the backticks. i.e. document.querySelector(`...`) )

*I'm lazy and it's late, and I totally promise to come back and fill in notes for the following....... promise. Any day now. Oh and I'll delete this.*
* querySelector()/querySelectorAll()
  * select elements matching value, i.e. select all elements with .key CSS class in tag:
    * document.querySelectorAll('.key');
* window.addEventListener() - event listeners
  * Listen for keydown (keypress) and run the playSound function
* if(!audio) return;
  * Flow control, exit the function if no tags match keypress code
* key.classList.add('playing')
  * Add CSS class .playing to 'key' constant
* this.classList.remove('playing');
  * Remove .playing CSS class from arg passed to function ('e')