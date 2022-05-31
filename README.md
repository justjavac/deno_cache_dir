# deno_cache_dir

[![tag](https://img.shields.io/github/release/justjavac/deno_cache_dir)](https://github.com/justjavac/deno_cache_dir/releases)
[![Build Status](https://github.com/justjavac/deno_cache_dir/workflows/ci/badge.svg?branch=master)](https://github.com/justjavac/deno_cache_dir/actions)
[![license](https://img.shields.io/github/license/justjavac/deno_cache_dir)](https://github.com/justjavac/deno_cache_dir/blob/master/LICENSE)
[![](https://img.shields.io/badge/deno-v1.3-green.svg)](https://github.com/denoland/deno)

Returns the path to the user's cache directory.

> _In v1.1.2(2020.06.26), Deno
> [Remove `Deno.dir` and dirs dependency #6385](https://github.com/denoland/deno/pull/6385)_

The returned value depends on the operating system and is either a string,
containing a value from the following table, or `null`.

| Platform | Value                               | Example                          |
| -------- | ----------------------------------- | -------------------------------- |
| Linux    | `$XDG_CACHE_HOME` or `$HOME`/.cache | /home/justjavac/.cache           |
| macOS    | `$HOME`/Library/Caches              | /Users/justjavac/Library/Caches  |
| Windows  | `$LOCALAPPDATA`                     | C:\Users\justjavac\AppData\Local |

## Usage

Requires `allow-env` permission.

Returns `null` if there is no applicable directory or if any other error occurs.

```ts
import cacheDir from "https://deno.land/x/cache_dir/mod.ts";

cacheDir();
// Lin: "/home/justjavac/.cache"
// Mac: "/Users/justjavac/Library/Caches"
// Win: "C:\Users\justjavac\AppData\Local"
```

## License

[deno_cache_dir](https://github.com/justjavac/deno_cache_dir) is released under
the MIT License. See the bundled [LICENSE](./LICENSE) file for details.
