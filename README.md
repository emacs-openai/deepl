<a href="#"><img align="right" src="etc/logo.png" width="20%"></a>
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![JCS-ELPA](https://raw.githubusercontent.com/jcs-emacs/badges/master/elpa/v/deepl.svg)](https://jcs-emacs.github.io/jcs-elpa/#/deepl)

# deepl
> Elisp library for the DeepL API

[![CI](https://github.com/emacs-openai/deepl/actions/workflows/test.yml/badge.svg)](https://github.com/emacs-openai/deepl/actions/workflows/test.yml)

The DeepL Elisp library provides convenient access to the DeepL API from
applications written in the Elips language. 

*P.S. This package is expected to be used as a library, so there are only a few
interactable commands you can use, and those are mostly examples.*

## 📚 Documentation

- [DeepL API docs](https://www.deepl.com/pro-api?cta=header-pro-api/)

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-refresh-toc -->
**Table of Contents**

- [deepl](#deepl)
  - [📚 Documentation](#📚-documentation)
  - [🔨 Usage](#🔨-usage)
    - [🔰 Example](#🔰-example)
  - [🛑 Debugging](#🛑-debugging)
  - [📂 Example projects](#📂-example-projects)
  - [🔗 References](#🔗-references)
  - [🛠️ Contribute](#🛠️-contribute)
    - [🔬 Development](#🔬-development)
  - [⚜️ License](#⚜️-license)

<!-- markdown-toc end -->

## 🔨 Usage

You will need to set up your API key before you can use this library.

```elisp
(setq deepl-key "[YOUR API KEY]")
```

Alternatively, you can configure a function to retrieve the key from some
external source. A function, `deepl-key-auth-source` is provided to retrieve
the key from an auth-source entry under the `:host` key `api.deepl.com`

```elisp
(setq deepl-key #deepl-key-auth-source)
```

For using another DEEPL endpoint, 

```elisp
(setq deepl-base-url "[DEEPL BASE URL]")
```

### 🔰 Example

Here is the simplest example that teaches you how to use this library. This is 
a function with a `text`, `target-lang` and a `callback` function.

```elisp
(deepl-translate "How are you?" "ZH"  ; translate to Chinese
                 (lambda (data)
                   (message "%s" data)))
```

## 🛑 Debugging

While playing through this library, you might see this error quite often.

```
400 - Bad request.  Please check error message and your parameters
```

Try setting the variable `deepl--show-log` to `t`, it will show more error
messages.

## 📂 Example projects

- N/A

## 🔗 References

- [txl.el](https://github.com/tmalsburg/txl.el)

## 🛠️ Contribute

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Elisp styleguide](https://img.shields.io/badge/elisp-style%20guide-purple)](https://github.com/bbatsov/emacs-lisp-style-guide)
[![Donate on paypal](https://img.shields.io/badge/paypal-donate-1?logo=paypal&color=blue)](https://www.paypal.me/jcs090218)
[![Become a patron](https://img.shields.io/badge/patreon-become%20a%20patron-orange.svg?logo=patreon)](https://www.patreon.com/jcs090218)

If you would like to contribute to this project, you may either
clone and make pull requests to this repository. Or you can
clone the project and establish your own branch of this tool.
Any methods are welcome!

### 🔬 Development

To run the test locally, you will need the following tools:

- [Eask](https://emacs-eask.github.io/)
- [Make](https://www.gnu.org/software/make/) (optional)

Install all dependencies and development dependencies:

```sh
$ eask install-deps --dev
```

To test the package's installation:

```sh
$ eask package
$ eask install
```

To test compilation:

```sh
$ eask compile
```

**🪧 The following steps are optional, but we recommend you follow these lint results!**

The built-in `checkdoc` linter:

```sh
$ eask lint checkdoc
```

The standard `package` linter:

```sh
$ eask lint package
```

*📝 P.S. For more information, find the Eask manual at https://emacs-eask.github.io/.*

## ⚜️ License

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.

See [`LICENSE`](./LICENSE.txt) for details.
