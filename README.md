# Heroku Buildpack: Train

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks)
for [Train](https://github.com/shaoshing/train), based on the [Revel](https://github.com/robfig/revel)
[buildpack](https://github.com/robfig/heroku-buildpack-go-revel).

## Train

From the author’s description:

  Assets Management Package for web app in Go. The main purpose of it is to introduce some good practices already existed in Ruby on Rails’ Assets Pipeline.

## Usage

### Setup

This buildpack requires [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to operate.
To use, create a `.buildpack` file in your root directory with a Ruby and Go buildpack:

```
$ heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git

$ cat .buildpacks
https://github.com/heroku/heroku-buildpack-ruby.git
https://github.com/robfig/heroku-buildpack-go-revel.git
https://github.com/nbio/heroku-buildpack-go-train.git
```

### Deployment

Once `.buildpacks` and heroku remote are set up, deployment is a single command.

```
$ git push heroku master
```

## Hacking on this Buildpack

To change this buildpack, fork it on GitHub. Push
changes to your fork, then create a test app with
`--buildpack YOUR_GITHUB_GIT_URL` and push to it. If you
already have an existing app you may use `heroku config:add
BUILDPACK_URL=YOUR_GITHUB_GIT_URL` instead of `--buildpack`.

[go]: http://golang.org/
[buildpack]: http://devcenter.heroku.com/articles/buildpacks
[quickstart]: http://mmcgrana.github.com/2012/09/getting-started-with-go-on-heroku.html
[build-constraint]: http://golang.org/pkg/go/build/
[app-engine-build-constraints]: http://blog.golang.org/2013/01/the-app-engine-sdk-and-workspaces-gopath.html
[heroku-buildpack-multi]: https://github.com/ddollar/heroku-buildpack-multi
[revel]: https://github.com/robfig/revel
[train]: https://github.com/shaoshing/train
