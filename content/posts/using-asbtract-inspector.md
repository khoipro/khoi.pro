---
title: "Using Asbtract Inspector"
date: 2019-10-16T15:47:11+07:00
---

[Abstract](https://www.abstract.com/) is a great design tool which help designers to create a complex design. It also was helpful with a developer through "Inspector" tool.

![Abstract Menu](/img/abstract-menu.png)

Let's get started by click "Inspect" when you preview a design on Sketch.

## What do you inspect on Abstract

![Abstract Screen](/img/abstract-example.png)

**Styleguide**

* Heading text
* Paragraph text
* Button Text, with hover state
* Link Text, with hover state
* Form Input, error and success form state

**Global Modules**

Mostly a designer will supply both of mobile, tablet and desktop screens.

* Header, with mobile (slideout) menu
* Footer
* Modal/Popup
* Sticky Header state
* Newsletter section

Otherwise you could see some card hover state, etc...

## What properties do you looking for

**Typography**

It usually stores in the `typography.css` file.

```text
font-size
line-height
letter-spacing
text-transform
```

**Button**

Should be add to `buttons.css` which includes

```text
/* Using typography @mixin button-text */
font-size
line-height
letter-spacing
text-transform
/* Extra style for button */
display: inline-block;
margin
padding
/* Hover */
&:hover {}
```

**Paragraph**

It should be add to `typography.css`, usually has 3 different sizes

- Large
- Normal (usually applies to `body`)
- Small

**Form: Standard Input**

The `input` (for text, email address, phone...) should have:

```text
/* Fixed height is better than using padding only */
height
padding
```

**Form: Spacing**

The spacing between rows or between columns should be preadded using some classes

```text
.form__row {
    margin-top: 10px;

    &:first-child {
        margin-top: 0;
    }
}

.form__row--half {
    @media (--m) {
        width: 50%;
        padding: 0 10px;
    }
}
```

![Abstract - Inspect Form Elements](/img/abstract-inspect-form.png)

**Modules**

With all modules, to match *pixel-perfect*, you should take a look for some specific properties

```text
# Text
color

# Text or Other Elements
margin
padding
```

![Abstract - Inspect Spacing](/img/abstract-inspect-spacing.png)

## Best Practices

**It's all good if any module elements are linked to Styleguide elements**

For example, when you inspect this below element, it displays the name from Styleguide (**Label**).

![Abstract Inspect Text Style](/img/abstract-inspect-text-style.png)


