---
property: value
---
#meta




# ==Zen for SilverBullet== Theme
> **_A theme for SilverBullet inspired by [Zen](https://zen-browser.app/). Design philosophy: Calm, reduced visual noise and consistency._**

**Features**
- Highly polished experience throughout Silverbullet
- Improved standard components (e.g. search, pickers)
- Line highlighting in code and frontmatter
- Row highlighting in tables
- Easy-to-see Markdown formatting markers
- Matching code syntax highlighting
- Non-jumping heading indicators
- Wider pages for easier editing
- Dark & light mode
- Easy color switching

**PS** [Let me know](https://github.com/mschmidtkorth/silverbullet-zen?tab=readme-ov-file) about commonly used plugins and I will add optional sections to include them.

==[GitHub Repository](https://github.com/mschmidtkorth/silverbullet-zen?tab=readme-ov-file)==










# Theme Foundation
## CSS Variables & Design System
```space-style
/* priority: 1000 */

/*  @import statements require priority: 1000 (see https://community.silverbullet.md/t/how-to-use-css-import-s-properly-on-using-the-new-space-style-priorities/2484) */
/*@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@300;400;600&display=swap');*/
@import url('https://fonts.googleapis.com/css2?family=Antonio:wght@100..700&family=Inter:wght@300;400;600&family=IBM+Plex+Mono:wght@100;200;300;400;500;600&family=Open+Sans:wght@300;400;600&family=Roboto:wght@300;400;600&display=swap');

:root, html, body {
  /* Main font */
  --editor-font: 'Inter', 'Roboto', -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Open Sans', 'Oxygen', 'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue', sans-serif;

  /* Zen browser brand colors */
  --zen-accent: 247, 111, 83;
  --zen-purple: #8B5CF6;
  --zen-dark-bg: #1F1F1F;
  --zen-darker-bg: 28, 28, 28;
  --zen-card-bg: #363636;
  --zen-hover-bg: #26262C;
  --zen-border: #32343B;
  --zen-text: #E8E8E8;
  --zen-text-secondary: #8F8F9D;
  --zen-text-tertiary: #6E6E7A;
  --selected-bg: var(--zen-dark-bg);
  --selected-text: #D1CFC0;

  /* UI accent colors */
  --ui-accent-color: rgba(var(--zen-accent));
  --ui-accent-text-color: rgba(var(--zen-accent));
  --ui-accent-contrast-color: #fff;
  --highlight-color: rgba(94, 106, 210, 0.3);
  --link-color: rgb(var(--zen-accent));
  --link-missing-color: #F59E0B;
  --meta-color: var(--zen-purple);
  --meta-subtle-color: var(--zen-text-tertiary);
  --subtle-color: var(--zen-text-secondary);
  --subtle-background-color: rgba(143, 143, 157, 0.1);

  /* Root styles */
  --root-background-color: var(--zen-dark-bg);
  --root-color: var(--zen-text);

  /* Top bar */
  --top-color: var(--zen-text);
  --top-background-color: var(--zen-darker-bg);
  --top-border-color: var(--zen-border);
  --top-sync-error-color: #F59E0B;
  --top-sync-error-background-color: rgba(245, 158, 11, 0.1);
  --top-saved-color: var(--zen-text);
  --top-unsaved-color: var(--zen-text-secondary);
  --top-loading-color: var(--zen-text-tertiary);

  /* Panels */
  --panel-background-color: var(--zen-darker-bg);
  --panel-border-color: var(--zen-border);
  --editor-widget-background-color: var(--zen-card-bg);

  /* BHS (Bottom/Horizontal/Side panels) */
  --bhs-background-color: var(--zen-darker-bg);
  --bhs-border-color: var(--zen-border);

  /* Modals */
  --modal-color: var(--zen-text);
  --modal-background-color: var(--zen-card-bg);
  --modal-border-color: var(--zen-border);
  --modal-header-label-color: rgba(var(--zen-accent));
  --modal-help-background-color: var(--zen-card-bg);
  --modal-help-color: var(--zen-text-secondary);
  --modal-selected-option-background-color: rgba(var(--zen-accent));
  --modal-selected-option-color: #fff;
  --modal-hint-background-color: rgba(var(--zen-accent));
  --modal-hint-color: #fff;
  --modal-hint-inactive-background-color: var(--zen-hover-bg);
  --modal-hint-inactive-color: var(--zen-text-secondary);
  --modal-description-color: var(--zen-text-tertiary);

  /* Notifications */
  --notifications-background-color: var(--zen-card-bg);
  --notifications-border-color: var(--zen-border);
  --notification-info-background-color: rgba(38, 181, 206, 0.1);
  --notification-error-background-color: rgba(239, 68, 68, 0.1);

  /* Buttons */
  --button-background-color: var(--zen-card-bg);
  --button-hover-background-color: var(--zen-hover-bg);
  --button-color: var(--zen-text);
  --button-border-color: var(--zen-border);
  --primary-button-background-color: rgba(var(--zen-accent));
  --primary-button-hover-background-color: #4C57C0;
  --primary-button-color: #fff;
  --primary-button-border-color: transparent;

  /* Text fields */
  --text-field-background-color: var(--zen-card-bg);

  /* Progress indicators */
  --progress-background-color: var(--zen-darker-bg);
  --progress-sync-color: rgba(var(--zen-accent));
  --progress-index-color: var(--zen-purple);

  /* Action buttons */
  --action-button-background-color: transparent;
  --action-button-color: var(--zen-text-secondary);
  --action-button-hover-color: var(--zen-text);
  --action-button-active-color: rgba(var(--zen-accent));

  /* Editor colors */
  --editor-meta-color: rgb(var(--zen-accent)) !important; /* ``` and --- */
  --editor-caret-color: rgba(var(--zen-accent));
    /* Linear
  --editor-selection-background-color: rgba(94, 106, 210, 0.2); */
  --editor-selection-background-color: rgba(var(--zen-accent), 0.2);
  --editor-panels-bottom-color: var(--zen-text);
  --editor-panels-bottom-background-color: var(--zen-darker-bg);
  --editor-panels-bottom-border-color: var(--zen-border);
  --editor-completion-detail-color: var(--zen-text-secondary);
  --editor-completion-detail-selected-color: var(--zen-text);
  --editor-list-bullet-color: var(--selected-text);
  --editor-heading-color: var(--zen-text);
  --editor-heading-meta-color: var(--zen-text-tertiary);
  --editor-hashtag-background-color: rgba(94, 106, 210, 0.15);
  --editor-hashtag-color: rgba(var(--zen-accent));
  --editor-hashtag-border-color: transparent;
  --editor-ruler-color: var(--zen-border);
  --editor-naked-url-color: var(--link-color);
  --editor-code-color: rgb(var(--zen-accent));
  --editor-link-color: var(--link-color);
  --editor-link-url-color: var(--link-color);
  --editor-link-meta-color: var(--zen-text-tertiary);
/* Linear
  --editor-wiki-link-page-background-color: rgba(38, 181, 206, 0.1); */
    --editor-wiki-link-page-background-color: rgba(var(--zen-accent), 0.1);
  /* Linear
  --editor-wiki-link-page-color: rgba( var(--zen-accent), 0.2); */
    --editor-wiki-link-page-color: rgba( var(--zen-accent), 0.8);
  --editor-wiki-link-page-missing-color: var(--link-missing-color);
  --editor-wiki-link-color: var(--zen-text-secondary);
  --editor-command-button-color: var(--zen-text);
  --editor-command-button-background-color: var(--zen-card-bg);
  --editor-command-button-hover-background-color: var(--zen-hover-bg);
  --editor-command-button-meta-color: var(--zen-text-tertiary);
  --editor-blockquote-background-color: rgba(143, 143, 157, 0.05);
  --editor-blockquote-border-color: var(--zen-border);
  --editor-code-background-color: #262624;
  --editor-code-border-color: var(--zen-border);
  --editor-inline-code-background-color: var(--zen-card-bg);
  --editor-inline-code-color: rgb(var(--zen-accent));
  --editor-checkbox-color: var(--zen-text-secondary);
  --editor-checkbox-checked-color: rgba(var(--zen-accent));
  --editor-directive-color: var(--zen-purple);
  --editor-command-button-hint-color: var(--zen-text-tertiary);
  --editor-embed-background-color: var(--zen-card-bg);
  --editor-embed-border-color: var(--zen-border);
  --editor-table-head-background-color: var(--zen-card-bg);
  --editor-table-head-color: var(--zen-text);
  --editor-table-even-background-color: var(--zen-darker-bg);
  --editor-table-odd-background-color: transparent;
  --editor-table-border-color: var(--zen-border);
  --editor-image-border-color: var(--zen-border);
  --editor-image-background-color: var(--zen-darker-bg);
  --editor-heading-1-color: var(--zen-text);
  --editor-heading-2-color: var(--zen-text);
  --editor-heading-3-color: var(--zen-text);
  --editor-heading-4-color: var(--zen-text);
  --editor-list-number-color: var(--zen-text-tertiary);
  --editor-admonition-background-color: var(--zen-card-bg);
  --editor-admonition-border-color: var(--zen-border);
  --editor-code-comment-color: var(--zen-text-tertiary);
  --editor-code-keyword-color: var(--zen-purple);
  --editor-code-string-color: #10B981;
  --editor-code-delimiter-color: var(--zen-text-secondary);
  --editor-code-operator-color: rgb(var(--zen-accent));
  --editor-code-variable-color: var(--zen-text);
  --editor-code-punctuation-color: var(--zen-text-secondary);
  --editor-code-number-color: #F59E0B;
  --editor-code-atom-color: rgba(var(--zen-accent));
  --editor-code-meta-color: var(--zen-text-tertiary);
  --editor-code-builtin-color: var(--zen-purple);
  --editor-code-type-color: rgb(var(--zen-accent));
  --code-background-color: var(--zen-card-bg);
  --code-border-color: var(--zen-border);
  --code-copy-background-color: var(--zen-hover-bg);
  --code-copy-color: var(--zen-text-secondary);
  --code-copy-hover-background-color: rgba(var(--zen-accent));
  --code-copy-hover-color: #fff;

  /* Widget colors */
  --widget-background-color: var(--zen-card-bg);
  --widget-border-color: var(--zen-border);
  --widget-code-background-color: var(--zen-darker-bg);
  --widget-code-copy-background-color: var(--zen-hover-bg);
  --widget-code-copy-hover-background-color: rgba(var(--zen-accent));
  --widget-code-copy-hover-color: #fff;
  --widget-code-copy-color: var(--zen-text-secondary);

  /* Tables */
  --table-head-background-color: var(--zen-card-bg);
  --table-head-color: var(--zen-text);
  --table-even-background-color: rgba(28, 28, 33, 0.3);
  --table-odd-background-color: transparent;
  --table-border-color: var(--zen-border);
}

:root {
  --zen-dark-bg: #1F1F1F;
}

/* TODO To be implemented */
html[data-theme="light"] {
  --zen-dark-bg: #FFF;
}
```
## Global Styles
```space-style
/* General typography and smoothing */
body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

/* Enable ligatures */
* {
  /* letter-spacing: -0.015em; */
  font-variant-ligatures: discretionary-ligatures;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

/* Smooth transitions */
* {
  transition: background-color 0.15s ease, border-color 0.15s ease, color 0.15s ease;
}

/* Focus states */
:focus-visible {
  outline: 2px solid rgba(var(--zen-accent));
  outline-offset: 2px;
}

/* Selection */
::selection, .sb-line-fenced-code .cm-line::selection {
  background-color: rgba(var(--zen-accent), 30);
}

/* Code selection */
/* Individual spans overlap, careful with translucent color */
.sb-line-fenced-code.cm-line *::selection {
  background-color: #F76F5350 !important;
}

/* Rounded corners for common components */
.cm-panel,
.modal,
.notification,
button,
input,
.action-button,
.command-button {
  border-radius: 8px;
}

/* Shadows */
.cm-tooltip {
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.3);
}

/* Panel styling */
.panel {
  backdrop-filter: blur(8px);
  background-color: rgba(22, 22, 26, 0.9);
}


```
## Scrollbars
```space-style
*, html, body {
  scrollbar-width: thin !important;
  scrollbar-color: var(--selected-text) transparent !important;
}

::-webkit-scrollbar {
  width: 12px;
  height: 12px;
}

::-webkit-scrollbar-track {
  background: transparent !important;
}

::-webkit-scrollbar-thumb {
  background: var(--selected-text) !important; /* Changed to solid */
  border-radius: 6px;
  /* Removed the border for consistency */
}

::-webkit-scrollbar-thumb:hover {
  background: var(--selected-text) !important;
  opacity: 0.8; /* Optional: add some hover feedback */
}
```
# Layout & Navigation
## Page Layout
```space-style
html {
  --editor-width: 1024px !important; /* Wider page */
}

#sb-root {
  background: var(--zen-dark-bg);
}

/* Gap between top bar and content */
.cm-content.cm-lineWrapping {
  margin-top: 2em !important;
}
```
## Top Bar
**Example:** The top bar contains the page title, sync status, and action buttons.
![[Examples/Example_TopBar.png]]

---

```space-style
#sb-top {
  border: none;
  opacity: 0.5;
  transition: opacity 0.3s;
  backdrop-filter: blur(8px);

  &:hover {
    opacity: 1;
  }

  &,
  & > .main > .inner {
    background-color: var(--zen-dark-bg) !important;
  }

  .main {
    .inner {
      .sb-actions button {
        &:hover {
          background: var(--zen-hover-bg) !important;
        }
      }
    }

    /* Page title styling */
    #sb-current-page {
      .cm-scroller,
      .cm-content {
        /* Typography */
        font-family: "Antonio", sans-serif !important;
        font-optical-sizing: auto;
        font-weight: 400;
        font-style: normal;
        font-size: 1em !important;
        line-height: 1em !important;

        /* Positioning */
        margin-top: 4px !important;
      }

      /* Page title color */
      > div > div > div.cm-scroller > div > div {
        color: lch(64.894% 2.106 272.695 / 1) !important;
      }
    }
  }
}

