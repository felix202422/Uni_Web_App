# Massachusetts Institute of Technology — Online Application System

A responsive university application portal interface styled after the official
online application systems used by universities such as UDOM: institutional
masthead, blue navigation bar, admission-window marquee, action cards, centered sign-in
card and official-looking form sections.

**Motto:** Your Academic Journey Starts Here.

## Technologies

- HTML5
- Plain CSS3
- Bootstrap 5.3.3 CSS only (grid, form controls and utilities; no Bootstrap JavaScript)
- Font Awesome Free 6.5.2 (icons)
- Google Fonts (Inter)

No JavaScript, frameworks, backend, database or APIs are used. The campus image
is stored locally; fonts and icons load from their CDNs when online.

## Folder structure

```text
UniApply/
├── index.html
├── register.html
├── application.html
├── style.css
├── images/
│   └── campus.jpg
└── README.md
```

## How to view

Open `index.html` in any modern web browser. No installation or server is
needed. Keep the `images` folder intact so the background image path works.

## Navigation

| From | To | Link |
| --- | --- | --- |
| index.html | register.html | Register button in the sign-in panel |
| index.html | application.html | Sign In |
| register.html | index.html | Home / Back to login |
| application.html | index.html | Submit Application |

The shared navigation bar connects the main pages. Register is available from the sign-in panel on the home page.

## Icons

Real icons are provided by **Font Awesome Free 6.5.2**. Source links:

- Icon browser: https://fontawesome.com/icons
- CDN details: https://cdnjs.com/libraries/font-awesome
- Stylesheet: https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css

## Implementation notes

- The admission window uses a real `<marquee>` element with continuous
  left-to-right scrolling, as requested.
- The password field has no `name` attribute, so it is never included in the URL
  when the sign-in form navigates.
- The programme picker uses CSS `:has()` to show diploma or bachelor programmes
  after an award level is chosen, without JavaScript.
- The campus photograph is stored locally in `images/campus.jpg`
  (source: Unsplash) so the layout works without an internet connection.

## CSS organisation

`style.css` is divided into the 16 requested sections, from the reset and
variables through each page area, responsive rules and hover effects.
