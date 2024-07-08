# CSS-Queries
 Documentation of learning how to implement container queries

## Table of contents
* [Technologies](#technologies)
* [Setup](#setup)
* [Features](#features)
* [Sources](#sources)
* [Devlog](#devlog)
	
## Technologies
Project is created with:
* HTML
* CSS
	
## Setup
To run this project, clone repo and click index.html file.

## Features
* Here's my journey of implementation container queries in my projects.
* First I want to create test project where I can experiment.

## Sources
What helped me:
* [An Interactive Guide to CSS Container Queries](https://ishadeed.com/article/css-container-query-guide/)
* [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_containment/Container_queries)
* [Frontlive Newsletter](https://frontlive.substack.com/)

## Devlog
Here is my devlog :D

I'am fan of learning new ways to improve my work and projects. So while reading Frontlive Newsletter I found article about CSS Container Queries.\
Previously I design my projects with media queries and percents to acheive responsibility. But it append to be tricky and laggy sometimes.\
For small websites I think that can be enough - but I want to improve myself and design more efficient websites :D

Let's start by creating simple page with two blocks with text inside.\
```html
    <main>
        <article class="kenobi">Hello there</article>
        <article class="grievous">General Kenobi</article>
    </main>
```

Now we are trying to center these blocks - and we will give them some look :D\
```css
*
{
    margin: 0;
    padding: 0;
}

main
{
    /*styling*/
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
}

article
{
    /*styling*/
    display: flex;
    align-items: center;
    justify-content: center;
}
```
And now we have centered our page :D\
We should add our container query:\
```css
main
{
    /*styling*/
    container: blocks / inline-size;
}

@container blocks (min-width: 180px)
{
    article
    {
        font-size: clamp(14px, 10px + 1.33cqw, 20px);
    }
}
```

Thanks to this query we can style element by the size of container.\
Now we added query to change font size. What else we can do?

Well, for now I don't exactly know. I want to make these block in column when the size of container is small.\
And I've found what I was doing wrong:
* I should changing main ``flex-direction``, not article.