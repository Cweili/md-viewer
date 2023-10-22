# MdViewer

[![npm][badge-version]][npm]
[![bundle size][badge-size]][bundlephobia]
[![npm downloads][badge-downloads]][npm]
[![license][badge-license]][license]


[![github][badge-issues]][github]
[![build][badge-build]][workflows]
[![coverage][badge-coverage]][coveralls]

View markdown with code highlighting, katex, mermaid.

* Rendering markdown in WebWorkers
* Dynamically load required libraries from CDN
* Code highlighting, katex, mermaid included
* React supported

[Documents and examples][doc].

## Installation

```shell
npm install md-viewer
```

## Usage

Markdown renderer

```js
import { markdown } from 'md-viewer'

const markdownOptions = {
  katex: {},
  marked: {},
  cdn: {
    prefix: 'https://cdnjs.cloudflare.com/ajax/libs/',
    libs: {
      marked: `marked/9.1.2/lib/marked.umd.min.js`,
      prism: `prism/1.29.0/components/prism-core.min.js`,
      katex: `KaTeX/0.16.9/katex.min.js`,
      mermaid: `mermaid/10.5.0/mermaid.min.js`,
    },
  },
}
const renderMarkdown = markdown(markdownOptions)
const content = '# hello world'
const html = await renderMarkdown(content)
const htmlWithMermaid = await renderMarkdown.mermaid(content, html)
```

React component

```jsx
import { MdViewer } from 'md-viewer'

function ReactComponent() {
  return (
    <MdViewer options={markdownOptions}>
      # hello world
    </MdViewer>
  )
}
```


[doc]: https://cweili.github.io/md-viewer/

[badge-version]: https://img.shields.io/npm/v/md-viewer.svg
[badge-downloads]: https://img.shields.io/npm/dt/md-viewer.svg
[npm]: https://www.npmjs.com/package/md-viewer

[badge-size]: https://img.shields.io/bundlephobia/minzip/md-viewer.svg
[bundlephobia]: https://bundlephobia.com/result?p=md-viewer

[badge-license]: https://img.shields.io/npm/l/md-viewer.svg
[license]: https://github.com/Cweili/md-viewer/blob/master/LICENSE

[badge-issues]: https://img.shields.io/github/issues/Cweili/md-viewer.svg
[github]: https://github.com/Cweili/md-viewer

[badge-build]: https://img.shields.io/github/actions/workflow/status/Cweili/md-viewer/ci.yml?branch=master
[workflows]: https://github.com/Cweili/md-viewer/actions/workflows/ci.yml?query=branch%3Amaster

[badge-coverage]: https://img.shields.io/coveralls/github/Cweili/md-viewer/master.svg
[coveralls]: https://coveralls.io/github/Cweili/md-viewer?branch=master
