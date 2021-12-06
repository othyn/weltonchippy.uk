# weltonchippy.uk

[![Continuous Integration](https://github.com/othyn/weltonchippy.uk/actions/workflows/ci.yml/badge.svg)](https://github.com/othyn/weltonchippy.uk/actions/workflows/ci.yml)
[![Continuous Deployment](https://github.com/othyn/weltonchippy.uk/actions/workflows/cd.yml/badge.svg)](https://github.com/othyn/weltonchippy.uk/actions/workflows/cd.yml)
[![GitHub license](https://img.shields.io/github/license/othyn/weltonchippy.uk)](https://github.com/othyn/weltonchippy.uk/blob/main/LICENSE)
[![Love](https://img.shields.io/badge/built%20with-love-red)](https://img.shields.io/badge/built%20with-love-red)

Welton Chippy's website (formerly Kedgeree), designed to be fresh and modern with inspiration from the sea with vibrancy. Design is inspired by [Vannsl/tailwind-landing-page-nuxt](https://github.com/Vannsl/tailwind-landing-page-nuxt).

The repo is based on NuxtJS (in static mode) which is then containerised and served in a thin Alpine flavoured NGINX image in K8's to keep things light and easily maintainable.

You can find the website at one of the following locations;

- [weltonchippy.uk](https://weltonchippy.uk)
- [welton-chippy.uk](https://welton-chippy.uk)
- [kedgeree.uk](https://kedgeree.uk)

With my favorite new fun locations being;

- [chippy.rocks](https://chippy.rocks)
- [welton.chippy.rocks](https://welton.chippy.rocks)

## Todo

- Containerise it!
- Push up to K8's cluster

## Development

When developing the site, use the following to get setup and running with a hot reload local environment:

```bash
# Install dependencies
$ yarn install

# Serve with hot reload at localhost:3000
$ yarn dev

# Ensure the code is linted
$ yarn lint
```

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org). Thought this sentence was best kept in!

## Building the production app image

**The CD GitHub Action should auto build and tag an image for you based on when a new tag is created/pushed**, so you shouldn't need to build the image manually or push it. This will then become [available as part of GitHub's packages feature](https://github.com/othyn/othyn.com/pkgs/container/othyn.com). Just create a tag via a [new GitHub release](https://github.com/othyn/othyn.com/releases) or push a local tag, and it should do the rest.

However, if you do wish to do it, go ahead and run a normal Docker Compose build:

```bash
# Ensure the code is linted
$ yarn lint

# Production container build
$ docker-compose build

# ...or if you're having problems...
$ docker-compose build --no-cache
```

Then push it to a remote container registry of your choice. There should be no requirement to develop from the app container itself, however if you wish to, knock yourself out!

For manually building a static Nuxt output, here is a [handy list of commands](https://nuxtjs.org/announcements/going-full-static/#commands);

```bash
# Start the development server (static aware)
$ yarn dev

# Bundle your Nuxt application for production if needed (static aware) and export your application to static HTML in `dist/` directory
$ yarn generate

# Serve your production application from `dist/`
$ yarn start
```
