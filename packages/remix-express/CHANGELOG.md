# `@remix-run/express`

## 2.16.5

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.16.5`

## 2.16.4

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.16.4`

## 2.16.3

### Patch Changes

- Better validation of `x-forwarded-host` header to preent potential security issues. ([#10553](https://github.com/remix-run/remix/pull/10553))
- Updated dependencies:
  - `@remix-run/node@2.16.3`

## 2.16.2

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.16.2`

## 2.16.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.16.1`

## 2.16.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.16.0`

## 2.15.3

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.15.3`

## 2.15.2

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.15.2`

## 2.15.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.15.1`

## 2.15.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.15.0`

## 2.14.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.14.0`

## 2.13.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.13.1`

## 2.13.0

### Patch Changes

- Fix adapter logic for aborting `request.signal` so we don't incorrectly abort on the `close` event for successful requests ([#10046](https://github.com/remix-run/remix/pull/10046))
- Updated dependencies:
  - `@remix-run/node@2.13.0`

## 2.12.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.12.1`

## 2.12.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.12.0`

## 2.11.2

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.11.2`

## 2.11.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.11.1`

## 2.11.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.11.0`

## 2.10.3

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.10.3`

## 2.10.2

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.10.2`

## 2.10.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.10.1`

## 2.10.0

### Patch Changes

- Upgrade `express` dependency to `^4.19.2` ([#9184](https://github.com/remix-run/remix/pull/9184))
- Updated dependencies:
  - `@remix-run/node@2.10.0`

## 2.9.2

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.9.2`

## 2.9.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.9.1`

## 2.9.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.9.0`

## 2.8.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.8.1`

## 2.8.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.8.0`

## 2.7.2

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.7.2`

## 2.7.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.7.1`

## 2.7.0

### Minor Changes

- Vite: Add a new `basename` option to the Vite plugin, allowing users to set the internal React Router [`basename`](https://reactrouter.com/v6/routers/create-browser-router#basename) in order to to serve their applications underneath a subpath ([#8145](https://github.com/remix-run/remix/pull/8145))

### Patch Changes

- Use `req.originalUrl` instead of `req.url` so that Remix sees the full URL ([#8145](https://github.com/remix-run/remix/pull/8145))

  - Remix relies on the knowing the full URL to ensure that server and client code can function together, and does not support URL rewriting prior to the Remix handler

- Updated dependencies:
  - `@remix-run/node@2.7.0`

## 2.6.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.6.0`

## 2.5.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.5.1`

## 2.5.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.5.0`

## 2.4.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.4.1`

## 2.4.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.4.0`

## 2.3.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.3.1`

## 2.3.0

### Patch Changes

- Fix flash of unstyled content on initial page load in Vite dev when using a custom Express server ([#7937](https://github.com/remix-run/remix/pull/7937))
- Updated dependencies:
  - `@remix-run/node@2.3.0`

## 2.2.0

### Patch Changes

- Allow the `@remix-run/express` adapter to work behind a proxy when using `app.enable('trust proxy')` ([#7323](https://github.com/remix-run/remix/pull/7323))
  - Previously, this used `req.get('host')` to construct the Remix `Request`, but that does not respect `X-Forwarded-Host`
  - This now uses `req.hostname` which will respect `X-Forwarded-Host`
- Updated dependencies:
  - `@remix-run/node@2.2.0`

## 2.1.0

### Patch Changes

- Flush headers for `text/event-stream` responses ([#7619](https://github.com/remix-run/remix/pull/7619))
- Updated dependencies:
  - `@remix-run/node@2.1.0`

## 2.0.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@2.0.1`

## 2.0.0

### Major Changes

- Require Node >=18.0.0 ([#6939](https://github.com/remix-run/remix/pull/6939))

- For preparation of using Node's built in fetch implementation, installing the fetch globals is now a responsibility of the app server ([#7009](https://github.com/remix-run/remix/pull/7009))

  - If you are using `remix-serve`, nothing is required
  - If you are using your own app server, you will need to install the globals yourself

    ```js filename=server.js
    import { installGlobals } from "@remix-run/node";

    installGlobals();
    ```

- `source-map-support` is now a responsibility of the app server ([#7009](https://github.com/remix-run/remix/pull/7009))

  - If you are using `remix-serve`, nothing is required
  - If you are using your own app server, you will need to install [`source-map-support`](https://www.npmjs.com/package/source-map-support) yourself.

    ```sh
    npm i source-map-support
    ```

    ```js filename=server.js
    import sourceMapSupport from "source-map-support";
    sourceMapSupport.install();
    ```

### Patch Changes

- Switch to `headers.entries()` instead of non-spec-compliant `headers.raw()` in `sendRemixResponse` ([#7150](https://github.com/remix-run/remix/pull/7150))
- Remove references to fetch polyfills in node and arc adapters ([#7230](https://github.com/remix-run/remix/pull/7230))
- Updated dependencies:
  - `@remix-run/node@2.0.0`
  - `@remix-run/web-fetch@4.4.0`
  - `@remix-run/web-file@3.1.0`
  - `@remix-run/web-stream@1.1.0`

## 1.19.3

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.19.3`

## 1.19.2

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.19.2`

## 1.19.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.19.1`

## 1.19.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.19.0`

## 1.18.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.18.1`

## 1.18.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.18.0`

## 1.17.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.17.1`

## 1.17.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.17.0`

## 1.16.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.16.1`

## 1.16.0

### Patch Changes

- feat: support async `getLoadContext` in all adapters ([#6170](https://github.com/remix-run/remix/pull/6170))
- Updated dependencies:
  - `@remix-run/node@1.16.0`

## 1.15.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.15.0`

## 1.14.3

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.14.3`

## 1.14.2

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.14.2`

## 1.14.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.14.1`

## 1.14.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.14.0`

## 1.13.0

### Patch Changes

- Fix fetch `Request` creation for incoming URLs with double slashes ([#5336](https://github.com/remix-run/remix/pull/5336))
- Updated dependencies:
  - `@remix-run/node@1.13.0`

## 1.12.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.12.0`

## 1.11.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.11.1`

## 1.11.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.11.0`

## 1.10.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.10.1`

## 1.10.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.10.0`

## 1.9.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.9.0`

## 1.8.2

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.8.2`

## 1.8.1

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.8.1`

## 1.8.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.8.0`

## 1.7.6

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.7.6`

## 1.7.5

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.7.5`

## 1.7.4

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.7.4`

## 1.7.3

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.7.3`

## 1.7.2

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.7.2`

## 1.7.1

### Patch Changes

- Ensured that requests are properly aborted on closing of a `Response` instead of `Request` ([#3626](https://github.com/remix-run/remix/pull/3626))
- Updated dependencies:
  - `@remix-run/node@1.7.1`

## 1.7.0

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.7.0`

## 1.6.8

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.6.8`

## 1.6.7

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.6.7`

## 1.6.6

### Patch Changes

- Updated dependencies:
  - `@remix-run/node@1.6.6`

## 1.6.5

### Patch Changes

- Updated dependencies
  - `@remix-run/node@1.6.5`