/* Icons */
svg {
  color: lch(64.894% 2.106 272.695 / 1) !important;

  &:hover,
  .sb-actions.hamburger button:hover & {
    color: rgb(var(--zen-accent)) !important;
  }
}
```
## Saving Indicator
**Example:** Visual feedback when the page is being saved.
![[Examples/Example_Saving.png|120]]

---

```space-style
/* Flash page title when saving.
From: https://github.com/MatthiasBenaets/silverbullet-library/blob/master/Styles/saving.md */
@keyframes saving {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0.1;
  }
}

.sb-unsaved {
  animation: saving 3s infinite;

  .cm-line {
    &::after {
      /* Icon */
      content: url('data:image/svg+xml,<svg class="" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="rgb(187,194,207)" viewBox="0 0 24 24"> <path fill-rule="evenodd" d="M5 3a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V7.414A2 2 0 0 0 20.414 6L18 3.586A2 2 0 0 0 16.586 3H5Zm3 11a1 1 0 0 1 1-1h6a1 1 0 0 1 1 1v6H8v-6Zm1-7V5h6v2a1 1 0 0 1-1 1h-4a1 1 0 0 1-1-1Z" clip-rule="evenodd"/> <path fill-rule="evenodd" d="M14 17h-4v-2h4v2Z" clip-rule="evenodd"/> </svg>');

      /* Positioning */
      margin-left: 10px;
    }
  }
}
```
# Content Typography
## Headings
**Examples:**
# H1 Heading
## H2 Heading
### H3 Heading
#### H4 Heading
##### H5 Heading
###### H6 Heading
---

```space-style
.sb-h1, .sb-h2, .sb-h3, .sb-h4, .sb-h5, .sb-h6,
.sb-line-h1, .sb-line-h2, .sb-line-h3, .sb-line-h4, .sb-line-h5, .sb-line-h6,
h1, h2, h3, h4, h5, h6 {
  /* Typography */
  font-family: 'Antonio', sans-serif !important;
  font-weight: normal !important;
  font-variant-ligatures: none; /* Avoid strange letter spacing */
  color: var(--selected-text) !important;
}

