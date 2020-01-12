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

## Quick Start

### Create a new post

$$
\sin \left(x\right)
$$

$$
i\hbar\frac{\partial}{\partial t}\psi=-\frac{\hbar^2}{2m}\nabla^2\psi+V\psi
$$

{% plantuml %}
@startuml
actor Bob #red
' The only difference between actor
'and participant is the drawing
participant Alice
participant "I have a really\nlong name" as L #99FF99
/' You can also declare:
   participant L as "I have a really\nlong name"  #99FF99
  '/

Alice->Bob: Authentication Request
Bob->Alice: Authentication Response
Bob->L: Log transaction
@enduml
{% endplantuml %}

<!--more-->

\begin{eqnarray\*}
\nabla\cdot\vec{E}&=&\frac{\rho}{\epsilon_0}\\\\
\nabla\cdot\vec{B}&=&0\\\\
\nabla\times\vec{E}&=&-\frac{\partial B}{\partial t}\\\\
\nabla\times\vec{B}&=&\mu_0\left(\vec{J}+\epsilon_0\frac{\partial E}{\partial t}\right)\\\\
\end{eqnarray\*}

{% plantuml %}
@startuml
scale 750 width
package foo1 <<Node>> {
  class Class1
}

package foo2 <<Rectangle>> {
  class Class2
}

package foo3 <<Folder>> {
  class Class3
}

package foo4 <<Frame>> {
  class Class4
}

package foo5 <<Cloud>> {
  class Class5
}

package foo6 <<Database>> {
  class Class6
}

@enduml
{% endplantuml %}

``` console
$ hexo new "My New Post"
```

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
