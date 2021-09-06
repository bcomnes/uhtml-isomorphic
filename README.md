# uhtml-isomorphic
[![Actions Status](https://github.com/bcomnes/uhtml-isomorphic/workflows/tests/badge.svg)](https://github.com/bcomnes/uhtml-isomorphic/actions)

Isomorphic exports of [uhtml][uhtml]

```
npm install uhtml-isomorphic
```

## Usage

Use [uhtml][uhtml] or [uhtml-ssr][ssr] from a single import identifier depending on then environment you are running.

``` js
import {render, html, svg} from 'uhtml-isomorphic';
// const {render, html, svg} = require('uhtml');

render(document.body, html`<h1>Hello 👋 µhtml</h1>`);
```

## How

While @webreflection recomends [require-overrides](https://github.com/WebReflection/require-overrides/#readme) in the offical documentation, that requires special flags or transforms to work.

`uhtml-isomorphic` works by utilizing environment specific exports fields so that you can have dependency injection at the built-in module resolver layer.
It supports the following export fields:

- `main` (cjs node)
- `browser` (cjs browser)
- `exports.import` (esm node)
- `exports.reqire` (cjs node)
- `exports.browser` (esm browser)

## License

MIT

[uhtml]: https://github.com/WebReflection/uhtml
[ssr]: https://github.com/WebReflection/uhtml-ssr