.sb-line-h1, .sb-line-h2, .sb-line-h3, .sb-line-h4, .sb-line-h5, .sb-line-h6 {
  span.sb-meta {
    color: rgba(var(--zen-accent)) !important
  }
}

.sb-line-h1, .sb-line-h2, .sb-line-h3, .sb-line-h4, .sb-line-h5, .sb-line-h6 {
/* Spacing */
  margin: 1rem 0 1rem -1rem;
}

.sb-line-h1:before, .sb-line-h2:before, .sb-line-h3:before, .sb-line-h4:before, .sb-line-h5:before, .sb-line-h6:before {
  color: rgb(var(--zen-accent));
}

/* Heading prefixes */
.sb-line-h1:before {
  content: "> ";
}

.sb-line-h1:focus:before {
  content: "" !important;
}

.sb-line-h2:before {
  content: ">> ";
}

.sb-line-h3:before {
  content: ">>> ";
}

.sb-line-h4:before {
  content: ">>>> ";
}

.sb-line-h5:before {
  content: ">>>>> ";
}

.sb-line-h6:before {
  content: ">>>>>> ";
}

/* Editing line */
#sb-main .cm-editor .sb-header-inside {
  &.sb-line-h2.cm-line {
    /*margin-left: -1em !important;*/
  }
  .sb-h2.sb-meta {
  /*margin-left: 0em;*/

    }
  /* Headings jump due to # appearing. Can be adjusted to only have the text jump by setting to 0, but creates awkward UX as the cursor is moving. Therefore, keep it stable by shifting to the left to balance # shifting to the right */
  &.sb-line-h1 {
     text-indent: -0.15ch !important;
  }
  &.sb-line-h2 {
     text-indent: -0.3ch !important;
  }
  &.sb-line-h3 {
     text-indent: -0.45ch !important;
  }
  &.sb-line-h4 {
     text-indent: -0.56ch !important;
  }
  &.sb-line-h5 {
     text-indent: -0.73ch !important;
  }
  &.sb-line-h6 {
     text-indent: -0.88ch !important;
  }
  &.sb-line-h1:before, &.sb-line-h2:before, &.sb-line-h3:before, &.sb-line-h4:before, &.sb-line-h5:before, &.sb-line-h6:before {
    content: ''
  }
}
```
## Lists
**Examples:**
- Unordered list item
  - Nested item
    - Deeply nested item

1. Ordered list item
   2. Nested ordered item
      3. Deeply nested ordered item

---

```space-style
.sb-list.sb-task {
  margin-left: 1em; /* Gap to icon, consistent for multiline */
}
```
## Links
**Examples:**
- [[Internal Page Link]]
- [[Non-Existing Page]]
- [External link](https://example.com)

---

```space-style
/* Links */
a {
  text-decoration: none;
  border-bottom: 1px solid transparent;
  transition: border-color 0.15s ease;

  &:hover {
    border-bottom-color: var(--link-color);
  }
}
```
## Blockquotes
**Example:**
> This is a wonderful quote.

---

```space-style
#sb-main .cm-editor .sb-blockquote-outside {
  /* Styling */
  border-left: 2px solid rgba(var(--zen-accent));
  border-top-right-radius: 10px;
  border-bottom-right-radius: 10px;

  /* Spacing */
  padding: 1em;
  text-indent: 0.5ch;
  margin-top: 0.5em;
  margin-bottom: 0.5em;
}
```
## Horizontal Rules
**Example:**

---

```space-style
hr, .sb-line-hr {
  /* Styling */
  border-width: 2px;
  border-color: var(--selected-text) !important;
  border-radius: 2px;

  /* Spacing */
  padding: 0.5em 0 !important;
  max-width: 95%;
  margin: 20px auto;
}
```
# Code & Syntax
## Inline Code
**Example:** Use `inline code` for small code snippets.

---

```space-style
/* Calm style */
span.sb-code {
  /* Styling */
  background: var(--zen-card-bg) !important;
  border: 1px solid #555;
  border-radius: 4px;
  color: var(--selected-text);

  /* Typography */
  font-family: IBM Plex Mono !important;
  font-size: 0.8em !important;

  /* Spacing */
  padding: 2px 4px;
}
```
## Code Blocks
**Example:** Incl. HighlightJS syntax
```javascript
function example() {
  console.log("Hello, SilverBullet!");
}
```

---

```space-style
/* Font for code blocks */
.sb-line-fenced-code {
  font-family: IBM Plex Mono !important;
  font-size: 0.8em !important;
}

