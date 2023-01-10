# ddev.com Front End

This repository’s source code is for [ddev.com](https://ddev.com)’s statically-generated front end. It’s built with [Astro](https://astro.build), a modern static site generator with all the development fancy you’d hope for but that only ships what’s necessary for the visitor. It helps us keep things organized, maintainable, and fast for visitors.

Most pages are built using plain old Astro components, but blog posts are pulled from the legacy WordPress install via GraphQL. (This is done at build time, so there’s no difference to the visitor.)

## Setup

The project includes an `.nvmrc` file, so if you have `nvm` installed you can run `nvm use` to make sure you’re running an appropriate Node.js version.

After that, run `npm install` to set up the project’s dependencies. Then you can run any of the [commands](#commands) below.

> 💡 There’s also a `.prettierrc` file in the project that’ll save you formatting time and keep things consistent if you’re using Prettier in your editor or IDE.

You’ll also need to wire up GraphQL so Astro can pull blog post content from Wordpress. Right now you’ll need a locally-running build of `drud/ddevdotcom`.

1. Get `drud/ddevdotcom` running locally, ideally with DDEV. :)
2. Install the WPGraphQL WordPress plugin.
3. Copy this project’s `.env.example` to `.env`, and add your GraphQL endpoint. (Something like `http://ddevdotcom.ddev.site/wp/graphql`.)
4. Run `npm run dev` or `npm run build` and see if it works or falls over.

## Ingredients

- [Astro](https://astro.build)
- [Tailwind CSS](https://tailwindcss.com)
- [Tailwind Typography](https://tailwindcss.com/docs/typography-plugin) plugin
- [Heroicons](https://heroicons.com)

## Project Structure

Astro looks for `.astro` or `.md` files in the `src/pages/` directory. Each page is exposed as a route based on its file name.

There’s nothing special about `src/components/`, but that’s where we like to put any Astro/React/Vue/Svelte/Preact components.

Any static assets, like images, can be placed in the `public/` directory.

You’ll also see a `lib/` directory with our consolidated GraphQL API queries and some custom formatting and text-handling stuff.

## Commands

All commands are run from the root of the project, from a terminal:

| Command                | Action                                             |
| :--------------------- | :------------------------------------------------- |
| `npm install`          | Installs dependencies                              |
| `npm run dev`          | Starts local dev server at `localhost:3000`        |
| `npm run build`        | Build your production site to `./dist/`            |
| `npm run preview`      | Preview your build locally, before deploying       |
| `npm run astro ...`    | Run CLI commands like `astro add`, `astro preview` |
| `npm run astro --help` | Get help using the Astro CLI                       |

## Resources

- [Astros documentation](https://docs.astro.build)
- [Astro Discord server](https://astro.build/chat)
