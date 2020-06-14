# prisonlife-diary
Prison Life game development diary

[Using Hugo and Github pages gh-pages branch method](https://gohugo.io/hosting-and-deployment/hosting-on-github/)

See: https://rationalgames.github.io/prisonlife-diary/

## Installation

[Download Hugo](https://github.com/gohugoio/hugo/releases/download/v0.72.0/hugo_0.72.0_Linux-64bit.deb)

Theme used: https://themes.gohugo.io/hugo-coder/

```
git submodule add https://github.com/luizdepra/hugo-coder.git themes/hugo-coder
```

## Development

the public folder is a git branch of the gh-pages branch where the static site will be generated.

To create the tree (only needed to be done one)
```
git worktree add -B gh-pages public origin/gh-pages
```

To generate the site, run hugo
```
hugo
```

To commit and publish all generated content
```
./publish-gh-pages.sh
```