.sb-line-code-outside.sb-line-fenced-code.cm-line .sb-code-info,
.sb-line-code-outside.sb-line-fenced-code.cm-line .sb-actions button svg,
.sb-line-fenced-code.cm-line .sb-actions button  {
  color: var(--selected-text) !important;

  svg {
    color: var(--selected-text) !important;
  }

  &:hover {
    opacity: 0.8;
  }
}

/* Code block styling */
div.sb-line-fenced-code {
  /* Spacing */
  padding-left: 0.5em !important;
  padding-right: 0.5em !important;

  /* Border */
  border: 1px solid transparent;
  line-height: 1.39; /* Make up for added border */

  &:hover {
    background: var(--zen-card) !important;
    border-top: 1px solid var(--selected-text);
    border-bottom: 1px solid var(--selected-text);
  }
}

/* Rounded borders */
/* First line with button */
.sb-line-fenced-code:has(.sb-actions) {
  border-top-left-radius: 8px;
  border-top-right-radius: 8px;
}

/* Last line with ``` */
.sb-line-fenced-code:has(.sb-meta):not(:has(.sb-actions)) {
  border-bottom-left-radius: 8px;
  border-bottom-right-radius: 8px;
}

/* Code syntax colors */
.sb-line-fenced-code .cm-line .sb-meta,
.sb-code-info,
.sb-meta {
  color: rgb(var(--zen-accent));
}
```
## HighlightJS Syntax
```space-style
.sb-line-fenced-code {
  &.cm-line {
    color: var(--selected-text) !important;
  }

  /* Headings */
  .sb-h1, .sb-h2, .sb-h3 {
    color: rgb(var(--zen-accent));
    font-weight: bold;
  }

  .sb-h1 { font-size: 1.8em; }
  .sb-h2 { font-size: 1.5em; }
  .sb-h3 { font-size: 1.2em; }

  /* Links and URLs */
  .sb-link, .sb-url, .sb-naked-url {
    color: #6CB6FF;
    text-decoration: underline;
  }

  .sb-wiki-link, .sb-wiki-link-page {
    color: #A78BFA;
    text-decoration: none;
    background-color: rgba(167, 139, 250, 0.1);
    padding: 2px 4px;
    border-radius: 3px;
  }

  /* Text formatting */
  .sb-emphasis {
    color: #FDE68A;
    font-style: italic;
  }

  .sb-strong {
    color: #FBBF24;
    font-weight: bold;
  }

  .sb-strikethrough {
    text-decoration: line-through;
    color: #9CA3AF;
  }

  .sb-quote {
    color: #A1A1AA;
    font-style: italic;
    border-left: 3px solid rgb(var(--zen-accent));
    padding-left: 12px;
    margin-left: 8px;
  }

  /* Code and syntax highlighting */
  .sb-keyword {
    color: #f75389;
    font-weight: 500;
  }

  .sb-string, .sb-regexp {
    color: #34D399;
  }

  .sb-string2 {
    color: #6EE7B7;
  }

  .sb-number {
    color: #FBBF24;
  }

  .sb-bool {
    color: #FB7185;
  }

  .sb-atom {
    color: rgb(var(--zen-accent));
  }

  .sb-variableName {
    color: #60A5FA;
  }

  .sb-typeName {
    color: #F59E0B;
    font-weight: 500;
  }

  .sb-operator {
    color: rgb(var(--zen-accent));
  }

  .sb-punctuation {
    color: #D1D5DB;
  }

  .sb-comment, .sb-comment-marker {
    color: #6B7280;
    font-style: italic;
  }

  .sb-meta, .sb-code-info {
    color: rgb(var(--zen-accent));
  }

  .sb-literal {
    color: #10B981;
  }

  .sb-invalid {
    color: #EF4444;
    background-color: rgba(239, 68, 68, 0.1);
  }

  /* Special elements */
  .sb-highlight {
    background-color: rgba(247, 111, 83, 0.2);
    color: var(--selected-text);
  }

  .sb-inserted {
    color: #22C55E;
    background-color: rgba(34, 197, 94, 0.1);
  }

  .sb-deleted {
    color: #EF4444;
    background-color: rgba(239, 68, 68, 0.1);
    text-decoration: line-through;
  }
}
```

# Interactive Elements
## Checkboxes
**Examples:**
- [ ] Unchecked task
- [x] Checked task

---

```space-style
.sb-checkbox input[type="checkbox"],
.cm-search input[type="checkbox"] {
  /* Reset default styling */
  appearance: none;
  -webkit-appearance: none;
  margin: 0;

  /* Dimensions */
  width: 22px;
  height: 22px;

  /* Styling */
  color: #FFF;
  border: 2.5px solid rgb(var(--zen-accent)) !important;
  border-radius: 99px;
  cursor: pointer;
  outline: none;

  /* Positioning */
  position: relative;
  top: 0.3em;

  /* Animation */
  transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);

  &:hover {
    transform: scale(1.15);
    background: rgba(var(--zen-accent), 0.3);
  }

  &:checked {
    background: rgba(var(--zen-accent), 1.0);
    border-color: rgb(var(--zen-accent)) !important;

    &::before {
      /* Checkmark */
      content: '';
      position: absolute;
      top: 50%;
      left: 50%;
      width: 5px;
      height: 11px;
      border: 2px solid white;
      border-top: none;
      border-left: none;
      transform: translate(-50%, -60%) rotate(45deg);
      opacity: 1;
    }
  }

  &:disabled {
    opacity: 0.5;
    cursor: not-allowed;
  }
}

