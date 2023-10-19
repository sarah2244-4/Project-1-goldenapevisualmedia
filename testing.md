# Testing

## Contents

- Responsivity
- Browser Compatibility
- User Stories

## Responsivity 

Responsivity was testing using chrome developer tools. 

| Tests for all pages | iPhone SE | Pixel 5 | Samsung Galazy S8+ | iPad Air | Surface Pro 7 | Nest Hub | Desktop |
| --- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | 
| Responsive | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Navbar toggle button | Yes | Yes | Yes | N/A | N/A | N/A | N/A |
| Full Navbar | N/A | N/A | N/A | Yes | Yes | Yes | Yes |
| Hero text fits on screen | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Links open correctly | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Form does not submit with invalid information | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Form submission works correctly | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| All images are seen | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Good sizing of gallery images | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| Contact form autofocuses | Yes | Yes | Yes | Yes | Yes | Yes | Yes |
| All footer information appears on screen | Yes | Yes | Yes | Yes | Yes | Yes | Yes |

## Browser compatibility

| Tests for all pages | Chrome | Firefox | Edge | Opera |
| --- | :---: | :---: | :---: | :---: |
| Loads as expected | Yes | 
| Responsive | Yes | 


## Testing User Stories

### Bugs

Below 284 px the navbar toggler moves below the logo. 

### Resolved bugs

Every time I added a background overlay to the header image it covered the buttons too. If I changed the brightness of the image it also changed the brightness of the buttons. I could not find a workaround so in the end I removed the overlay and used contrasting white text and buttons on a dark image. 

The profile image took a lot of work. To start with it was cropped but I wanted the full image. To fix it I found the code
```
object-fit: scale-down;
```
on W3schools.

I then couldn't get the image into the right place. With a lot of trial and error, I managed to fix it by changing the height and the width of the image form px to % with the code
```
width: 100%;
height: 55vh;
```

Once I had made the image responsive for a small screen, it was off-center and I finally managed to fix it by adding the code
```
display: block;
```

As I used a textarea from Bootstrap with a responsive number of columns, the input was a different style to the rest of the form. I found the CSS used to style inputs on and finally changed the border radius, border and box shadow so they all matched.

Once deployed Bootstrap, css stylesheets and images were not linked correctly. After some searching, I hadn't included all of the correct Bootstrap links and I changed some of my link paths to link the css and images correctly. The header image still wouldn't show up no matter how many different file paths I did, but it turned out because I had replaced my file with a smaller file but kept the name, I needed to retype out the file again. I found this out by changing it to a different picture and then changing it back again. 

### Unresolved Bugs

- When submitting an invalid form, the required messages don't appear below the input fields that need completing. I couldn't find any fix without removing all formatting for the form. However, the message still comes up if the mouse hovers over the inputs and the page scrolls up to the input with the problem. I decided to also add red borders to invalid fields as a visual cue the inputs weren't complete. 

## Validating

I used the [W3 Validator](https://validator.w3.org/) to validate my code. 

Initial issues were: 

- The 404 and thank you pages contained extra body tags. 
- The modals contained example aria-lablledby values so I changed these to aria-label. The validator still comes up with a warning that these labels have been misused, however there is no text in the modals so I kept this as it was. 

All pages have been run through the validator and all files pass. 

![W3C Validator message](assets/images/w3validator.JPG)

## Lighthouse Testing

![Initial lighthouse test](assets/images/testing/lighthouse-initial-test.JPG)

Initial testing found issues with:

- For performance images massively impacted load time. I then changed the image sizes to .WebP and resized them. 
- The SEO had issues with a missing description in the head, which I added in. 
- Accessibility showed that ARIA IDs were not unique. I was unsure how to recifty this as it came from the Bootstrap navbar. 
- Also the footer headings had skipped heading order to h5 so I changed these to h2 and resized them in the style.css file. 

Once everything had been fixed I tested the pages with Lighthouse again. 

### Results of lighthouse testing

#### About Page

#### Gallery Page

#### Contact Page

#### Thank You Page

#### 404 Error Page