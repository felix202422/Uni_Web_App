# DarCity University — Online Application System

A responsive university application portal interface styled after the official
online application systems used by universities such as UDOM: institutional
masthead, blue navigation bar, admission-window marquee, action cards, centered sign-in
card and a five-step application flow.

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
│   ├── campus.jpg
│   └── favicon.svg
└── README.md
```

## How to view

Open `index.html` in any modern web browser. No installation or server is
needed. Keep the `images` folder intact so the background image path works.

## Navigation

| From | To | Link |
| --- | --- | --- |
| index.html | register.html | Register button in the sign-in panel |
| index.html | application.html#step-personal | Sign In, after browser validation |
| register.html | index.html#login-card | Register submit / Back to login |
| application.html | application.html | Direct open shows the Sign In Required gate |
| application.html | application.html#step-academic | Step 1 Continue |
| application.html | application.html#step-programme | Step 2 Continue |
| application.html | application.html#step-review | Step 3 Continue |
| application.html | application.html#step-confirmation | Step 4 Continue |
| application.html | application.html#step-personal | Edit Step 1 |
| application.html | index.html | Cancel / Return Home |

The application is a single-page, no-JavaScript step flow. CSS `:target` shows
one step at a time, while CSS `:has()` keeps later steps locked until the
earlier required fields are complete. A locked panel appears if a later
fragment is opened early. Continue controls are fragment links, so answers stay
in the page while it is open. The home page and application page have no portal
nav links; the register page keeps only Home. Opening `application.html`
directly shows a Sign In Required gate; the demo Sign In action opens Step 1.
Register returns to the login card.

## Icons

Real icons are provided by **Font Awesome Free 6.5.2**. Source links:

- Icon browser: https://fontawesome.com/icons
- CDN details: https://cdnjs.com/libraries/font-awesome
- Stylesheet: https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css

## Implementation notes

- The admission window uses a real `<marquee>` element with continuous
  left-to-right scrolling, as requested.
- The sign-in fields have no `name` attributes, so the username, password and
  Remember Me state are not included in the URL when the form opens Step 1.
- The programme picker uses CSS `:has()` to show diploma or bachelor programmes
  after an award level is chosen, without JavaScript.
- The application uses one HTML file with a CSS-gated sign-in screen, a step
  lock and five `:target` step panels: Personal Information, Academic
  Background, Programme Selection, Review and Confirmation. Later steps and
  progress links unlock only when earlier controls satisfy their native
  `required` constraints. Opening a later fragment early shows the locked
  panel. No JavaScript, form submission or storage is involved. The gate is a
  demo navigation aid, not real authentication.
- Navigation uses fragment links, so entered values stay in the open document
  when moving between steps. They are not saved and are cleared by a reload.
  The programme radios keep `name="programme"` only for native grouping; no
  field values are placed in the address bar by the step links.
- Review and Confirmation use only `NEEDS VERIFICATION` and `MISSING` states. No
  application is submitted, no reference number is issued, and no official
  record is created in this static demo.
- The campus photograph is stored locally in `images/campus.jpg`
  (source: Unsplash) so the layout works without an internet connection.

## CSS organisation

`style.css` is divided into the 16 requested sections, from the reset and
variables through each page area, responsive rules and hover effects.