/* Search panel checkboxes */
.cm-search input[type="checkbox"] {
  width: 18px;
  height: 18px;
  position: relative;
  top: 0.45em !important;
  border-color: var(--selected-text) !important;

  &:checked:before {
    width: 4px;
    height: 7px;
  }
}

.cm-panel.cm-search label {
  margin-right: 2em !important;
  text-transform: capitalize;
}

/* Animations */
@keyframes checkboxPulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.1); }
}

@keyframes checkmarkSlide {
  0% {
    opacity: 0;
    transform: translate(-50%, -60%) rotate(45deg) scale(0.5);
  }
  100% {
    opacity: 1;
    transform: translate(-50%, -60%) rotate(45deg) scale(1);
  }
}

.sb-checkbox input[type="checkbox"].animate-on-click:checked {
  animation: checkboxPulse 0.3s ease-out;

  &::before {
    animation: checkmarkSlide 0.2s ease-out 0.1s both;
  }
}
```
## Buttons
**Example:** ${widgets.button("Button", function()
  editor.flashNotification "This is the button speaking"
end)}

---

```space-style
.sb-lua-wrapper .sb-lua-directive-inline {
  &:has(button) {
    border: none !important; /* Remove outline */
  }

  button {
    background: var(--zen-dark-bg);
    color: var(--selected-text);
    border: 1px solid var(--selected-text);
    border-radius: 6px;
    padding: 0.5rem;

    &:hover {
      cursor: pointer;
      opacity: 0.8;
      background: var(--zen-hover-bg);
    }
  }
}
```
## Tags
**Examples:**
- Priority tags: #A  #B #C
- Regular tags: #myTag #project #todo
---

```space-style
/* Priority tags */
.sb-hashtag[data-tag-name="A"],
.sb-hashtag[data-tag-name="B"],
.sb-hashtag[data-tag-name="C"] {
  border: 1px solid goldenrod;

  .sb-hashtag-text {
    /*display: none;*/
    padding: 0 1em;
  }

  &:hover {
    opacity: 0.8;
    border-color: rgba(var(--zen-accent));
  }
}

