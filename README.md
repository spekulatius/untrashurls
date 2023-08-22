# `untrashurls`: Untrashes URL strings

Removes various usually irrelevant URL pieces from a file containing URLs or STDIN:

- `http://....:80/` => `http://..../`
- `https://....:443/` => `https://..../`
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

## `filter-static-urls`: The `urinteresting`-mode

Inspired by Tomnomnom's [`urinteresting`](https://github.com/tomnomnom/hacks/tree/master/urinteresting) there is a helper script to achieve a similar output:


```bash
cat ./lots-of-urls | untrashurls | filter-static-urls
```

or

```bash
untrashurls --file ./lots-of-urls | filter-static-urls
```

This will drop any static assets. For a detailed list of dropped extensions check the script.

More detailed checks are provided by `urinteresting`.

## Installation

You'll need `trurl` to run `untrashurls`. You can build and install `trurl` yourself:

```bash
git clone git@github.com:curl/trurl.git /tmp/trurl
cd /tmp/trurl
make
mv /tmp/trurl/trurl /home/$USER/.local/
cd -
rm -rf /tmp/trurl
```