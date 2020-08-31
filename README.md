# Heading Tool with anchor

![Version of EditorJS that the plugin is compatible with](https://badgen.net/badge/Editor.js/v2.0/blue)

Provides Headings Blocks with the ability to set an anchor text for the [Editor.js](https://ifmo.su/editor). Forked by [Header Tool](https://github.com/editor-js/header)

## Screenshot
![header-with-anchor](https://user-images.githubusercontent.com/12189769/91700694-f1998c00-eb7e-11ea-9cfe-4662924afa72.jpg)

## Installation

### Install via NPM

Get the package

```shell
npm i --save editorjs-header-with-anchor
```

Include module at your application

```javascript
const Header = require('editorjs-header-with-anchor');
```

### Download to your project's source dir

1. Upload folder `dist` from repository
2. Add `dist/bundle.js` file to your page.


## Usage

Add a new Tool to the `tools` property of the Editor.js initial config.

```javascript
var editor = EditorJS({
  ...

  tools: {
    ...
    header: Header,
  },

  ...
});
```

## Shortcut

You can insert this Block by a useful shortcut. Set it up with the `tools[].shortcut` property of the Editor's initial config.

```javascript
var editor = EditorJS({
  ...

  tools: {
    ...
    header: {
      class: Header,
      shortcut: 'CMD+SHIFT+H',
    },
  },

  ...
});
```

## Config Params

All properties are optional.

| Field        | Type       | Description                      |
| ------------ | ---------- | -------------------------------- |
| placeholder  | `string`   | header's placeholder string      |
| levels       | `number[]` | enabled heading levels           |
| defaultLevel | `number`   | default heading level            |
| allowAnchor  | `boolean`  | Anchor enabling (default: `true`) |
| anchorLength  | `number`  | Anchor length (default: `50`)     |

```javascript
var editor = EditorJS({
  ...

  tools: {
    ...
    header: {
      class: Header,
      config: {
        placeholder: 'Enter a header',
        levels: [2, 3, 4],
        defaultLevel: 3,
        allowAnchor: true,
        anchorLength: 100,
      }
    }
  }

  ...
});
```

## Output data

| Field  | Type     | Description                                      |
| ------ | -------- | ------------------------------------------------ |
| text   | `string` | header's text                                    |
| level  | `number` | level of header: 1 for H1, 2 for H2 ... 6 for H6 |
| anchor | `string` | anchor's text                                    |

```json
{
  "type": "header",
  "data": {
    "text": "Why Telegram is the best messenger",
    "level": 2,
    "anchor": "Anchor"
  }
}
```