.sb-hashtag[data-tag-name="A"] {
  background: #e76f51;
  color: #e76f51;

  /*&:before {
    content: "    A";
    color: #03045e;
  }*/
}

.sb-hashtag[data-tag-name="B"] {
  background: #e9c46a;
  color: #e9c46a;

  /*&:before {
    content: "    B";
    color: #03045e;
  }*/
}

.sb-hashtag[data-tag-name="C"] {
  background: #2a9d8f;
  color: #2a9d8f;

  /*&:before {
    content: "    C";
    color: #03045e;
  }*/
}

/* Regular tags */
.sb-hashtag {
  /* Styling */
  background: rgba(var(--zen-accent), 0.15) !important;
  border-radius: 4px;
  color: rgba(var(--zen-accent));

  /* Typography */
  font-family: IBM Plex Mono !important;
  font-size: 0.9em;

  /* Spacing */
  padding: 2px 4px;
}
```
## Highlights
**Examples:**
- Highlighted ==text==
- Highlighted ==`code`==

---

```space-style
html[data-theme=dark] {
  #sb-editor span.sb-highlight:not(.sb-meta), .highlight {
    background-color: rgba(var(--zen-accent), 0.8) !important;
    color: white !important;
  }

  /* Do not highlight `==` in edit mode */
  #sb-editor span.sb-highlight.sb-meta {
    background: transparent;
    color: rgba(var(--zen-accent));
  }
}

#sb-main .cm-editor .sb-highlight {
  border-radius: 3px !important;
  padding: 3px !important;
  text-indent: 0 !important;
}
```

# Tables
**Example:** Left, center and right aligned
| Header 1 | Header 2 | Header 3 |
| :------- | :------: | -------: |
| Cell A   |  Cell B  |   Cell C |
| Cell D   |  Cell E  |   Cell F |

---

```space-style
#sb-main .cm-editor table {
  border-collapse: collapse;
  margin-top: 20px;

  /* Table headers */
  thead {
    /* Typography */
    font-size: 0.9em;
    line-height: 0.9em;
    font-family: Antonio;

    tr {
      font-weight: normal;
      opacity: 1;

      td {
        padding: 1ch 1.5ch;

        &:hover {
          cursor: default;
        }
      }

      /* Rounded corners for header */
      &:first-child {
        td:first-child {
          border-top-left-radius: 8px;
        }

        td:last-child {
          border-top-right-radius: 8px;
        }
      }
    }
  }

  /* All cells */
  td {
    padding: 1ch 1.5ch;
  }

  /* Table body */
  tbody {
    tr {
      /* Hover effect */
      &:hover,
      &:nth-of-type(even):hover,
      &:nth-of-type(odd):hover {
        background-color: rgba(255, 255, 255, 0.1);
        filter: brightness(1.2);
      }

      /* Alternating row colors */
      &:nth-of-type(even) {
        background: rgba(var(--editor-table-even-background-color));
      }

      /* Rounded corners for last row */
      &:last-child {
        td:first-child {
          border-bottom-left-radius: 8px;
        }

        td:last-child {
          border-bottom-right-radius: 8px;
        }
      }
    }
  }
}
```
# Media & Special Content
## Images
**Example:**
![[Examples/Example_Image.png]]

---

```space-style
#sb-main .cm-editor {
  img {
    border-radius: 20px;

    &:hover {
      box-shadow: 0 4px 8px 0 rgba(66, 66, 66, 1.0), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
  }
}
```
## Frontmatter
**Example:** ![[Examples/Example_Frontmatter.png]]

```space-style
.sb-frontmatter {
  /* Styling */
  border: 1px solid transparent;
  line-height: 1.41; /* Make up for border */
  background: var(--editor-code-background-color) !important;

  &.cm-line {
    /* Typography */
    font-family: IBM Plex Mono !important;
    font-size: 0.9em;

    /* Styling */
    background: var(--zen-card-bg);

    /* Spacing */
    padding-left: 0.5em !important;
    padding-right: 0.5em !important;
  }

  &:hover {
    border-top: 1px solid var(--selected-text);
    border-bottom: 1px solid var(--selected-text);
  }

  /* Property names */
  .sb-atom {
    font-weight: 500;
  }

  /* Colon */
  .sb-meta {
    margin-right: 1em;
  }

  /* Values */
  > span {
    font-weight: 300;
  }
}

.sb-frontmatter-marker {
  color: var(--editor-code-info-color);
}

/* Rounded borders */
.sb-line-frontmatter-outside {
  /* First line */
  &:has(.sb-frontmatter-marker) {
    border-top-left-radius: 8px;
    border-top-right-radius: 8px;
  }

  /* Last line */
  &:not(:has(.sb-frontmatter-marker)) {
    border-bottom-left-radius: 8px;
    border-bottom-right-radius: 8px;
    margin-bottom: 0.5em;
  }

  /* Not for first/last line */
  &:hover {
    border: 1px solid transparent !important;
  }
}
```
## Admonitions
- [ ] Update admonition style

**Examples:**

> **note**
> This is a note.

> **warning**
> And a warning.

---

```space-style
```
## Keyboard Indicators
**Example:** Press ${widget.new { html = kbd("Ctrl+C") }} to copy

```space-lua
function kbd(text)
  return "<kbd>" .. tostring(text) .. "</kbd>"
end
```

Usage: `${widget.new { html = kbd("Ctrl+C") }}`

---

```space-style
kbd {
  /* Styling */
  box-shadow: oklab(0.701433 0.144643 0.0947755 / 0.5) 0px 0px 0px 1px,
              oklab(0.701433 0.144643 0.0947755 / 0.5) 0px 3px 0px 0px !important;
  border: 1px solid transparent;
  border-radius: 6px;
  background: #000;
  color: var(--selected-text);
  outline: none;

  /* Typography */
  font-size: 0.8em;

  /* Spacing */
  padding: 1px 2px;
}

/* Remove border added by Lua code output widget */
.sb-lua-directive-inline:has(kbd) {
  border: none !important;
}
```
# Search & Navigation
## Page Search

**Example:** Search results are highlighted when searching within a page

![[Examples/Example_SearchInline.png|700]]

![[Examples/Example_Search.png|400]]
![[Examples/Example_SearchSpace.png|700]]

---

```space-style
/* Page search panel */
.cm-panels, .cm-search {
  margin-left: 0.25em;
  margin-right: 0.25em;

  .cm-search {
    /* Styling */
    font-size: 16px;
    background: var(--zen-card-bg);
    border-top: 1px solid var(--selected-text) !important;

    /* Spacing for all children */
    * {
      margin: 0.3em 0.6em 0.3em 0 !important;
    }

    /* Text fields */
    .cm-textfield {
      /* Styling */
      border: 0px;
      border-color: var(--editor-panels-bottom-color);
      background-color: #444;
      border-radius: 5px;

      /* Typography */
      font-size: 1em;
      line-height: 0.8em;

      /* Spacing */
      padding: 0.5em 0.5em;

      &:focus {
        border: none;
        outline: 1px solid rgba(var(--zen-accent));
        box-shadow: unset;
        background: rgba(var(--zen-accent), 0.3);
      }

      &:hover {
        background: rgba(var(--zen-accent), 0.3) !important;
      }
    }

    /* Buttons */
    .cm-button {
      /* Reset */
      background-image: unset;

      /* Styling */
      border: 1px solid #eeeeee40;
      border-radius: 5px;
      background: var(--zen-dark-bg) !important;
      color: var(--selected-text) !important;
      cursor: pointer;

      /* Typography */
      font-size: 0.8em;
      font-weight: 300; /* Fixed typo: font-wight -> font-weight */
      text-transform: capitalize;

      /* Spacing */
      padding: 0.7em 1em;

      &:hover {
        background: rgba(var(--zen-accent), 0.3) !important;
        border-color: var(--blue);
        color: var(--blue);
      }
    }

    /* Close button */
    [aria-label="close"] {
      font-size: 24px !important;
      color: var(--top-color);
      cursor: pointer;

      &:hover {
        color: var(--ui-accent-color);
      }
    }

    /* Make labels and inputs clickable */
    label, label input {
      cursor: pointer;
    }
  }
}

/* Highlighted search results */
.ͼ1 .cm-searchMatch, .ͼ2 .cm-searchMatch, .ͼ3 .cm-searchMatch {
  /* Styling */
  border: 1px dashed #FFF !important;
  border-radius: 6px;
  background: rgba(var(--zen-accent), 0.8) !important;
  color: #FFF !important;
  opacity: 0.8;

  /* Spacing */
  padding: 1px 3px;

  &.cm-searchMatch-selected {
    background: rgba(var(--zen-accent), 1.0) !important;
    opacity: 1;
  }
}

