<p align="center"><img src="https://raw.githubusercontent.com/go-birdsite/brand/main/social/go-birdsite.png" alt="go-birdsite" width="640"></p>

<h1 align="center">go-birdsite</h1>
<p align="center">Pure-Go best-effort read client for public Twitter/X timelines.</p>
<p align="center"><a href="https://go-birdsite.github.io/docs/"><img src="https://img.shields.io/badge/docs-mkdocs--material-0A6E96?style=flat-square&logo=materialformkdocs&logoColor=white" alt="docs"></a> <a href="https://pkg.go.dev/github.com/go-birdsite/twitter"><img src="https://img.shields.io/badge/pkg.go.dev-reference-0079A8?style=flat-square&logo=go&logoColor=white" alt="pkg.go.dev"></a> <img src="https://img.shields.io/badge/Go-1.26-00ADD8?style=flat-square&logo=go&logoColor=white" alt="Go"> <img src="https://img.shields.io/badge/license-BSD--3--Clause-0A6E96?style=flat-square" alt="license"></p>

---

## What is this?

A pure-Go (**CGO=0**), dependency-free, **best-effort** read client for public Twitter/X profile timelines. It reads the public syndication timeline endpoint that powers embedded timeline widgets and extracts tweets from the `__NEXT_DATA__` JSON blob.

The client lives in [`go-birdsite/twitter`](https://github.com/go-birdsite/twitter):

```go
c := twitter.New()

tl, err := c.UserTweets(context.Background(), "jack")
if err != nil {
	panic(err) // 403/429 here means Twitter/X is blocking the request.
}
for _, tw := range tl.Tweets {
	fmt.Printf("@%s: %s (%d likes)\n", tw.Author, tw.Text, tw.Likes)
}
```

## Install

```sh
go get github.com/go-birdsite/twitter
```

## ⚠️ Best-effort — read this first

This is inherently fragile. Twitter/X changes and locks these endpoints, and many profiles or rate states require a valid auth token.

Blocked requests (403/429) surface as errors — they indicate blocking and fragility, not a bug in the code. Respect Twitter/X's Terms of Service and applicable law when using this library.

## Links

- 📖 Docs — <https://go-birdsite.github.io/docs/>
- 🌐 Site — <https://go-birdsite.github.io/>
- 🧩 Client — <https://github.com/go-birdsite/twitter>
- 📦 API reference — <https://pkg.go.dev/github.com/go-birdsite/twitter>
- 🎨 Brand assets — <https://github.com/go-birdsite/brand>

---
<p align="center"><sub>Branding in <a href="https://github.com/go-birdsite/brand">go-birdsite/brand</a>.</sub></p>
