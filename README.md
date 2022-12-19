Inspired by John [Refer John's starter here](https://github.com/john-smilga/default-starter)

- DEV SERVER - When working with HTML CSS we can use `Preview on Web Server` to spinup live server. To run the server use, `CTRL+SHIFT+L`

### Normalize CSS

- Small CSS file that provides cross-browser consistency in default styling of HTML elements.

- Normalize won't provide box-sizing so add it to your css

```css
* {
  box-sizing: border-box;
}
```

- Take a look at [Docs](https://necolas.github.io/normalize.css/)
- Select the latest version
- Create `normalize.css` file
- Setup this link in HTML. This link should be put before all other css we define

`<link rel="stylesheet" href="normalize.css" />`

### Fonts

Picking the right fonts to our projects is always a pain. We have 2 step process

- Pick the fonts
- Set line height and other default styles

Two most popular font resources are

- [fontpair](https://www.fontpair.co/)
- [pagecloud](https://www.pagecloud.com/blog/best-google-fonts-pairings)

Once we have decided the fonts then we can use **typescale** site

### Grab some default CSS

- [typescale](https://type-scale.com/)
  - Here we select heading and body fonts and see how it looks.
  - Once we are happy with these fonts then we can click on `Grab the CSS` and get the CSS and paste in our css file

### Change some defaults to the above grabbed CSS

- once we grab the css from here, then add some css variables to make it reusable

- Add a bit more margin to <p> and set max-width (around 45em) so that it will nicely wrap into 2 or 3 lines consuming less space instead of being one long line taking up all the row

- I don't like margin tops so we can remove them and instead have margin bottoms, and also set text-transform to capitalize

### Colors

- We need to choose the primary and/or secondary color. For this we can use [coolers](https://coolors.co/)

- Now we also need different shades of the picked color. For this we can use [shadow colors](https://noeldelgado.github.io/shadowlord/#1e5a81) and select the color and 20%. This 20% will divide shades into 10 colors.

- So first, in coolers, I pick a color I like and add it as `--primary-500`. Then on shadow color, we get the shades for this and name as `--primary-100` through `--primary-900`

- For doing the same in a faster approach, you can use either [tailwind](https://tailwindcss.com/docs/customizing-colors#color-palette-reference) OR [bootstrap](https://getbootstrap.com/docs/5.0/customize/color/#color-sass-maps) to save some time on picking colors as you can copy directly from here.

- I would set up gray color shades similarly using tailwind or bootstrap. Once done, I can set background color of body to lightest gray and color to darkest gray.

- The other resource for colors is [happyhues](https://www.happyhues.co/). This is awesome as you can visually see how the site looks like with different color palette. **This is the best palette I liked so far**.

### Shadows

- We can use [tailwind](https://tailwindcss.com/docs/box-shadow). This has shadow small to xl. We will grab these shadows and use on cards or images. Small shadows can be applied on cards and when hovered, large ones can be applied.

### Images

- When we grab an image from any site like [Pexels](https://www.pexels.com/search/computer/), the image will have its own width and height
- One good way to control image's width and height is by having it relative to it's parent. We can give the image a `img` class and then set it's width to 100%. This would set the image width (also height by default, we don't have to set height) to its parent
- We can then set width to parent and image automatically scales well accordingly

**Example**

```html
<div class="container">
  <img src="./computer.jpg" alt="computer" class="img" />
</div>
```

```css
.container {
  width: 50vw;
  border: 5px solid var(--primary-500);
  border-radius: var(--borderRadius);
  max-width: var(
    --maxWidth
  ); /*so the container is still good in big screen and not too much wider*/
}

.img {
  width: 100%; /*depends on parent .container*/
  display: block; /*without this we might get a strange empty space at the bottom */
  object-fit: cover; /*image won't be distorted if height is set on image or parent*/
}
```

### Buttons

These are some of the button defaults to begin with.

```css
.btn {
  cursor: pointer;
  color: var(--white);
  background: var(--primary-500);
  border: transparent;
  border-radius: var(--borderRadius);
  letter-spacing: var(--letterSpacing);
  text-transform: capitalize;
  padding: 0.375rem 0.75rem;
  box-shadow: var(--shadow-1);
  transition: var(--transition);
  display: inline-block; /*note that we do this inline-block so we can place it where we want in a column
  An alternate option would be to do `display:block` add width and add margin: 0 auto
  */
}

.btn:hover {
  background-color: var(--primary-700);
  box-shadow: var(--shadow-3);
}
```

## Summary of resources

- **Base**

  - [Normalize](https://necolas.github.io/normalize.css/) - apply normalize css

- **Fonts**

  - [fontpair](https://www.fontpair.co/) OR [pagecloud](https://www.pagecloud.com/blog/best-google-fonts-pairings) - Pick a heading and paragraph font
  - [typescale](https://type-scale.com/) - Grab default CSS for above chosen fonts

- **Colors**

  - [coolers](https://coolors.co/) - Pick primary and secondary colors
  - [shadow colors](https://noeldelgado.github.io/shadowlord/#1e5a81) - Get shades for the above chosen colors
  - [tailwind](https://tailwindcss.com/docs/customizing-colors#color-palette-reference) OR [bootstrap](https://getbootstrap.com/docs/5.0/customize/color/#color-sass-maps) - For fast access of the above shades
  - [happyhues](https://www.happyhues.co/) - See the website first, get a feel for it and then choose those colors unlike above shades approach

- **Box Shadows**

  - [tailwind](https://tailwindcss.com/docs/box-shadow) - grab small to large shadows and we can show large shadows when hovered