/* Space search (Cmd+Shift+F) */
.sb-modal-box {
  .sb-prompt label {
    color: var(--selected-text);
  }

  .sb-prompt-buttons button {
    /* Reset */
    background-image: unset;

    /* Styling */
    border: 1px solid #eeeeee40;
    border-radius: 5px;
    background: var(--zen-dark-bg) !important;
    color: var(--selected-text) !important;
    cursor: pointer;

    /* Typography */
    font-size: 0.8em;
    font-weight: 300;
    text-transform: capitalize;

    /* Spacing */
    padding: 0.7em 1em;

    &:hover {
      background: rgba(var(--zen-accent), 0.3) !important;
      border-color: var(--blue);
      color: var(--blue);
    }
  }
}
```
## Page Context Picker
**Example:** Appears when typing `[[]]` to link to pages
![[Examples/Example_Context.png|250]]

---

```space-style
/* Link tooltip */
#sb-editor .cm-editor .cm-tooltip {
  z-index: 99999 !important;
  border: solid 1px var(--violet);
  overflow: hidden;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif !important;
  background: var(--zen-card-bg);

  li {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif !important;
    border: 1px solid transparent;
    border-radius: 12px;

    /* Selection state */
    &[aria-selected],
    &:hover {
      background: var(--zen-hover-bg) !important;
      color: var(--selected-text) !important;
      border: 1px solid var(--selected-text);

      .cm-completionDetail {
        color: var(--selected-text) !important;
      }
    }
    &:not([aria-selected]) {
      opacity: 0.8;
    }
  }
}

.cm-tooltip-autocomplete {
  .cm-completionLabel {
    font-weight: 600 !important;
  }

  .cm-completionDetail {
    font-style: normal;
    display: block;
    font-size: 80%;
    margin-left: 5px;
  }
}

/* Rounding based on position */
.cm-tooltip-below {
  border-radius: 0px 10px 10px 10px;
}

.cm-tooltip-above {
  border-radius: 10px 10px 10px 0px;
}

/* Hover effects */
.cm-completionOption:hover,
.cm-completionOption[aria-selected] {
  background-color: var(--zen-hover-bg);
}
```
# Modals & Notifications
## Command Palette (${widget.new { html = kbd("Cmd+K") }})
**Example:** Modal that appears for page navigation and commands
![[Examples/Example_Commands.png]]

---

```space-style
/* Command palette styling */
.sb-modal-box {
  backdrop-filter: blur(16px);
  margin-top: 80px;

  .sb-header,
  .sb-help-text,
  .sb-result-list {
    padding-left: 1em !important;
    padding-right: 1em !important;
  }

  .sb-help-text {
    font-size: 0.8em;
    cursor: default;
  }

  .sb-result-list {
    margin: 0.2em 0;
  }
}

.modal {
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
}

/* Selected option */
.sb-selected-option {
  background: var(--selected-bg) !important;
  color: var(--selected-text) !important;
  border-radius: 6px;
}

/* Page picker buttons */
.sb-modal-box .sb-result-list .sb-option .sb-hint,
.sb-modal-box .sb-selected-option .sb-hint {
  /* Typography */
  font-size: 0.8em;
  font-weight: 300;

  /* Styling */
  /* Removed confusing default button styling, as they are not separate buttons but just information for the main row action */
  /* background: var(--zen-dark-bg) !important; */
  background: transparent !important;
  color: var(--selected-text) !important;
  /* border: 1px solid #eeeeee40; */
  border: none !important;

  /* Spacing */
  padding-left: 0.8em;
  padding-right: 0.8em;
}
```
## Notifications
**Example:** Messages displayed via `editor.flashNotification`

${widgets.button("Click me", function()
  editor.flashNotification "This is the button speaking"
end)}

…appear as:
![[Examples/Example_Button.png|200]]

---

```space-style
.sb-notification {
  color: var(--text-selected) !important;
  border-color: var(--selected-text) !important;
}

.sb-notification-info {
  background-color: var(--zen-card-bg);
  color: var(--selected-text) !important;
  border-color: var(--selected-text) !important;
}

.sb-notification-warning {
  /* TODO */
}
```
# Special Directives
## Lua Directives
**Example:** Query blocks and inline Lua expressions

---
${query[[from index.tag "task" where (page == editor.getCurrentPage() and not done) select {Location="[[" .. ref .. "|Open]]", Task=name}]]}

```space-style
.sb-lua-directive-block {
  border: none !important; /* Only remove for blocks. Inline Lua keeps the border */
  font-size: 0.9em;

  table thead tr td:hover {
      cursor: default;
    }

  /* Enable line break instead of overflow */
  table tbody tr td {
    text-wrap: auto !important;
    text-wrap-mode: wrap !important;
    padding: 0.5em 0 !important;
  }

  table tbody tr td:not(:last-child) {
    border-right: 0.5em solid transparent;
  }
  .button-bar {
    background: transparent !important;
    top: 18px !important;

    /* Buttons */
    button {
      padding: 0.1em 0.5em !important;
      margin-right: 0.5em !important;
    }
    button:hover {
      background: var(--zen-hover-bg) !important;
      /*padding: 1px !important;*/
    }
  }
}
```
## Widgets
**Example:** Linked mentions, table of contents and other widgets at the top or bottom of pages
![[Examples/Example_ToC.png]]
![[Examples/Example_Mentions.png]]

---

```space-style
/* Linked Mentions */
.sb-lua-bottom-widget {
  margin-top: 1em !important;
}

/* Top/Bottom Widgets */
#sb-main .cm-editor .sb-lua-top-widget h1,
#sb-main .cm-editor .sb-lua-bottom-widget h1 {
  background: var(--zen-card-bg);
  padding-left: 1em !important;
}

#sb-main .cm-editor .sb-lua-top-widget .content {
  border-radius: 12px !important;
}

/* Refresh icon */
#sb-main .cm-editor .sb-lua-top-widget .button-bar {
  border-radius: 20px;
  max-height: 1em;
}

#sb-main .cm-editor .collapsible-linked-mentions h1 {
  padding-left: 0.5em !important;
}
```