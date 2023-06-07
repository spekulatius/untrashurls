# `untrashurls`: Untrashes URL strings

Removes various usually irrelevant URL pieces from a file containing URLs or STDIN:

- `http://....:80/` => `http://..../`
- `https://....:443/` => `http://..../`
- `?utm_*` => `/dev/null`
- `?att_*` => `/dev/null`

The final result will automatically be deduplicated.

## Usage

```bash
cat ./lots-of-urls | untrashurls
```

or 

```bash
untrashurls --file ./lots-of-urls
```

## `--strict`: The `urinteresting`-mode

Inspired by Tomnomnom's [urinteresting](https://github.com/tomnomnom/hacks/tree/master/urinteresting) there is a mode to achieve a similar output:


```bash
cat ./lots-of-urls | untrashurls --strict
```

or

```bash
untrashurls --file ./lots-of-urls --strict
```

This will drop any static assets.

## Installation

You'll need `trurl` and `grep` to run `untrashurls`. You can build and install `trurl` yourself:

```bash
git clone git@github.com:curl/trurl.git /tmp/trurl
cd /tmp/trurl
make
mv /tmp/trurl/trurl /home/$USER/.local/
cd -
rm -rf /tmp/trurl
```

