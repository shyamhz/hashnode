---
title: "Emmet for HTML: A Beginner’s Guide to Writing Faster Markup"
datePublished: Sun Feb 01 2026 18:16:01 GMT+0000 (Coordinated Universal Time)
cuid: cml42aovd000c02le4rgz0vyl
slug: emmet
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769963286084/04c086b8-37b0-4d32-9316-ede376aebf6f.png
tags: emmet, chaiaurcode, chaicode, chaicohort, chaicode-webdev-cohort-2026, emmet-for-html-a-beginners-guide-to-writing-faster-markup

---

You cannot escape HTML but you can escape the tedious repetition of it. Didn’t get what that means? You will, shortly. If you are beginner or do not know what Emmet is you may have faced a very stingily recurring issue while writing HTML is manually writing all the nesting and deep semantic structure of your webpage.

Also if you have overall similar structure with few minor differences then changing them one by one is also a chore.  

Your editor may suggest and write the tag for you or at most change opening closing tag name but if you are tired of the repeating same opening closing tags again and again, Emmet will totally change your life and make writing HTML fun again!

## Emmet as a shortcut

To be able to visualize effectiveness of Emmet you need at least to items to make. You will understand what that means.

```xml
 h1+p
```

This means create two sibling elements. `+` is used to denote relationship as “siblings”.

```xml
<h1></h1>
<p></p>
```

There is no limit to how many siblings you can create at the same time but , whole point of Emmet was to eliminate repeatition not write `h1+h1+h1` 10 or 100 times.

For that we have very interesting shortcut with `*` symbol.

```xml
h1*5
```

This will create 5 `h1` elements as siblings

```xml
<h1></h1>
<h1></h1> 
<h1></h1> 
<h1></h1> 
<h1></h1> 
```

This can be any number.

Next thing that takes more time is nesting, you can create nested structure like below.

```xml
ul>li+li
```

Here `>` sign sets the relationship as Parent and child, left element is parent and right one is the child. You can also apply the `*` shortcut here using `(` Parenthesis `)` .

```xml
ul>(li*2)
```

This will create nested structure.

```xml
<ul>
<li></li>
<li></li>
</ul>
```

you can also add id and class, for class you add id with `#` and class with `.` .

```xml
nav#navbar
```

Above one will create `<nav id=”navbar”></nav>` .

## Conclusion

You can mix and match on how you create your elements. You can also mix match different Emmet shortcuts. There is a huge amount of possible Emmet shortcuts that cannot be mentioned in a single blog. if you are curious you can visit [Emmet Docs Cheatsheet](https://docs.emmet.io/cheat-sheet/) to read more on your own and explore and have fun.

Hopefully after this the joy of Front-end will come back to you.