---
title: Hello World
toc: true
mathjax: true
abbrlink: 16107
tags: ["hello", "world"]
categories: Golang
thumbnail: //p.pstatp.com/origin/fefd00018ec9ca73a39e
---
Welcome to [Hexo](https://hexo.io/)! This is your very first post. Check [documentation](https://hexo.io/docs/) for more info. If you get any problems when using Hexo, you can find the answer in [troubleshooting](https://hexo.io/docs/troubleshooting.html) or you can ask me on [GitHub](https://github.com/hexojs/hexo/issues).

<!--more-->

## Quick Start

### Create a new post

$$
\sin \left(x\right)
$$

$$
i\hbar\frac{\partial}{\partial t}\psi=-\frac{\hbar^2}{2m}\nabla^2\psi+V\psi
$$

\begin{eqnarray\*}
\nabla\cdot\vec{E}&=&\frac{\rho}{\epsilon_0}\\\\
\nabla\cdot\vec{B}&=&0\\\\
\nabla\times\vec{E}&=&-\frac{\partial B}{\partial t}\\\\
\nabla\times\vec{B}&=&\mu_0\left(\vec{J}+\epsilon_0\frac{\partial E}{\partial t}\right)\\\\
\end{eqnarray\*}

Here is a footnote reference,[^1] and another.[^longnote]

[^1]: Here is the footnote.

[^longnote]: Here's one with multiple blocks.

    Subsequent paragraphs are indented to show that they
belong to the previous footnote.

``` console
$ hexo new "My New Post"
```

Here is an inline note.^[Inlines notes are easier to write, since you don't have to pick an identifier and move down to type the note.]

{% codeblock hexo-filter-mathjax lang:javascript https://github.com/stevenjoezhang/hexo-filter-mathjax/blob/master/index.js index.js %}
hexo.extend.filter.register('after_render:html', data => {
  return data.replace(/<head>(?!<\/head>).+?<\/head>/s, str => str.replace('</head>', `<style>${css}</style></head>`));
});
{% endcodeblock %}

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` console
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` console
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### Deploy to remote sites

``` console
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/one-command-deployment.html)
