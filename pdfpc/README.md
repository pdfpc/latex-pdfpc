# pdfpc

This LaTeX package provides a convenient way to specify notes and to define
certain meta properties of the presentation when used with [PDF Presenter
Console (`pdfpc`)](https://pdfpc.github.io), a GPLv3+ licensed multi-monitor PDF
presentation viewer application available on GitHub.


## Dependencies

The `pdfpc` package depends on these other packages:
[`kvoptions`](https://ctan.org/pkg/kvoptions),
[`xstring`](https://ctan.org/pkg/xstring),
[`iftex`](https://ctan.org/pkg/iftex),
[`hyperxmp`](https://ctan.org/pkg/hyperxmp)

When using LuaTeX, it additionally depends on these packages:
[`stringenc`](https://ctan.org/pkg/stringenc),
[`pdftexcmds`](https://ctan.org/pkg/pdftexcmds)


## Usage

The [PDF Presenter Console](https://pdfpc.github.io) program accepts a variety
of configuration options when started from the command line. (See the *pdfpc(1)*
manual page for details.)

This package allows certain details, such as presentation duration, default
slide transitions, and speaker notes, to be specified within the metadata of the
PDF itself, instead of via the command line. These settings are parsed by the
PDF Presenter Console when the presentation is loaded.

These parameters can be specified as package options, and/or via the `\pdfpcsetup` command.

The following is a simple LaTeX document demonstrating a few example features:

```latex
\documentclass{beamer}
\usepackage[overridenote]{pdfpc}
% "overridenote" must be specified as a package option
\pdfpcsetup{
    % Other settings can be package options, or can go here
    duration=5,
    lastminutes=2,
}

% The usual Beamer document setup
\title{\texttt{pdfpc} Example Presentation}
\author{\texttt{pdfpc} Contributors}
\institute{GitHub}
\date{\today}

\begin{document}
\maketitle

\begin{frame}
    Hello PDFPC World!
    % Because of "overridenote", this uses the pdfpc note command
    \note{This speaker note will be shown by `pdfpc`, but hidden for the audience.}
    \pause
    Notice that the timer starts counting down from 5 minutes, just as we specified in the preamble!
\end{frame}

\end{document}
```


## Documentation

Complete
[documentation](http://mirrors.ctan.org/macros/latex/contrib/pdfpc/pdfpc-doc.pdf)
for the current version of `pdfpc` is availble on [its CTAN
page](https://ctan.org/pkg/pdfpc).
