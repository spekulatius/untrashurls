# `untrashurls`: Untrashes URL strings

Removes various usually irrelevant URL pieces from a file containing URLs or STDIN:

- `http://....:80/` => `http://..../`
- `https://....:443/` => `http://..../`
- `?utm_*` => `/dev/null`
- `?att_*` => `/dev/null`

The final result will automatically be deduplicated.

## Usage:

```bash
cat lots-of-urls | untrashurls
```

```bash
cat lots-of-urls | untrashurls
```

## `urinteresting`-mode

Inspired by Tomnomnom's [urinteresting](https://github.com/tomnomnom/hacks/tree/master/urinteresting) there is a mode to achieve a similar output: