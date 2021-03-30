# Presentation Slides

React [MDX][]-based presentation decks

- :memo: Write presentations in markdown
- :atom_symbol: Import and use [React components](#imports)
- :nail_care: Customizable [themes](#theming) and components
- :zero: Zero-config CLI
- :tipping_hand_woman: [Presenter mode](#presenter-mode)
- :notebook: [Speaker notes](#speaker-notes)

---

- [Getting Started](#getting-started)
- [Using MDX](#using-mdx)
- [Theming](#theming)
- [Components](#components)
- [Layouts](#layouts)
- [Presenter Mode](#presenter-mode)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [CLI Options](#cli-options)

## Getting Started

```sh
npm i -D mdx-deck
```

Create an [MDX][] file and separate each slide with `---`.

```mdx
# Hello

---

## This is my deck

---

## The End
```

Add a run script to your `package.json` with the MDX Deck CLI
pointing to the `.mdx` file to start the development server:

```json
"scripts": {
  "start": "mdx-deck deck.mdx"
}
```

Start the development server:

```sh
npm start
```

Use the left and right arrow keys to navigate through the presentation.

## Using MDX

MDX uses Markdown syntax and can render React components inline with JSX.

### Imports

To import components, use ES import syntax separated with empty lines between any markdown or JSX syntax.

```mdx
import { Box } from 'theme-ui';

<Box color="tomato">Hello</Box>
```

Read more about MDX syntax in the [MDX Docs][mdx].

## Theming

<div>
  <img src='docs/images/future.png' width='256' />
  <img src='docs/images/comic.png' width='256' />
  <img src='docs/images/yellow.png' width='256' />
</div>

MDX Deck uses [Theme UI][] and [Emotion][] for styling, making practically any part of the presentation themeable.
It also includes several built-in themes to change the look and feel of the presentation.

- See the list of available [Themes](docs/themes.md)
- Read more about theming in the [Theming docs](docs/theming.md).

## Components

MDX Deck includes built-in components to help with creating presentations,
a `Notes` component for adding speaker notes,
a `Head` component for the document head,
`Header` and `Footer` components for persistent header and footer content,
and a `Steps` component for adding multiple intermediate steps in a single slide.

Read more in the [Components](docs/components.md) docs.

### Third-Party Components

These optional libraries are intended for use with MDX Deck.

- [CodeSurfer][]: React component for scrolling, zooming and highlighting code.
- [mdx-code][]: Runnable code playgrounds for MDX Deck.
- [mdx-deck-live-code][]: Live React and JS coding in slides.

_Note: please check with version compatibility when using these libraries._

[codesurfer]: https://github.com/pomber/code-surfer
[mdx-code]: https://github.com/pranaygp/mdx-code
[mdx-deck-live-code]: https://github.com/JReinhold/mdx-deck-live-code

## Layouts

Each slide can include a custom layout around its content,
which can be used as a _template_ for visually differentiating slides.

```js
// example Layout.js
import React from 'react';

export default ({ children }) => (
  <div
    style={{
      width: '100vw',
      height: '100vh',
      backgroundColor: 'tomato',
    }}
  >
    {children}
  </div>
);
```

```mdx
import Layout from './Layout';

# No Layout

---

<Layout>

# Custom Layout

</Layout>
```

The layout component will wrap the MDX elements within that slide,
which means you can add custom layout styles
or style child elements with CSS-in-JS.

## Presenter Mode

Press `Option + P` to toggle _Presenter Mode_,
which will show a preview of the next slide, a timer, and speaker notes.

![presenter mode screenshot](docs/images/presenter-mode.png)

The presentation can be opened in two separate windows at the same time,
and it will stay in sync with the other window.

## Keyboard Shortcuts

| Key                                | Description                                 |
| ---------------------------------- | ------------------------------------------- |
| Left Arrow, Page Up, Shift + Space | Go to previous slide (or step in [Steps][]) |
| Right Arrow, Page Down, Space      | Go to next slide (or step in [Steps][])     |
| Option + P                         | Toggle [Presenter Mode](#presenter-mode)    |
| Option + O                         | Toggle Overview Mode                        |
| Option + G                         | Toggle Grid Mode                            |

[steps]: docs/components.md#steps

## CLI Options

```
-p --port     Dev server port
-h --host     Host the dev server listens to
--no-open     Prevent from opening in default browser
```

---

### Related

- [MDX Deck][]
- [MDX][]
- [Gatsby][]
- [Theme UI][]
- [Emotion][]
- [Spectacle][]

[MIT License](LICENSE.md)

[mdx deck]: https://github.com/jxnblk/mdx-deck
[mdx]: https://mdxjs.com/
[gatsby]: https://gatsbyjs.org
[spectacle]: https://github.com/FormidableLabs/spectacle
[emotion]: https://emotion.sh
[theme ui]: https://theme-ui.com
