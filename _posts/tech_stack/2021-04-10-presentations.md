---
title: Presentation Tooling
category: Tools
tags: [latex, dual screen presentations, pympress]
---

Caching tooling configuration that ease off dual screen presentations for future quick access

## Dual Screen Presentations

 - use [pympress](https://github.com/Cimbali/pympress/)
 - using beamer: set show notes option accordingly and import with notes in pympress

```latex
\document{beamer}
\usepackage{pgfpages}

%\setbeameroption{hide notes}
\setbeameroption{show notes on second screen=right}
```
