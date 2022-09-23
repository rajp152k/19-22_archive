---
title: "LSP-mode Clangd Peculiarities"
category: "tools"
tags: [C++, emacs, clangd]
---

### [2021-10-30 Sat 12:38] - 7852

Uniformity is the one thing all tech-aficionados will go out of their way
to achieve. The LSP takes it one step further and makes life easier for
all the polyglots out there.

The [ language server protocol
](https://microsoft.github.io/language-server-protocol/) is a primal
component of any good text-editor based IDE.

Setting up LSP-mode for C++ is slightly different than other languages.
Post the basic
[procedure](https://emacs-lsp.github.io/lsp-mode/tutorials/CPP-guide/),
one will still face errors regarding unidentified header files.

Quoting the [ clangd ](https://clangd.llvm.org/installation.html) docs:
> To understand your source code, clangd needs to know the compiler flags that are used to build the project. (This is just a fact of life in C++, source files are not self-contained).

You'll be redirected to the docs claiming that you need to have a
compilation database in place which could be achieved using some
more tooling (CMake, Bear et cetera). 

But all that is overkill and isn't necessary if you're not working
with a large project with multiple headers and source files.

Moreover, one needs to create the compilation database (`compilation_commands.json`) for each
project separately.

Given you, the reader, are just as lazy as the average power user, you probably
grunt at the idea of setting up a project for one file.

Thankfully, upon further search, you'll read, somewhere insignificant, about a
`compile_flags.txt`.

It'll cover the basics, not letting the meta-stuff bog you down. It's
just a collection of compilation flags that will be passed to the
concerned clang-tooling, enlightening it, with some context.

Executing this in the root of the source tree does the job:

```
--$: cat > compile_flags.txt
--$: -I<path to c++ headers>
```

My `compile_flags.txt` looks like:

```
-I/usr/include/c++/9
-I/usr/include/x86_64-linux-gnu/c++/9
```

The server will take the contextual compilation to be 
```bash
$(CC) -$(FLAGS) <any source file in that dir>.cpp
```

Automating the same into a hook called upon opening a C++ buffer:

``` elisp
(defun clangd-lsp-setup ()
  (interactive)
  ;;check if database already exists
  (let* ((dir default-directory)
	 ;;system specific params
	 (include-path-1 "/usr/include/c++/")
	 (include-path-2 "/usr/include/x86_64-linux-gnu/c++/")
	 (ver (caddr (directory-files include-path-1)))
	 (includes-str (concat "-I" (concat include-path-1 ver) "/\n"
			       "-I" (concat include-path-2 ver) "/\n"))
	 (compilation-db (concat dir "compile_flags.txt")))
    (if (file-exists-p compilation-db)
	(message "compilation database already exists")
      (progn (message "placing a new compilation database")
	     (write-region includes-str nil compilation-db)))))

(general-add-hook 'c++-mode-hook
		  (list#'clangd-lsp-setup))
```

And now, I can get down to business without worrying about the
displeasing red squigglies.

Note the system specific parameters, I use Ubuntu-20.04 (WSL2) with the
kernel being:
```
$: uname -ar
Linux Raj-Y520 5.10.60.1-microsoft-standard-WSL2 #1 SMP Wed Aug 25 23:20:18 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux
```
