![Stream Deck package banner image](https://res.cloudinary.com/j4ckofalltrades/image/upload/v1713716273/foss/streamdeck-package.png)

![Version](https://img.shields.io/github/v/tag/j4ckofalltrades/streamdeck-package?label=version)
![License](https://img.shields.io/github/license/j4ckofalltrades/streamdeck-package)

This repo contains an action for packaging Stream Deck plugins with the [Elgato Maker CLI](https://github.com/elgatosf/cli).

> [!NOTE]  
> The Elgato Maker CLI is currently in beta.

## Input

```yaml
inputs:
  input-directory:
    description: "Path of the plugin to pack (the *.sdPlugin directory)"
    required: true
  output-directory:
    description: "Specifies the path for the output directory where the .streamDeckPlugin file will be created"
    required: false
    default: 'release'
```

## Usage

This action will package your Stream Deck plugin and create a GitHub release.

```yaml
name: Package Stream Deck plugin
on:
  push:
    tags:
      - 'v*.*.*'
  workflow_dispatch:

jobs:
  package-plugin:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: j4ckofalltrades/streamdeck-package@v0.0.1
        with:
          input-directory: "path/to/plugin/dir"
          output-directory: "path/to/output/dir"
```

## Attribution

Icons by [Icons8](https://icons8.com)
