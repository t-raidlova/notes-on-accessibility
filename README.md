# Notes on Accessibility

## Table of Contents

1. **[Semantic HTML](#1-semantic-html)**
1. **[Focus management](#2-focus-management)**

---

## Resources

- [Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/)
- [A11y Project](https://www.a11yproject.com/)
- [ARIA](https://www.w3.org/TR/html-aria/)
- [WebAIM](https://webaim.org/)

### Courses

- [Google Web Accessibility course](https://www.udacity.com/course/web-accessibility--ud891)
- [Marcy Sutton - Start Building Accessible Web Applications Today](https://egghead.io/courses/start-building-accessible-web-applications-today)

- [Jon Kuperman - Introduction to Accessibility](https://learn-a11y.netlify.app/focus-management/index.html)
- [Tatiana T. Mac - Hacking Digital Styleguides for Accessibility](https://www.skillshare.com/classes/Hacking-Digital-Styleguides-for-Accessibility-Type-Color-Imagery/1920202818)

---

## 1. Semantic HTML

### **Accessible buttons**

#### button element with **icon**

- [visually hidden class](https://gist.github.com/t-raidlova/a3d7b7690dbc88633610312f8317e6ba)

```html
<button>
  <span class="visually-hidden">Info</span>
  <i aria-hidden="true"></i>
</button>
```

#### div element with svg

```html
<div role="button" tabindex="0">
  <svg>
    <title id="svg-title">Accessible name here</title>
  </svg>
</div>
```

## 2. Focus management

### Tab index

- **negative value** means that the element should be focusable, but should not be reachable via sequential keyboard navigation
- **0** means that the element should be focusable and reachable via sequential keyboard navigation, but its relative order is defined by the platform convention
- **positive value** means should be focusable and reachable via sequential keyboard navigation; its relative order is defined by the value of the attribute: the sequential follow the increasing number of the tabindex. If several elements share the same tabindex, their relative order follows their relative position in the document.

```html
<div tabindex="“0”">I’m focusable</div>
```

### Skip Links

[Learn more about skip links](webaim.org/techniques/skipnav/)

### How to make a skip link

- Create an anchor with the body "Skip to content"
- Prepend it to the body of your website
- Make it visually hidden
- Give it a focus state which makes it visible
