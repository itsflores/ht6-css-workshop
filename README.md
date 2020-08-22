# Intro to CSS

## About us

### Omar Flores

- Software Engineer Intern at Google
- 4th year CS at Carleton University
- All things frontend
- [omarg247](https://github.com/omarg247) on GitHub
- [omarflores.dev](https://omarflores.dev) on the web

### Jason Le

- Developer (Intern) at RBC Amplify
- 3rd year CS at Carleton University
- jqwotos on [Linkedin](https://www.linkedin.com/in/jqwotos/) and [Github](https://github.com/jqwotos)

## What is CSS?

According to MDN web docs (Mozilla Developer Network):

- Cascading Style Sheets (CSS) is a stylesheet language used to describe the presentation of a document written in HTML or XML (including XML dialects such as SVG, MathML or XHTML). CSS describes how elements should be rendered on screen, on paper, in speech, or on other media.

> **TL;DR** a way to style documents, most commonly HTML and SVG

## CSS seems scary
**Queue the horror music**
- "I hate CSS" 
- "I can't center this div!"
- "I can't do CSS for my life"
- "WhAT iS CSs"

**Why does this happen?**
- Lack of true resources
- A lot of detailing
- If things aren't built properly from the beginning, you'll end up using `!important` EVERYWHERE

## Essentials 

- [x] selectors
- [x] pseudo classes
- [x] box model
- [x] sizing units
- [ ] position
- [ ] layouts
- [ ] transitions

## Selectors

- Elements vs divs vs id, what to use?
- Depends on the context

### Syntax
- `.class`
- `#id`
- `element`

**Classes**
```html
  <div class="profile-container">
    <img class="profile-picture" src="./me.png">
    <h3 class="profile-name">
      Omar
    </h3>
  </div>
```

**What can we do with **this**?**
```css
  .profile-container {
    display: flex;
    flex-orientation: column;
    padding: 16px;
  }

  .profile-picture {
    height: 64px;
    width: 64px;
    border-radius: 100%;
  }

  .profile-name {
    margin-top: 32px;
  }
```

**There is not a single way to use selectors**
### Syntax
- space -> another level in
- no space -> same element 
- comma -> different element

```html
  <div class="profile-container">
    <img src="./me.png">
    <h3>
      Omar
    </h3>
  </div>
```

```css
  .profile-container {
    display: flex;
    flex-orientation: column;
    padding: 16px;
  }

  .profile-container img {
    height: 64px;
    width: 64px;
    border-radius: 100%;
  }

  .profile-container h3 {
    margin-top: 32px;
  }
```

- SCSS
```css
  .profile-container {
    display: flex;
    flex-orienation: column;

    & img {
      height: 64px;
      width: 64px;
      border-radious: 100%;
    }

    & h3 {
      margin-top: 32px;
    }
  }
  ```

**Pseudo classes**
- `:hover`
- `:active`
- `:focus`
- `:visited`
- `:first`
- `:first-child`
- `:last-child`

**Can be combined**
- `:not(:first-child)`

```css
  .image-container img:hover {
    box-shadow: 4px 4px 12px rgba(0, 0, 0, 0.5);
  }
```

## Box model

<img src="./img/box-model.bmp" style="height: 264px; padding: 32px" />

- height & width can be either relative or static
- padding goes inwards <<
- margin goes outwards >>

## Sizing units

**%**
- Size relative to to parent element
- Usually used when parent components have a set height/width

**px**
- Pixels
- Usually the standard for all units

**rem "root element font size"**
- Size scalable to what the "root element of font size is"
- Usually set as 16px
- `em` stands for element font size, nearest font size is used

**vh, vw**
- Size relative to viewport
- Usually used in parent body, html, or main components

**Static one pager website**
```html
  <body>
    <div class="main-container">
      <div class="profile-container">
        <img>
      </div>
    </div>
  </body>
```

```css
  html, body {
    height: 100vh;
    width: 100vw;
  }

  .main-container {
    padding: 1rem;
    height: 264px;
    width: 264px;
    display: flex;
  }

  .profile-container {
    margin: auto;
    padding: 1rem;
    
  }

  .profile-image {
    height: 100%;
    width: 100%;
  }
```

## Position

**static**
- The normal position

**relative**
- Used to be able to use absolute in the children

**absolute**
- Relative to the closest parent component that has `position: relative` on it.

**fixed**
- 

**-webkit-sticky**

## Flavours of CSS

- Sass
- CSS in JS

## Layouts

### Flexbox

### Grids

#### Basics of CSS Grids

```css
.parent {
  display: grid;
}
```

**Grid Tracks**

- Grid Tracks define the **rows** and **columns** of our grid layout through the use of: `grid-template-columns`, `grid-template-rows`, and the short-hand `grid-template`.

```css
.parent {
  grid-template-columns: 1fr auto minmax(100px, 200px);
  grid-template-rows: min-content auto;
}
```

**Units of Measurement and Sizing**
- `fr`
- `minmax(<min>, <max>)`
- `auto`
- `repeat()`


**Gutters**
- Gutters help us evenly space items between rows and columns through the use of: `column-gap`, `row-gap`, and the short-hand `gap`.

#### Alignment

#### Examples

## Best practices 

- Divs, divs and more divs
  - Items should never be on their own
  - Grouping is key

- Naming is key when dealing with a lot of components

- Flexbox (and grids) is your friend

- The internet is your friend

- `!important`

- ```css
  * {
    outline: solid 1px red;
  }
  ```
