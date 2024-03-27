# Lesson Tool

![Version of EditorJS that the plugin is compatible with](https://badgen.net/badge/Editor.js/v2.0/blue)

Provides Lesson Blocks for the [Editor.js](https://ifmo.su/editor).

## Installation

Get the package

```shell
yarn add @kalebu2468/editor-lessons
```

Include module at your application

```javascript
import Lessons from "@kalebu2468/editor-lessons";
```

## Usage

Add a new Tool to the `tools` property of the Editor.js initial config.

```javascript
var editor = EditorJS({
  ...

  tools: {
    ...
    lessons: Lessons,
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
    lessons: {
      class: Lessons,
    },
  },

  ...
});
```

## Config Params

All properties are optional.

| Field        | Type       | Description                 |
| ------------ | ---------- | --------------------------- |
| placeholder  | `string`   | lesson's placeholder string |
| levels       | `number[]` | enabled lesson levels       |
| defaultLevel | `number`   | default lesson level        |

```javascript
var editor = EditorJS({
  ...

  tools: {
    ...
    lessons: {
      class: Lessons,
      config: {
        placeholder: 'Enter a lesson',
        levels: [2, 3, 4],
        defaultLevel: 3
      }
    }
  }

  ...
});
```

## Tool's settings

![An image showing the lesson block tool](https://capella.pics/634ad545-08d7-4cb7-8409-f01289e0e5e1.jpg)

You can select one of six levels for heading.

## Output data

| Field | Type     | Description     |
| ----- | -------- | --------------- |
| text  | `string` | lesson's text   |
| level | `number` | level of lesson |

```json
{
  "type": "lessons",
  "data": {
    "text": "Why Telegram is the best messenger",
    "level": 2
  }
}
```
