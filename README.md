# ByteKnight - HTML and CSS Profile Card

## Table of contents


- [Introduction](#introduction)
- [Final Result](#final-result)
- [Creating Profile Card Component](#creating-profile-card-component)
  - [What are profile card?](#what-are-profile-card)
  - [Let's start building](#lets-start-building)
- [Conclusion](#conclusion)


## Introduction
Card components are very common in modern user interface designs and they are visible everywhere. It is a versatile and indispensable tool for presenting information and content in an engaging and visually appealing manner. In this article, we get familier with card components and learn how we can build a good looking card components by building a profile card component.

## Final Result
![Final Profile Card Component](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ck15rbg1uwi09f9m86ry.png)
- **This is how It looks in the end If you want to try. You can get starter file and final code in this [GitHub repo](url)**

## Creating Profile Card Component
### What are profile card?
Profile cards are UI components used to display information about about an individual in a concise and visually appealing manner. Generally, a profile card includes a profile picture, a name, job title, location, contact information, skills. There may also be a brief bio. Keeping all this in mind we will build our profile card.

### Let's start building
#### First step, let's create a html document containing above mentioned details
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="icon" type="image/x-icon" href="./assets/images/favicon.ico"/>
    <link rel="stylesheet" href="./style/style.css">
    <title>profile-card</title>
</head>
<body>
    <main class="profile-card">
        <img class="profile-pic" src="./assets/images/profile-pic.png">
        <div class="details">
        <h1 class="name">
            Whiskers Whiskerton
        </h1>

        <div class="location"><img src="./assets/images/location-dot-solid.svg"/><span >NEW YORK</span></div>
        <p class="description">
            UI/UX designer and front-end developer
        </p>
        <div class="button">
            <button class="message-button">Message</button>
            <button class="follow-button following">Follow</button>
        </div>
        <div class="skills">
            <h2>SKILLS</h2>
            <ul class="skills-list">
            <li>UI/UX</li>
            <li>Front End Development</li>
            <li>HTML</li>
            <li>CSS</li>
            <li>Javascript</li>
            <li>React</li>
            <li>Bootstap</li>
        </ul>
        </div>
    </div>
    </main>
</body>
</html>
```


- `<main>` contains all the details and this will be our card. 
- I have already added css file in `<head>`.
- I have also defined class name for styling.

#### Now we deal with styling which is the most important part in this

- **Removing default styles:**
```css
/* GLOBAL */

* {
    margin: 0;
    padding: 0;
}
```
- **Choosing a appropriate color scheme:**
  - This will depends on brand color. Then you can choose complementing colors. 
  - Brand colour is your primary colour, this will be morw visible color. That does not mean it will be used more in design but it means it will be used where you want your user to focus on.
  - Here that will be our card component and buttons.
```css
/* COLORS */
:root {
    /* primary */
    --brand-color: rgb(42, 38, 95);
    --button: rgb(29, 24, 107);
    /* neutral */
    --dark: rgb(20, 16, 68);
    --light: rgb(238, 237, 253);
    --light-grey: rgb(211, 211, 245);
    --background-blue: rgb(113, 117, 218);
}
```
- **Defining the Stucture and Layout:**
  - Card should have a rectangular shape.
  - Generally, it has fixed width and height.
  - Defining the position of the card. Here since there is only on card it should be place at center.

```css
body {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
}

.profile-card {
    width: 350px;
    padding: 3rem 0rem 0rem 0rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
    border-radius: 14px;
    background-color: var(--light);
}
```
- **Use compelling typograpy:**
  - we use `font-face` to add that,
```css
/* FONTS */

@font-face {
    font-family: 'Roboto';
    src: url(../assets/fonts/Roboto-Regular.ttf);
    font-weight: 400;
}

@font-face {
    font-family: 'Roboto';
    src: url(../assets/fonts/Roboto-Bold.ttf);
    font-weight: 700;
}
body {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Roboto';
    font-weight: 400;
    font-size: 0.9rem;
    color: var(--light-grey);
    background-color: var(--background-blue);
}
```

- **Styling all other element, while styling keep these points in mind**
  - keep corner round, roundness may vary, it make it look soft(use border-radius).
  - vary `font-size` and `font-weight` such that it make hierarchy visible.
```css
.profile-pic {
    padding: 5px;
    width: 160px;
    border-radius: 90px;
    filter: brightness(70%);
    border: 3px solid var(--brand-color)
}


.details {
    padding: 1rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    background-color: var(--brand-color);
    border-radius: 0px 0px 14px 14px;
}

.name {
    font-size: 1.3rem;
    font-weight: 700;
    color: white;
    margin-bottom: 20px;
}

.location {
    display: flex;
    align-items: center;
    gap: 10px;
}

.location img {
    height: 1rem;
    filter: invert();
}

.button {
    width: 70%;
    display: flex;
    justify-content: space-around;
}

.button button {
    width: 100px;
    padding: 0.8rem 1.2rem;
    border: none;
    background-color: var(--dark);
    color: var(--light);
    border-radius: 5px;
}


.skills {
    margin-top: 30px 0px;
    padding: 1rem 0rem;
    border-top: 2px solid var(--dark);
}

.skills h2 {
    padding: 0.3rem 1rem;
    font-size: 1rem;
    font-weight: 700;
    color: white;
}

.skills-list {
    list-style: none;
    margin: 0px;
    padding: 0px;
}

.skills-list li {
    cursor: pointer;
    padding: 0.1rem 1rem;
    margin: 2px 0px;
    font-size: 0.8rem;
    border-radius: .4rem;
    display: inline-block;
    color: var(--light);
}
```

- **Adding shadow:**
  - adding shadow using box-shadow add 3d effect, it give depth to element. It create huge difference.

- **Interation and responsive:**
  - adding effects on hover for interaction
  - for responsiveness there is not much to do in this project

```css
.skills-list li:hover {
    transform: translateY(-5px);
    color: var(--dark);
    background-color: var(--background-blue);
}

.button button:hover {
    transform: translateY(-3px);
    color: white;
    background-color: var(--button);
}
.profile-pic:hover {
    transform: translateY(-5px);
    filter: brightness(100%);
}
```

![Profile Card Componet after all these changes](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ehc7hfdaqvp41godtc5w.png)

**Final CSS code**
```css
/* GLOBAL */

* {
    margin: 0;
    padding: 0;
}


/* FONTS */

@font-face {
    font-family: 'Roboto';
    src: url(../assets/fonts/Roboto-Regular.ttf);
    font-weight: 400;
}

@font-face {
    font-family: 'Roboto';
    src: url(../assets/fonts/Roboto-Bold.ttf);
    font-weight: 700;
}

/* COLORS */
:root {
    /* primary */
    --brand-color: rgb(42, 38, 95);
    --button: rgb(29, 24, 107);
    /* neutral */
    --dark: rgb(20, 16, 68);
    --light: rgb(238, 237, 253);
    --light-grey: rgb(211, 211, 245);
    --background-blue: rgb(113, 117, 218);
}


body {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: 'Roboto';
    font-weight: 400;
    font-size: 0.9rem;
    color: var(--light-grey);
    background-color: var(--background-blue);
}

.profile-card {
    width: 350px;
    padding: 3rem 0rem 0rem 0rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
    border-radius: 14px;
    background-color: var(--light);
    box-shadow: 0px 3px 8px var(--dark);
}

.profile-pic {
    padding: 5px;
    width: 160px;
    border-radius: 90px;
    filter: brightness(70%);
    border: 3px solid var(--brand-color)
}

.profile-pic:hover {
    transform: translateY(-5px);
    filter: brightness(100%);
}

.details {
    padding: 1rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    background-color: var(--brand-color);
    border-radius: 0px 0px 14px 14px;
}

.name {
    font-size: 1.3rem;
    font-weight: 700;
    color: white;
    margin-bottom: 20px;
}

.location {
    display: flex;
    align-items: center;
    gap: 10px;
}

.location img {
    height: 1rem;
    filter: invert();
}

.button {
    width: 70%;
    display: flex;
    justify-content: space-around;
}

.button button {
    width: 100px;
    padding: 0.8rem 1.2rem;
    border: none;
    background-color: var(--dark);
    color: var(--light);
    border-radius: 5px;
    box-shadow: 0px 1px 3px 0px black;
}

.button button:hover {
    transform: translateY(-3px);
    color: white;
    background-color: var(--button);
}

.skills {
    margin-top: 30px 0px;
    padding: 1rem 0rem;
    border-top: 2px solid var(--dark);
}

.skills h2 {
    padding: 0.3rem 1rem;
    font-size: 1rem;
    font-weight: 700;
    color: white;
}

.skills-list {
    list-style: none;
    margin: 0px;
    padding: 0px;
}

.skills-list li {
    cursor: pointer;
    padding: 0.1rem 1rem;
    margin: 2px 0px;
    font-size: 0.8rem;
    border-radius: .4rem;
    display: inline-block;
    color: var(--light);
}

.skills-list li:hover {
    transform: translateY(-5px);
    color: var(--dark);
    background-color: var(--background-blue);
}
```
**Final Card Component**
![Final Profile Card Component](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ck15rbg1uwi09f9m86ry.png)

## Conclusion
This the process I follow while building most the components. If you keep all the points in article you are good to go. Try building more and more projects. Practice is only way to get these right.

I practice from [fontendmentor](https://www.frontendmentor.io). You can give it a try.
