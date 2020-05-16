# Deno features

[https://deno.land](https://deno.land)

## VS Code (JetBrains IDEs is not yet available)

- Support Deno Extension [axetroy.vscode-deno](https://marketplace.visualstudio.com/items?itemName=axetroy.vscode-deno)

  ```json
  // .vscode/settings.json
  {
    "deno.enable": true,
    "deno.import_map": "./import_map.json",
    "editor.formatOnSave": true,
    "[typescript]": {
      "editor.defaultFormatter": "esbenp.prettier-vscode"
      // "editor.defaultFormatter": "axetroy.vscode-deno" - default deno formatter
    }
  }
  ```

- Formatter

  Deno has own formatter `deno fmt` (without configuration 😢). I use [prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode).

## Features

- import_map (used with --unstable arg)

  ```json
  // import_map.json
  {
    "imports": {
      "http/": "https://deno.land/std/http/",
      "flags/": "https://deno.land/std/flags/"
    }
  }
  ```

  ```ts
  import { parse } from 'flags/mod.ts'
  import { serve } from 'http/server.ts'
  ```
