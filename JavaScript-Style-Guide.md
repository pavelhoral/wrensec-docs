Based on Google's [JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html), which is licensed under the [CC-BY 3.0 License](https://creativecommons.org/licenses/by/3.0/). _This style guide is provided under the same license._

[![Creative Commons License](https://i.creativecommons.org/l/by/3.0/88x31.png)](https://creativecommons.org/licenses/by/3.0/)

Deviations from / additions to Google's style guide are noted with "Deviation Notes" in context.

Table of Contents generated with [gh-md-toc](https://github.com/ekalinin/github-markdown-toc).

## Table of Contents
* [1. Introduction](#1-introduction)
   * [1.1 Terminology notes](#11-terminology-notes)
   * [1.2 Guide notes](#12-guide-notes)
* [2. Source file basics](#2-source-file-basics)
   * [2.1 File name](#21-file-name)
   * [2.2 File encoding: UTF-8](#22-file-encoding-utf-8)
   * [2.3 Special characters](#23-special-characters)
      * [2.3.1 Whitespace characters](#231-whitespace-characters)
      * [2.3.2 Special escape sequences](#232-special-escape-sequences)
      * [2.3.3 Non-ASCII characters](#233-non-ascii-characters)
* [3. Source file structure](#3-source-file-structure)
   * [3.1 License and copyright information](#31-license-and-copyright-information)
      * [3.1.1 New Files](#311-new-files)
      * [3.1.2 Header Modifications in Existing Files](#312-header-modifications-in-existing-files)
      * [3.1.3 Substantial Contributions from a Third Party](#313-substantial-contributions-from-a-third-party)
   * [3.2 @fileoverview JSDoc, if present](#32-fileoverview-jsdoc-if-present)
   * [3.3 require statements](#33-require-statements)
   * [3.5 The file's implementation](#35-the-files-implementation)
* [4. Formatting](#4-formatting)
   * [4.1 Braces](#41-braces)
      * [4.1.1 Braces are used for all control structures](#411-braces-are-used-for-all-control-structures)
      * [4.1.2 Nonempty blocks: K &amp; R style](#412-nonempty-blocks-k--r-style)
      * [4.1.3 Empty blocks: may be concise](#413-empty-blocks-may-be-concise)
   * [4.2 Block indentation:  4 spaces](#42-block-indentation-4-spaces)
      * [4.2.1 Array literals: optionally block-like](#421-array-literals-optionally-block-like)
      * [4.2.2 Object literals: optionally block-like](#422-object-literals-optionally-block-like)
      * [4.2.3 Class literals](#423-class-literals)
      * [4.2.4 Function expressions](#424-function-expressions)
      * [4.2.5 Switch statements](#425-switch-statements)
   * [4.3 Statements](#43-statements)
      * [4.3.1 One statement per line](#431-one-statement-per-line)
      * [4.3.2 Semicolons are required](#432-semicolons-are-required)
   * [4.4 Column limit: 100 encouraged, and no more than 120](#44-column-limit-100-encouraged-and-no-more-than-120)
   * [4.5 Line-wrapping](#45-line-wrapping)
      * [4.5.1 Where to break](#451-where-to-break)
      * [4.5.2 Indent continuation lines at least  4 spaces](#452-indent-continuation-lines-at-least-4-spaces)
   * [4.6 Whitespace](#46-whitespace)
      * [4.6.1 Vertical whitespace](#461-vertical-whitespace)
      * [4.6.2 Horizontal whitespace](#462-horizontal-whitespace)
      * [4.6.3 Horizontal alignment: discouraged](#463-horizontal-alignment-discouraged)
      * [4.6.4 Function arguments](#464-function-arguments)
   * [4.7 Grouping parentheses: recommended](#47-grouping-parentheses-recommended)
   * [4.8 Comments](#48-comments)
      * [4.8.1 Block comment style](#481-block-comment-style)
* [5. Language features](#5-language-features)
   * [5.1 Local variable declarations](#51-local-variable-declarations)
      * [5.1.1 Use const and <code>let</code>](#511-use-const-and-let)
         * [5.1.2 One variable per declaration, per line](#512-one-variable-per-declaration-per-line)
      * [5.1.3 Declared when needed, initialized as soon as possible](#513-declared-when-needed-initialized-as-soon-as-possible)
      * [5.1.4 Declare types as needed](#514-declare-types-as-needed)
   * [5.2 Array literals](#52-array-literals)
      * [5.2.1 Use trailing commas](#521-use-trailing-commas)
      * [5.2.2 The variadic Array constructor must not be used](#522-the-variadic-array-constructor-must-not-be-used)
      * [5.2.3 Non-numeric properties](#523-non-numeric-properties)
      * [5.2.4 Destructuring](#524-destructuring)
      * [5.2.5 Spread operator](#525-spread-operator)
   * [5.3 Object literals](#53-object-literals)
      * [5.3.1 Use trailing commas](#531-use-trailing-commas)
      * [5.3.2 The Object constructor must not be used](#532-the-object-constructor-must-not-be-used)
      * [5.3.3 Quoted and unquoted keys must not be mixed](#533-quoted-and-unquoted-keys-must-not-be-mixed)
      * [5.3.4 Computed property names](#534-computed-property-names)
      * [5.3.5 Method shorthand](#535-method-shorthand)
      * [5.3.6 Shorthand properties](#536-shorthand-properties)
      * [5.3.7 Destructuring](#537-destructuring)
      * [5.3.8 Enums](#538-enums)
   * [5.4 Classes](#54-classes)
      * [5.4.1 Constructors](#541-constructors)
      * [5.4.2 Fields](#542-fields)
      * [5.4.3 Computed properties](#543-computed-properties)
      * [5.4.4 Static methods](#544-static-methods)
      * [5.4.5 Old-style class declarations](#545-old-style-class-declarations)
      * [5.4.6 Class prototypes should not be manipulated directly](#546-class-prototypes-should-not-be-manipulated-directly)
      * [5.4.7 Getters and Setters](#547-getters-and-setters)
      * [5.4.8 Overriding toString](#548-overriding-tostring)
      * [5.4.9 Interfaces](#549-interfaces)
   * [5.5 Functions](#55-functions)
      * [5.5.1 Top-level functions](#551-top-level-functions)
      * [5.5.2 Nested functions and closures](#552-nested-functions-and-closures)
      * [5.5.3 Arrow functions](#553-arrow-functions)
      * [5.5.4 Generators](#554-generators)
      * [5.5.5 Parameters](#555-parameters)
         * [5.5.5.1 Default parameters](#5551-default-parameters)
         * [5.5.5.2 Rest parameters](#5552-rest-parameters)
      * [5.5.6 Returns](#556-returns)
      * [5.5.7 Generics](#557-generics)
      * [5.5.8 Spread operator](#558-spread-operator)
   * [5.6 String literals](#56-string-literals)
      * [5.6.1 Use single quotes](#561-use-single-quotes)
      * [5.6.2 Template strings](#562-template-strings)
      * [5.6.3 No line continuations](#563-no-line-continuations)
   * [5.7 Number literals](#57-number-literals)
   * [5.8 Control structures](#58-control-structures)
      * [5.8.1 For loops](#581-for-loops)
      * [5.8.2 Exceptions](#582-exceptions)
         * [5.8.2.1 Empty catch blocks](#5821-empty-catch-blocks)
      * [5.8.3 Switch statements](#583-switch-statements)
         * [5.8.3.1 Fall-through: commented](#5831-fall-through-commented)
         * [5.8.3.2 The default case is present](#5832-the-default-case-is-present)
   * [5.9 this](#59-this)
   * [5.10 Disallowed features](#510-disallowed-features)
      * [5.10.1 with](#5101-with)
      * [5.10.2 Dynamic code evaluation](#5102-dynamic-code-evaluation)
      * [5.10.3 Automatic semicolon insertion](#5103-automatic-semicolon-insertion)
      * [5.10.4 Non-standard features](#5104-non-standard-features)
      * [5.10.5 Wrapper objects for primitive types](#5105-wrapper-objects-for-primitive-types)
      * [5.10.6 Modifying built-in objects](#5106-modifying-built-in-objects)
* [6. Naming](#6-naming)
   * [6.1 Rules common to all identifiers](#61-rules-common-to-all-identifiers)
   * [6.2 Rules by identifier type](#62-rules-by-identifier-type)
      * [6.2.1 Package names](#621-package-names)
      * [6.2.2 Class names](#622-class-names)
      * [6.2.3 Method names](#623-method-names)
      * [6.2.4 Enum names](#624-enum-names)
      * [6.2.5 Constant names](#625-constant-names)
         * [6.2.5.1 Definition of "constant"](#6251-definition-of-constant)
         * [6.2.5.1 Local aliases](#6251-local-aliases)
      * [6.2.6 Non-constant field names](#626-non-constant-field-names)
      * [6.2.7 Parameter names](#627-parameter-names)
      * [6.2.8 Local variable names](#628-local-variable-names)
      * [6.2.9 Template parameter names](#629-template-parameter-names)
   * [6.3 Camel case: defined](#63-camel-case-defined)
* [7. JSDoc](#7-jsdoc)
   * [7.1 General form](#71-general-form)
   * [7.2 Markdown](#72-markdown)
   * [7.3 JSDoc tags](#73-jsdoc-tags)
   * [7.4 Line wrapping](#74-line-wrapping)
   * [7.5 Top/file-level comments](#75-topfile-level-comments)
   * [7.6 Class comments](#76-class-comments)
   * [7.7 Enum and typedef comments](#77-enum-and-typedef-comments)
   * [7.8 Method and function comments](#78-method-and-function-comments)
   * [7.9 Property comments](#79-property-comments)
   * [7.10 Type annotations](#710-type-annotations)
      * [7.10.1 Nullability](#7101-nullability)
      * [7.10.2 Type Casts](#7102-type-casts)
      * [7.10.3 Template Parameter Types](#7103-template-parameter-types)
   * [7.11 Visibility annotations](#711-visibility-annotations)
   * [7.12 Deprecation](#712-deprecation)
* [8. Policies](#8-policies)
   * [8.1 Issues unspecified by Wren Style: Be Consistent!](#81-issues-unspecified-by-wren-style-be-consistent)
   * [8.2 Compiler warnings](#82-compiler-warnings)
      * [8.2.1 Use a standard warning set](#821-use-a-standard-warning-set)
      * [8.2.2 How to handle a warning](#822-how-to-handle-a-warning)
      * [8.2.3 Suppress a warning at the narrowest reasonable scope](#823-suppress-a-warning-at-the-narrowest-reasonable-scope)
   * [8.3 Code not in Wren Style](#83-code-not-in-wren-style)
      * [8.3.1 Reformatting existing code](#831-reformatting-existing-code)
      * [8.3.2 Newly added code: use Wren Style](#832-newly-added-code-use-wren-style)
   * [8.4 Generated code: mostly exempt](#84-generated-code-mostly-exempt)
* [9. Appendices](#9-appendices)
   * [9.1 JSDoc tag reference](#91-jsdoc-tag-reference)
   * [9.3 Style-related tools](#93-style-related-tools)
      * [9.3.1 The Google Closure Compiler](#931-the-google-closure-compiler)
      * [9.3.2 clang-format](#932-clang-format)
      * [9.3.3 The Google Closure compiler linter](#933-the-google-closure-compiler-linter)
      * [9.3.4 Conformance framework](#934-conformance-framework)
   * [9.4 Exceptions for legacy platforms](#94-exceptions-for-legacy-platforms)
      * [9.4.1 Overview](#941-overview)
      * [9.4.2 Use var](#942-use-var)
         * [9.4.2.1 var declarations are NOT block-scoped](#9421-var-declarations-are-not-block-scoped)
         * [9.4.2.2 Declare variables as close as possible to first use](#9422-declare-variables-as-close-as-possible-to-first-use)
         * [9.4.2.3 Use @const for constants variables](#9423-use-const-for-constants-variables)
      * [9.4.3 Do not use block scoped functions declarations](#943-do-not-use-block-scoped-functions-declarations)

## 1. Introduction
This document serves as the **complete** definition of Wren Security's coding standards for source code in the JavaScript programming language. A JavaScript source file is described as being _in Wren Style_ if and only if it adheres to the rules herein.

Like other programming style guides, the issues covered span not only aesthetic issues of formatting, but other types of conventions or coding standards as well. However, this document focuses primarily on the hard-and-fast rules that we follow universally, and avoids giving advice that isn't clearly enforceable (whether by human or tool).

### 1.1 Terminology notes
In this document, unless otherwise clarified:

1. The term _comment_ always refers to _implementation_ comments. We do not use the phrase documentation comments, instead using the common term "JSDoc" for both human-readable text and machine-readable annotations within `/** ... */`.
    
2. This Style Guide uses [RFC 2119](http://tools.ietf.org/html/rfc2119) terminology when using the phrases _must_, _must not_, _should_, _should not_, and _may_. The terms _prefer_ and _avoid_ correspond to _should_ and _should not_, respectively. Imperative and declarative statements are prescriptive and correspond to _must_.

Other terminology notes will appear occasionally throughout the document.

> **Deviation Note:** This style guide has been modified to follow RFC 2119 more closely. Google's original JavaScript Style Guide indicates that it follows RFC 2119, but many sections did not consistently apply terminology from the RFC.

### 1.2 Guide notes
Example code in this document is **non-normative**. That is, while the examples are in Wren Style, they may not illustrate the _only_ stylish way to represent the code. Optional formatting choices made in examples must not be enforced as rules.

## 2. Source file basics
### 2.1 File name
File names must be all lowercase and may include underscores (`_`) or dashes (`-`), but no additional punctuation. Follow the convention that your project uses. Filenames' extension must be `.js`.

### 2.2 File encoding: UTF-8
Source files must be encoded in **UTF-8**.

### 2.3 Special characters
#### 2.3.1 Whitespace characters
Aside from the line terminator sequence, the ASCII horizontal space character (`0x20`) is the only whitespace character that may appear anywhere in a source file. This implies that

1. All other whitespace characters in string literals are escaped, and    
2. Tab characters are **not** used for indentation.

#### 2.3.2 Special escape sequences
For any character that has a special escape sequence (`\'`, `\"`, `\\`, `\b`, `\f`, `\n`, `\r`, `\t`, `\v`), that sequence must be used rather than the corresponding numeric escape (e.g `\x0a`, `\u000a`, or `\u{a}`). Legacy octal escapes are never used.

#### 2.3.3 Non-ASCII characters
For the remaining non-ASCII characters, either the actual Unicode character (e.g. `∞`) or the equivalent hex or Unicode escape (e.g. `\u221e`) must be used, depending only on which makes the code **easier to read and understand**.

> **Tip:** In the Unicode escape case, and occasionally even when actual Unicode characters are used, an explanatory comment can be very helpful.

| Example                                                  | Discussion                                                                |
| -------------------------------------------------------- | ------------------------------------------------------------------------- |
| `const units = 'μs';`                                    | Best: perfectly clear even without a comment.                             |
| `const units = '\u03bcs'; // 'μs'`                       | Allowed, but there's no reason to do this.                                |
| `const units = '\u03bcs'; // Greek letter mu, 's'`       | Allowed, but awkward and prone to mistakes.                               |
| `const units = '\u03bcs';`                               | Poor: the reader has no idea what this is.                                |
| `return '\ufeff' + content; // byte order mark`          | Good: use escapes for non-printable characters, and comment if necessary. |

> **Tip:** Never make your code less readable simply out of fear that some programs might not handle non-ASCII characters properly. If that happens, those programs are **broken** and they must be **fixed**.

## 3. Source file structure
A source file consists of, **in order**:

1. License and copyright information
2. `@fileoverview` JSDoc, if present
3. `require` statements
5.  The file's implementation

**Exactly one blank line** must separate each section that is present, except the file's implementation, which may be preceded by 1 or 2 blank lines.

> **Deviation Note:** Compared to Google's JavaScript Style Guide, in this style guide, Google-specific guidance related to `goog.module` and `goog.require` have been removed, and replaced with more general advice pertaining to CommonJS `require` functionality. In addition the original section 3.3 in the original guide has been removed from this style guide.

### 3.1 License and copyright information
[CDDL license](/WrenSecurity/wrensec-docs/wiki/CDDL-1.1-License) and copyright information belongs here in the source file. 

> **Deviation Note:** This section of the style guide notably differs from Google's JavaScript Style Guide: in this style guide, a license and copyright header are **mandatory**, and must adhere to the CDDL.

#### 3.1.1 New Files
All new JavaScript source files added to Wren Security projects must have a [CDDL license](/WrenSecurity/wrensec-docs/wiki/CDDL-1.1-License) header, which includes a copyright line. The header must have the following format:

```JavaScript
/*
 * The contents of this file are subject to the terms of the Common Development and
 * Distribution License (the License). You may not use this file except in compliance with the
 * License.
 *
 * You can obtain a copy of the License at legal/CDDLv1.1.txt. See the License for the
 * specific language governing permission and limitations under the License.
 *
 * When distributing Covered Software, include this CDDL Header Notice in each file and include
 * the License file at legal/CDDLv1.1.txt. If applicable, add the following below the CDDL
 * Header, with the fields enclosed by brackets [] replaced by your own identifying
 * information: "Portions copyright [year] [name of copyright owner]".
 *
 * [COPYRIGHT LINES]
 */
```

The copyright line of a new source file should read "Copyright YEAR Wren Security. All rights reserved." `YEAR` must indicate the year that the file was first created.

#### 3.1.2 Header Modifications in Existing Files
To ensure compliance with [the CDDL license](/WrenSecurity/wrensec-docs/wiki/CDDL-1.1-License), contributors must adhere to the following guidelines:
- Never remove a copyright line. Ever. No matter how small the original contribution was, the owner of the contribution must be acknowledged.

- Older source files may have a CDDL header of a slightly different format than that shown above in [section 3.1.1](#311-new-files). You may update the format of the header in these files to match the new format, but *the copyright notices in the header &ndash; including the years of effect and name of each copyright owner &ndash; must be preserved.*.

- Formatting changes to copyright lines &ndash; even to make those lines consistent with the style of other lines in the same file or other files &ndash; are discouraged and should not be made, unless the party making the formatting change claims ownership of the affected copyright notice (e.g. Wren Security can change the formatting of our own copyright lines, but should not change the formatting of ForgeRock copyright lines).

- When modifying a source file, the line "Portions Copyright YEAR Wren Security." should be added below other copyright lines &ndash; unless a similar line already  exists, in which case it should be updated. YEAR must indicate the years of the contributions. For example, if the source file was first modified in 2017 and then again in 2019, the line should read "Portions Copyright 2017-2019 Wren Security."

#### 3.1.3 Substantial Contributions from a Third Party
Third-party organizations who are contributing a new feature and/or re-factoring an existing feature may use a CDDL copyright line that credits their own organization instead of the Wren Security organization, so long as the changes being contributed span three or more source files. Otherwise, single-file contributions should credit "Wren Security" as the copyright owner.

This guideline helps to ensure that copyright headers do not become burdened with dozens of copyright claims for seemingly-minor changes.

### 3.2 `@fileoverview` JSDoc, if present

See [7.5 Top/file-level comments](#75-top-file-level-comments) for formatting rules.

### 3.3 `require` statements
Imports must be done with `require` statements, which must be grouped together immediately following the module declaration. Each `require` must be assigned to a single constant alias, or else must be destructured into several constant aliases. These aliases are the only acceptable way to refer to the `require`d dependency, whether in code or in type annotations: the fully qualified name is never used except as the argument to `require`. Alias names should match the final dot-separated component of the imported module name when possible, though additional components may be included (with appropriate casing such that the alias' casing still correctly identifies its type) if necessary to disambiguate, or if it significantly improves readability. `require` statements may not appear anywhere else in the file.

If a module is imported only for its side effects, the assignment may be omitted, but the fully qualified name may not appear anywhere else in the file. A comment is required to explain why this is needed and suppress a compiler warning.

The lines must be sorted according to the following rules: All requires with a name on the left hand side must come first, sorted alphabetically by those names. These must be followed by destructuring requires, which must again be sorted by the names on the left hand side. Finally, these must be followed by any `require` calls that are standalone (generally these are for modules imported just for their side effects).

> **Tip:** There's no need to memorize this order and enforce it manually. You can rely on your IDE to report requires that are not sorted correctly.

If a long alias or module name would cause a line to exceed the 120-column limit, it **must not** be wrapped: `require` lines are an exception to the 120-column limit.

Example:

```js
const MyClass = require('some.package.MyClass');
const NsMyClass = require('other.ns.MyClass');
const googAsserts = require('asserts');
const testingAsserts = require('testing.asserts');
const than80columns = require('pretend.this.is.longer.than80columns');
const {clear, forEach, map} = require('array');
/** @suppress {extraRequire} Initializes MyFramework. */
require('my.framework.initialization');

```

Illegal:

```js
const randomName = require('something.else'); // name must match

const {clear, forEach, map} = // don't break lines
    require('array');

function someFunction() {
    const alias = require('my.long.name.alias'); // must be at top level
    // ...
}
```

> **Deviation Note:** This section of the style guide notably differs from Google's JavaScript Style Guide: in this style guide, the absolute limit has been raised to 120 characters. This is maintain consistency with the vast majority of code that Wren Security has inherited from ForgeRock, especially given that the block indent for our is [twice as long](#42-block-indentation-4-spaces) as Google's standard indent.

### 3.5 The file's implementation
The actual implementation follows after all dependency information is declared (separated by at least one blank line).

This may consist of any module-local declarations (constants, variables, classes, functions, etc), as well as any exported symbols.

## 4. Formatting
> **Terminology Note**: _block-like construct_ refers to the body of a class, function, method, or brace-delimited block of code. Note that, by [5.2 Array literals](#52-array-literals) and [5.3 Object literals](#53-object-literals), any array or object literal may optionally be treated as if it were a block-like construct.

> **Tip:** Use `clang-format`. The JavaScript community has invested effort to make sure clang-format does the right thing on JavaScript files. `clang-format` has integration with several popular editors.

### 4.1 Braces
#### 4.1.1 Braces are used for all control structures
Braces must be used for all control structures (i.e. `if`, `else`, `for`, `do`, `while`, as well as any others), even if the body contains only a single statement. The first statement of a non-empty block must begin on its own line.

Illegal:
```js
if (someVeryLongCondition())
    doSomething();

for (let i = 0; i < foo.length; i++) bar(foo[i]);
```

**Exception**: A simple `if` statement that can fit entirely on a single line with no wrapping (and that doesn't have an else) may be kept on a single line with no braces when it improves readability. This is the only case in which a control structure may omit braces and newlines.

```js
if (shortCondition()) return;
```

#### 4.1.2 Nonempty blocks: K & R style
Braces follow the Kernighan and Ritchie style ([Egyptian brackets](http://www.codinghorror.com/blog/2012/07/new-programming-jargon.html)) for _nonempty_ blocks and block-like constructs:
* A line break must not appear before the opening brace.
* A line break must appear after the opening brace.
* A line break must appear before the closing brace.
* A line break must appear after the closing brace, _only if_ terminates a statement or the body of a function or class statement, or a class method. Specifically, there must be _no_ line break after the brace if it is followed by `else`, `catch`, `while`, or a comma, semicolon, or right-parenthesis.

Example:
```js
class InnerClass {
    constructor() {}

    /** @param {number} foo */
    method(foo) {
        if (condition(foo)) {
            try {
                // Note: this might fail.
                something();
            } catch (err) {
                recover();
            }
        }
    }
}
```

#### 4.1.3 Empty blocks: may be concise
An empty block or block-like construct _may_ be closed immediately after it is opened, with no characters, space, or line break in between (i.e. `{}`), **unless** it is a part of a _multi-block statement_ (one that directly contains multiple blocks: `if`/`else` or `try`/`catch`/`finally`).

Example:
```js
function doNothing() {}
```

Illegal:
```js
if (condition) {
    // ...
} else if (otherCondition) {} else {
    // ...
}

try {
    // ...
} catch (e) {}
```

### 4.2 Block indentation: +4 spaces
Each time a new block or block-like construct is opened, the indent must increase by four spaces. When the block ends, the indent must return to the previous indent level. The indent level must apply to both code and comments throughout the block. (See the example in [4.1.2 Nonempty blocks: K&R style](#412-nonempty-blocks-k--r-style)).

> **Deviation Note:** This section of the style guide notably differs from Google's JavaScript Style Guide: in this style guide, four spaces instead of two spaces are used for indentation. This is to maintain consistency with the vast majority of code that Wren Security has inherited from ForgeRock.

#### 4.2.1 Array literals: optionally block-like
Any array literal may optionally be formatted as if it were a "block-like construct." For example, the following are all valid (**not** an exhaustive list):

```js
const a = [
    0,
    1,
    2,
];
```
```js
const b =
    [0, 1, 2];
```
```js
const c = [0, 1, 2];

someMethod(foo, [
    0, 1, 2,
], bar);
```

Other combinations are allowed, particularly when emphasizing semantic groupings between elements, but should not be used only to reduce the vertical size of larger arrays.

#### 4.2.2 Object literals: optionally block-like
Any object literal may optionally be formatted as if it were a "block-like construct." The same examples apply as [4.2.1 Array literals: optionally block-like](#421-array-literals-optionally-block-like). For example, the following are all valid (**not** an exhaustive list):

```js
const a = {
    a: 0,
    b: 1,
};
```
```js
const b =
    {a: 0, b: 1};
```
```js
const c = {a: 0, b: 1};

someMethod(foo, {
    a: 0, b: 1,
}, bar);
```

#### 4.2.3 Class literals
Class literals (whether declarations or expressions) must be indented as blocks. Semicolons must not be added after methods, or after the closing brace of a class _declaration_ (statements &ndash; such as assignments &ndash; that contain class _expressions_ are still terminated with a semicolon). You must use the `extends` keyword, but not the `@extends` JSDoc annotation, unless the class extends a templatized type.

Example:
```js
class Foo {
    constructor() {
        /** @type {number} */
        this.x = 42;
    }

    /** @return {number} */
    method() {
        return this.x;
    }
}
Foo.Empty = class {};
```
```js
/** @extends {Foo<string>} */
foo.Bar = class extends Foo {
    /** @override */
    method() {
        return super.method() / 2;
    }
};
```
```js
/** @interface */
class Frobnicator {
    /** @param {string} message */
    frobnicate(message) {}
}

```
#### 4.2.4 Function expressions
When declaring an anonymous function in the list of arguments for a function call, the body of the function must be indented four spaces more than the preceding indentation depth.

Example:
```js
prefix.something.reallyLongFunctionName('whatever', (a1, a2) => {
    // Indent the function body +4 relative to indentation depth
    // of the 'prefix' statement one line above.
    if (a1.equals(a2)) {
        someOtherLongFunctionName(a1);
    } else {
        andNowForSomethingCompletelyDifferent(a2.parrot);
    }
});

some.reallyLongFunctionCall(arg1, arg2, arg3)
    .thatsWrapped()
    .then((result) => {
        // Indent the function body +4 relative to the indentation depth
        // of the '.then()' call.
        if (result) {
            result.use();
        }
    });
```

> **Deviation Note:** This section of the style guide notably differs from Google's JavaScript Style Guide: in this style guide, four spaces instead of two spaces are used for indentation. This is to maintain consistency with the vast majority of code that Wren Security has inherited from ForgeRock.

#### 4.2.5 Switch statements
As with any other block, the contents of a switch block must be indented +4.

Each switch label must be followed by a newline, and the indentation level must be increased +4, exactly as if a block were being opened. An explicit block may be used if required by lexical scoping. The following switch label must return to the previous indentation level, as if a block had been closed.

A blank line may optionally appear between a `break` and the following case.

Example:
```js
switch (animal) {
    case Animal.BANDERSNATCH:
        handleBandersnatch();
        break;

    case Animal.JABBERWOCK:
        handleJabberwock();
        break;

    default:
        throw new Error('Unknown animal');
}
```

> **Deviation Note:** This section of the style guide notably differs from Google's JavaScript Style Guide: in this style guide, four spaces instead of two spaces are used for indentation. This is to maintain consistency with the vast majority of code that Wren Security has inherited from ForgeRock.

### 4.3 Statements
#### 4.3.1 One statement per line
Each statement must be followed by a line-break.

#### 4.3.2 Semicolons are required
Every statement must be terminated with a semicolon. Relying on automatic semicolon insertion is forbidden.

### 4.4 Column limit: 100 encouraged, and no more than 120
Where possible, JavaScript code should strive for a column limit of 100 characters, and must not exceed 120 characters. A column limit is important, regardless of the fact that modern developers have wider screen monitors capable of 160, 240, or even 320+ characters of text on screen at a single time. Consider that contributions to Wren Security projects typically are submitted through GitHub pull requests, to be reviewed and quality checked by project maintainers. Without a character limit, it is cumbersome and error-prone for reviewers to examine differences in source files that don't fit on-screen, side-by-side, on a modern laptop screen. No one wants a security defect to slip in and go unnoticed as a result of an easily-correctable formatting issue.

A "character" means any Unicode code point. Except as noted below, any line that would exceed this limit must be line-wrapped, as explained in [4.5 Line-wrapping](#45-line-wrapping).

Each Unicode code point counts as one character, even if its display width is greater or less. For example, if using [fullwidth characters](https://en.wikipedia.org/wiki/Halfwidth_and_fullwidth_forms), you may choose to wrap the line earlier than where this rule strictly requires.

**Exceptions:**
1. Lines where obeying the column limit is not possible (for example, a long URL in JSDoc or a shell command intended to be copied-and-pasted).
2. `require` statements (see [3.3 `require` statements](#33-require-statements)).

> **Deviation Note:** This section of the style guide notably differs from Google's JavaScript Style Guide: in this style guide, a 100-character limit is merely encouraged but not required, while the absolute limit has been raised to 120 characters. This is maintain consistency with the vast majority of code that Wren Security has inherited from ForgeRock, especially given that the block indent for our is [twice as long](#42-block-indentation-4-spaces) as Google's standard indent.

### 4.5 Line-wrapping
> **Terminology Note**: _Line-wrapping_ is defined as breaking a single expression into multiple lines.

There is no comprehensive, deterministic formula showing _exactly_ how to line-wrap in every situation. Very often there are several valid ways to line-wrap the same piece of code.

Note: While the typical reason for line-wrapping is to avoid overflowing the column limit, even code that would in fact fit within the column limit may be line-wrapped at the author's discretion.

> Tip: Extracting a method or local variable may solve the problem without the need to line-wrap.

#### 4.5.1 Where to break
The prime directive of line-wrapping is: prefer to break at a **higher syntactic level**.

Preferred:
```js
currentEstimate =
    calc(currentEstimate + x * currentEstimate) /
        2.0f;
```

Discouraged:
```js
currentEstimate = calc(currentEstimate + x *
    currentEstimate) / 2.0f;
```

In the preceding example, the syntactic levels from highest to lowest are as follows: assignment, division, function call, parameters, number constant.

Operators must be wrapped as follows:
1. When a line is broken at an operator, the break must come after the symbol. (Note that this is not the same practice used in Wren style for Java.)
    1.  This must not apply to the dot (`.`), which is not actually an operator.
2. A method or constructor name must stay attached to the open parenthesis (`(`) that follows it.
3. A comma (`,`) must stay attached to the token that precedes it.

> Note: The primary goal for line wrapping should be to have clear code, not necessarily code that fits in the smallest number of lines.

#### 4.5.2 Indent continuation lines at least +4 spaces
When line-wrapping, each line after the first (each _continuation line_) must be indented at least +4 from the original line, unless it falls under the rules of block indentation.

When there are multiple continuation lines, indentation may be varied beyond +4 as appropriate. In general, continuation lines at a deeper syntactic level should be indented by larger multiples of 4, and two lines may use the same indentation level _if and only if_ they begin with syntactically parallel elements.

[4.6.3 Horizontal alignment: discouraged](#463-horizontal-alignment-discouraged) addresses the discouraged (but acceptable) practice of using a variable number of spaces to align certain tokens with previous lines.

> **Deviation Note:** This section of the style guide has additional clarifications not present in Google's JavaScript Style Guide.

### 4.6 Whitespace
#### 4.6.1 Vertical whitespace
A single blank line must appear:
1. Between consecutive methods in a class or object literal
    1.  Exception: A blank line between two consecutive property definitions in an object literal (with no other code between them) is optional. Such blank lines may be used as needed to create _logical groupings_ of fields.
2. Within method bodies, sparingly to create _logical groupings_ of statements. Blank lines at the start or end of a function body are not allowed.
3. _Optionally_ before the first or after the last method in a class or object literal (neither encouraged nor discouraged).
4. As required by other sections of this document (e.g. [3.3 `require` statements](#33-require-statements)).

_Multiple_ consecutive blank lines are permitted, but must not be required (nor encouraged).

#### 4.6.2 Horizontal whitespace
Use of horizontal whitespace depends on location, and falls into three broad categories: _leading_ (at the start of a line), _trailing_ (at the end of a line), and _internal_. Leading whitespace (i.e., indentation) is addressed elsewhere. Trailing whitespace is forbidden.

Beyond where required by the language or other style rules, and apart from literals, comments, and JSDoc, a single internal ASCII space must appear in the following places **only**.

1. Separating any reserved word (such as `if`, `for`, or `catch`) from an open parenthesis (`(`) that follows it on that line.
2. Separating any reserved word (such as `else` or `catch`) from a closing curly brace (`}`) that precedes it on that line.
3. Before any open curly brace (`{`), with two exceptions:
    1.  Before an object literal that is the first argument of a function or the first element in an array literal (e.g. `foo({a: [{c: d}]})`).
    2.  In a template expansion, as it is forbidden by the language (e.g. `abc${1 + 2}def`).
4. On both sides of any binary or ternary operator.
5. After a comma (`,`) or semicolon (`;`). Note that spaces are _never_ allowed before these characters.
6. After the colon (`:`) in an object literal.
7. On both sides of the double slash (`//`) that begins an end-of-line comment. Here, multiple spaces are allowed, but not required.
8. After an open-JSDoc comment character and on both sides of close characters (e.g. for short-form type declarations or casts: `this.foo = /** @type {number} */ (bar);` or `function(/** string */ foo) {`).

#### 4.6.3 Horizontal alignment: discouraged
> **Terminology Note**: _Horizontal alignment_ is the practice of adding a variable number of additional spaces in your code with the goal of making certain tokens appear directly below certain other tokens on previous lines.

This practice is permitted, but it is **generally discouraged** by Wren Style. It is not even required to _maintain_ horizontal alignment in places where it was already used.

Here is an example without alignment, followed by one with alignment. Both are allowed, but the latter is discouraged:

```js
{
  tiny: 42, // this is great
  longer: 435, // this too
};
```
```js
{
  tiny:   42,  // permitted, but future edits
  longer: 435, // may leave it unaligned
};
```

> **Tip:** Alignment can aid readability, but it creates problems for future maintenance. Consider a future change that needs to touch just one line. This change may leave the formerly-pleasing formatting mangled, and that is allowed. More often it prompts the coder (perhaps you) to adjust whitespace on nearby lines as well, possibly triggering a cascading series of reformattings. That one-line change now has a blast radius. This can at worst result in pointless busywork, but at best it still corrupts version history information, slows down reviewers and exacerbates merge conflicts.

#### 4.6.4 Function arguments
Prefer to put all function arguments on the same line as the function name. If doing so would exceed the 120-column limit, the arguments must be line-wrapped in a readable way. To save space, you may wrap as close to 120 as possible, or put each argument on its own line to enhance readability. Indentation should be four spaces. Aligning to the parenthesis is allowed, but discouraged. Below are the most common patterns for argument wrapping:

```js
// Arguments start on a new line, indented four spaces. Preferred when the
// arguments don't fit on the same line with the function name (or the keyword
// "function") but fit entirely on the second line. Works with very long
// function names, survives renaming without reindenting, low on space.
doSomething(
    descriptiveArgumentOne, descriptiveArgumentTwo, descriptiveArgumentThree) {
    // ...
}

// If the argument list is longer, wrap at 120. Uses less vertical space,
// but violates the rectangle rule and is thus not recommended.
doSomething(veryDescriptiveArgumentNumberOne, veryDescriptiveArgumentTwo,
    tableModelEventHandlerProxy, artichokeDescriptorAdapterIterator) {
    // ...
}

// Four-space, one argument per line.  Works with long function names,
// survives renaming, and emphasizes each argument.
doSomething(
    veryDescriptiveArgumentNumberOne,
    veryDescriptiveArgumentTwo,
    tableModelEventHandlerProxy,
    artichokeDescriptorAdapterIterator) {
    // ...
}
```

> **Deviation Note:** This section of the style guide notably differs from Google's JavaScript Style Guide: in this style guide, the absolute limit has been raised to 120 characters. This is maintain consistency with the vast majority of code that Wren Security has inherited from ForgeRock, especially given that the block indent for our is [twice as long](#42-block-indentation-4-spaces) as Google's standard indent.

### 4.7 Grouping parentheses: recommended
Optional grouping parentheses may only be omitted when the author and reviewer agree that there is no reasonable chance that the code will be misinterpreted without them, nor would they have made the code easier to read. It is _not_ reasonable to assume that every reader has the entire operator precedence table memorized.

Unnecessary parentheses must not appear around the entire expression following `delete`, `typeof`, `void`, `return`, `throw`, `case`, `in`, `of`, or `yield`.

Parentheses must be used for type casts: `/** @type {!Foo} */ (foo)`.

### 4.8 Comments
This section addresses _implementation comments_. JSDoc is addressed separately in [7 JSDoc](#7-jsdoc).

#### 4.8.1 Block comment style
Block comments must be indented at the same level as the surrounding code. They may be in `/* ... */` or `//`-style. 

For multi-line `/* ... */` comments, subsequent lines must start with `*` aligned with the `*` on the previous line, to make comments obvious with no extra context. "Parameter name" comments should appear after values whenever the value and method name do not sufficiently convey the meaning.

```js
/*
 * This is
 * okay.
 */
```
```js 
// And so
// is this.
```
```js
/* This is fine, too. */
```
```js
someFunction(obviousParam, true /* shouldRender */, 'hello' /* name */);
```

Comments should not be enclosed in boxes drawn with asterisks or other characters.

JSDoc (`/** ... */`) must not be used for any of the above implementation comments.

## 5. Language features
JavaScript includes many dubious (and even dangerous) features. This section delineates which features may or may not be used, and any additional constraints on their use.

### 5.1 Local variable declarations
#### 5.1.1 Use `const` and `let`
All local variables must be declared with either `const` or `let`. `const` should be used by default, unless a variable needs to be reassigned. The `var` keyword must not be used.

##### 5.1.2 One variable per declaration, per line
Every local variable declaration declares only one variable per line: declarations such as `let a = 1, b = 2;` are not used.

**Exception:** when the name of each variable is on its own line.

Examples:
```js
    // This is acceptable
    let x = 1;
    let y = 2;
```

```js
    // This is equally acceptable
    let x = 1,
        y = 2;
```

```js
    // This is not acceptable: multiple variables are declared on the same line
    let x = 1, y = 2;
```

> **Deviation Note:** This section of the style guide is more permissive than the same section in Google's JavaScript Style Guide. Multiple variables can share the same definition if the variable names appear on separate lines.

#### 5.1.3 Declared when needed, initialized as soon as possible
Local variables should **not** be habitually declared at the start of their containing block or block-like construct. Instead, local variables should be declared close to the point they are first used (within reason), to minimize their scope.

One shortcoming of declaring local variables as they are needed, rather than at the top of a block, is that it can lead to longer methods. Consider that when variables are declared at the top, long methods would cause a developer to frequently have to scroll between the declaration of a variable and its use; that is not the case when variables are declared as they are needed. Nevertheless, strive to keep methods just as short and limited in complexity as you would if all variables _were_ declared at the start of the block.

> **Deviation Note:** This section of the style guide provides additional guidance about long methods than Google's JavaScript Style Guide. 

#### 5.1.4 Declare types as needed
JSDoc type annotations may be added either on the line above the declaration, or else inline before the variable name.

Example:
```js
const /** !Array<number> */ data = [];

/** @type {!Array<number>} */
const data = [];
```

> **Tip:** There are many cases where the compiler can infer a templatized type but not its parameters. This is particularly the case when the initializing literal or constructor call does not include any values of the template parameter type (e.g., empty arrays, objects, `Map`s, or `Set`s), or if the variable is modified in a closure. Local variable type annotations are particularly helpful in these cases since otherwise the compiler will infer the template parameter as unknown.

### 5.2 Array literals
#### 5.2.1 Use trailing commas
A trailing comma must be included whenever there is a line break between the final element and the closing bracket.

Example:

```js
const values = [
  'first value',
  'second value',
];
```

#### 5.2.2 The variadic `Array` constructor must not be used
The constructor is error-prone if arguments are added or removed. Use a literal instead.

Illegal:
```js
const a1 = new Array(x1, x2, x3);
const a2 = new Array(x1, x2);
const a3 = new Array(x1);
const a4 = new Array();
```

This works as expected except for the third case: if `x1` is a whole number then `a3` is an array of size `x1` where all elements are `undefined`. If `x1` is any other number, then an exception will be thrown, and if it is anything else then it will be a single-element array.

Instead, write:
```js
const a1 = [x1, x2, x3];
const a2 = [x1, x2];
const a3 = [x1];
const a4 = [];

```
Explicitly allocating an array of a given length using `new Array(length)` is allowed when appropriate.

#### 5.2.3 Non-numeric properties
Non-numeric properties on an array (other than `length`) must not be defined or used. A `Map` (or `Object`) should be used instead.

#### 5.2.4 Destructuring
Array literals may be used on the left-hand side of an assignment to perform destructuring (such as when unpacking multiple values from a single array or iterable). A final rest element may be included (with no space between the `...` and the variable name). Elements should be omitted if they are unused.

```js
const [a, b, c, ...rest] = generateResults();
let [, b,, d] = someArray;
```

Destructuring may also be used for function parameters (note that a parameter name is required but ignored). `[]` must be specified as the default value if a destructured array parameter is optional, and default values must be provided on the left hand side:

```js
/** @param {!Array<number>=} param1 */
function optionalDestructuring([a = 4, b = 2] = []) { ... };
```

Illegal:
```js
function badDestructuring([a, b] = [4, 2]) { ... };
```

> **Tip:** For (un)packing multiple values into a function's parameter or return, prefer object destructuring to array destructuring when possible, as it allows naming the individual elements and specifying a different type for each.

#### 5.2.5 Spread operator
Array literals may include the spread operator (`...`) to flatten elements out of one or more other iterables. The spread operator should be used instead of more awkward constructs with `Array.prototype`. There is no space after the `...`.

Example:
```js
[...foo]   // preferred over Array.prototype.slice.call(foo)
[...foo, ...bar]   // preferred over foo.concat(bar)
```

### 5.3 Object literals
#### 5.3.1 Use trailing commas
A trailing comma must be included whenever there is a line break between the final property and the closing brace.

#### 5.3.2 The `Object` constructor must not be used
While `Object` does not have the same problems as `Array`, it is still disallowed for consistency. An object literal (`{}` or `{a: 0, b: 1, c: 2}`) should be used instead.

#### 5.3.3 Quoted and unquoted keys must not be mixed 
Object literals may represent either _structs_ (with unquoted keys and/or symbols) or _dicts_ (with quoted and/or computed keys). These key types must not be mixed in a single object literal.

Illegal:
```js
{
  a: 42, // struct-style unquoted key
  'b': 43, // dict-style quoted key
}
```

#### 5.3.4 Computed property names
Computed property names (e.g., `{['key' + foo()]: 42}`) are allowed, and are considered dict-style (quoted) keys (i.e., must not be mixed with non-quoted keys) unless the computed property is a symbol (e.g., `[Symbol.iterator]`). Enum values may also be used for computed keys, but should not be mixed with non-enum keys in the same literal.

#### 5.3.5 Method shorthand
Methods may be defined on object literals using the method shorthand (`{method() {... }}`) in place of a colon immediately followed by a `function` or arrow function literal.

Example:
```js
return {
  stuff: 'candy',
  method() {
    return this.stuff;  // Returns 'candy'
  },
};
```

Note that `this` in a method shorthand or `function` refers to the object literal itself whereas `this` in an arrow function refers to the scope outside the object literal.

Example:
```js
class {
  getObjectLiteral() {
    this.stuff = 'fruit';
    return {
      stuff: 'candy',
      method: () => this.stuff,  // Returns 'fruit'
    };
  }
}
```

#### 5.3.6 Shorthand properties
Shorthand properties are allowed on object literals.

Example:
```js
const foo = 1;
const bar = 2;
const obj = {
  foo,
  bar,
  method() { return this.foo + this.bar; },
};
assertEquals(3, obj.method());
```

#### 5.3.7 Destructuring
Object destructuring patterns may be used on the left-hand side of an assignment to perform destructuring and unpack multiple values from a single object.

Destructured objects may also be used as function parameters, but should be kept as simple as possible: a single level of unquoted shorthand properties. Deeper levels of nesting and computed properties may not be used in parameter destructuring. Specify any default values in the left-hand-side of the destructured parameter (`{str = 'some default'} = {}`, rather than `{str} = {str: 'some default'}`), and if a destructured object is itself optional, it must default to `{}`. The JSDoc for the destructured parameter may be given any name (the name is unused but is required by the compiler).

Example:

```js
/**
 * @param {string} ordinary
 * @param {{num: (number|undefined), str: (string|undefined)}=} param1
 *     num: The number of times to do something.
 *     str: A string to do stuff to.
 */
function destructured(ordinary, {num, str = 'some default'} = {})
```

Illegal:
```js
/** @param {{x: {num: (number|undefined), str: (string|undefined)}}} param1 */
function nestedTooDeeply({x: {num, str}}) {};
/** @param {{num: (number|undefined), str: (string|undefined)}=} param1 */
function nonShorthandProperty({num: a, str: b} = {}) {};
/** @param {{a: number, b: number}} param1 */
function computedKey({a, b, [a + b]: c}) {};
/** @param {{a: number, b: string}=} param1 */
function nontrivialDefault({a, b} = {a: 2, b: 4}) {};
```

Destructuring may also be used for `require` statements, and in this case must not be wrapped: the entire statement occupies one line, regardless of how long it is (see [3.3 `require` statements](#33-require-statements)).

#### 5.3.8 Enums
Enumerations must be defined by adding the `@enum` annotation to an object literal. Additional properties may not be added to an enum after it is defined. Enums must be constant, and all enum values must be deeply immutable.

```js
/**
 * Supported temperature scales.
 * @enum {string}
 */
const TemperatureScale = {
    CELSIUS: 'celsius',
    FAHRENHEIT: 'fahrenheit',
};

/**
 * An enum with two options.
 * @enum {number}
 */
const Option = {
    /** The option used shall have been the first. */
    FIRST_OPTION: 1,
    /** The second among two options. */
    SECOND_OPTION: 2,
};
```

### 5.4 Classes
#### 5.4.1 Constructors
Constructors are optional for concrete classes. Subclass constructors must call `super()` before setting any fields or otherwise accessing `this`. Interfaces must not define a constructor.

#### 5.4.2 Fields
All of a concrete object's fields (i.e. all properties other than methods) must be set in the constructor. Fields that are never reassigned with `@const` must be annotated (these need not be deeply immutable). Private fields must be annotated with `@private` and their names must end with a trailing underscore. Fields must never be set on a concrete class' `prototype`.

Example:
```js
class Foo {
    constructor() {
        /** @private @const {!Bar} */
        this.bar_ = computeBar();
    }
}
```

> **Tip:** Properties should never be added to or removed from an instance after the constructor is finished, since it significantly hinders VMs' ability to optimize. If necessary, fields that are initialized later should be explicitly set to `undefined` in the constructor to prevent later shape changes. Adding `@struct` to an object will check that undeclared properties are not added/accessed. Classes have this added by default.

#### 5.4.3 Computed properties
Computed properties may only be used in classes when the property is a symbol. Dict-style properties (that is, quoted or computed non-symbol keys, as defined in [5.3.3 Quoted and unquoted keys must not be mixed](#533-quoted-and-unquoted-keys-must-not-be-mixed)) are not allowed. A `[Symbol.iterator]` method should be defined for any classes that are logically iterable. Beyond this, `Symbol` should be used sparingly.

> **Tip:** be careful of using any other built-in symbols (e.g., `Symbol.isConcatSpreadable`) as they are not polyfilled by the compiler and will therefore not work in older browsers.

#### 5.4.4 Static methods
Where it does not interfere with readability, module-local functions should be preferred over private static methods.

Static methods should only be called on the base class itself. Static methods should not be called on variables containing a dynamic instance that may be either the constructor or a subclass constructor (and must be defined with `@nocollapse` if this is done), and must not be called directly on a subclass that doesn't define the method itself.

Illegal:
```js
class Base { /** @nocollapse */ static foo() {} }
class Sub extends Base {}
function callFoo(cls) { cls.foo(); }  // discouraged: don't call static methods dynamically
Sub.foo();  // illegal: don't call static methods on subclasses that don't define it themselves
```

#### 5.4.5 Old-style class declarations
While ES6 classes are preferred, there are cases where ES6 classes may not be feasible.

For example:
1. If there exists or will exist subclasses, including frameworks that create subclasses, that cannot be immediately changed to use ES6 class syntax. If such a class were to use ES6 syntax, all downstream subclasses not using ES6 class syntax would need to be modified.
    
2. Frameworks that require a known `this` value before calling the superclass constructor, since constructors with ES6 super classes do not have access to the instance `this` value until the call to `super` returns.

In all other ways the style guide still applies to this code: `let`, `const`, default parameters, rest, and arrow functions should all be used when appropriate.

Example:
```javascript
/**
 * @constructor @extends {S}
 * @param {string} value
 */
function C(value) {
    S.call(this, 2);

    /** @const */
    this.prop = value;
}

/**
 * @param {string} param
 * @return {number}
 */
C.prototype.method = function(param) {
    return 0;
};

```

Per-instance properties should be defined in the constructor after the call to the super class constructor, if there is a super class. Methods should be defined on the prototype of the constructor.

> **Deviation Note:** Compared to Google's JavaScript Style Guide, Google-specific guidance related to `goog.defineClass` and `goog.inherits` has been removed from this style guide.

#### 5.4.6 Class `prototype`s should not be manipulated directly
The `class` keyword allows clearer and more readable class definitions than defining `prototype` properties. Ordinary implementation code has no business manipulating these objects, though they are still useful for defining `@record` interfaces and classes as defined in [5.4.5 Old-style class declarations](#545-old-style-class-declarations). Mixins and modifying the prototypes of built-in objects are explicitly forbidden.

**Exception**: Framework code (such as Polymer, or Angular) may need to use `prototype`s, and should not resort to even-worse workarounds to avoid doing so.

**Exception**: Defining fields in interfaces (see [5.4.9 Interfaces](#549-interfaces)).

#### 5.4.7 Getters and Setters
[JavaScript getter and setter properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get) must not be used. They are potentially surprising and difficult to reason about, and have limited support in the compiler. Ordinary methods should be provided instead.

**Exception**: when working with data binding frameworks (such as Angular and Polymer), getters and setters may be used sparingly. Note, however, that compiler support is limited. When they are used, they must be defined either with `get foo()` and `set foo(value)` in the class or object literal, or if that is not possible, with `Object.defineProperties`. Do not use `Object.defineProperty`, which interferes with property renaming. Getters **must not** change observable state.

Illegal:
```js
class Foo {
  get next() { return this.nextId++; }
}
```

#### 5.4.8 Overriding toString
The `toString` method may be overridden, but must always succeed and never have visible side effects.

Tip: Beware, in particular, of calling other methods from toString, since exceptional conditions could lead to infinite loops.

#### 5.4.9 Interfaces
Interfaces may be declared with `@interface` or `@record`. Interfaces declared with `@record` must be explicitly (i.e. via `@implements`) or implicitly implemented by a class or object literal.

All non-static method bodies on an interface must be empty blocks. Fields must be defined after the interface body as stubs on the `prototype`.

Example:
```js
/**
 * Something that can frobnicate.
 * @record
 */
class Frobnicator {
    /**
     * Performs the frobnication according to the given strategy.
     * @param {!FrobnicationStrategy} strategy
     */
    frobnicate(strategy) {}
}

/** @type {number} The number of attempts before giving up. */
Frobnicator.prototype.attempts;
```

### 5.5 Functions
#### 5.5.1 Top-level functions
Exported functions may be defined directly on the `exports` object, or else declared locally and exported separately. Non-exported functions are encouraged and should not be declared `@private`.

Examples:
```js
/** @return {number} */
function helperFunction() {
    return 42;
}
/** @return {number} */
function exportedFunction() {
    return helperFunction() * 2;
}
/**
 * @param {string} arg
 * @return {number}
 */
function anotherExportedFunction(arg) {
    return helperFunction() / arg.length;
}
/** @const */
exports = {exportedFunction, anotherExportedFunction};
```

```js
/** @param {string} arg */
exports.foo = (arg) => {
    // do some stuff ...
};
```

#### 5.5.2 Nested functions and closures
Functions may contain nested function definitions. If it is useful to give the function a name, it should be assigned to a local `const`.

#### 5.5.3 Arrow functions
Arrow functions provide a concise syntax and fix a number of difficulties with `this`. Arrow functions should be preferred over the `function` keyword, particularly for nested functions (but see [5.3.5 Method shorthand](#535-method-shorthand)).

Prefer using arrow functions over `f.bind(this)`. Avoid writing `const self = this`. Arrow functions are particularly useful for callbacks, which sometimes pass unexpected additional arguments.

The right-hand side of the arrow may be a single expression or a block. Parentheses around the arguments are optional if there is only a single non-destructured argument.

> **Tip:** It is a good practice to use parentheses even for single-argument arrows, since the code may still parse reasonably (but incorrectly) if the parentheses are forgotten when an additional argument is added.

> **Deviation Note:** Compared to Google's JavaScript Style Guide, Google-specific guidance related to `goog.bind` has been removed from this style guide.

#### 5.5.4 Generators
Generators enable a number of useful abstractions and may be used as needed.

When defining generator functions, the `*` must be attached to the `function` keyword when present, and it must be separated from the name of the function by a space. When using delegating yields, the `*` must be attached to the `yield` keyword.

Example:
```js
/** @return {!Iterator<number>} */
function* gen1() {
    yield 42;
}

/** @return {!Iterator<number>} */
const gen2 = function*() {
    yield* gen1();
}

class SomeClass {
    /** @return {!Iterator<number>} */
    * gen() {
        yield 42;
    }
}
```

#### 5.5.5 Parameters
Function parameters must be typed with JSDoc annotations in the JSDoc preceding the function's definition, except in the case of same-signature `@override`s, where all types are omitted.

Parameter types _may_ be specified inline, immediately before the parameter name (as in `(/** number */ foo, /** string */ bar) => foo + bar`). Inline and `@param` type annotations _must not_ be mixed in the same function definition.

##### 5.5.5.1 Default parameters
Optional parameters are permitted using the equals operator in the parameter list. Optional parameters must include spaces on both sides of the equals operator, be named exactly like required parameters (i.e., not prefixed with `opt_`), use the `=` suffix in their JSDoc type, come after required parameters, and not use initializers that produce observable side effects. All optional parameters must have a default value in the function declaration, even if that value is `undefined`.

Example:
```js
/**
 * @param {string} required This parameter is always needed.
 * @param {string=} optional This parameter can be omitted.
 * @param {!Node=} node Another optional parameter.
 */
function maybeDoSomething(required, optional = '', node = undefined) {}
```

Use default parameters sparingly. Prefer destructuring (as in [5.3.7 Destructuring](#537-destructuring)) to create readable APIs when there are more than a small handful of optional parameters that do not have a natural order.

> **Note:** Unlike Python's default parameters, it is okay to use initializers that return new mutable objects (such as `{}` or `[]`) because the initializer is evaluated each time the default value is used, so a single object won't be shared across invocations.

> **Tip:** While arbitrary expressions including function calls may be used as initializers, these should be kept as simple as possible. Avoid initializers that expose shared mutable state, as that can easily introduce unintended coupling between function calls.

##### 5.5.5.2 Rest parameters
A _rest_ parameter should be used instead of accessing `arguments`. Rest parameters must be typed with a `...` prefix in their JSDoc. The rest parameter must be the last parameter in the list. There must not be a space between the `...` and the parameter name. The rest parameter must not be named `var_args`. A local variable or parameter must never be named `arguments`, as doing so confusingly shadows the built-in name.

Example:
```js
/**
 * @param {!Array<string>} array This is an ordinary parameter.
 * @param {...number} numbers The remainder of arguments are all numbers.
 */
function variadic(array, ...numbers) {}
```

#### 5.5.6 Returns
Function return types must be specified in the JSDoc directly above the function definition, except in the case of same-signature `@override`s where all types are omitted.

#### 5.5.7 Generics
Generic functions and methods must be declared, when necessary, with `@template TYPE` in the JSDoc above the class definition.

#### 5.5.8 Spread operator
Function calls may use the spread operator (`...`). Prefer the spread operator to `Function.prototype.apply` when an array or iterable is unpacked into multiple parameters of a variadic function. There is no space after the `...`.

Example:
```js
function myFunction(...elements) {}
myFunction(...array, ...iterable, ...generator());
```

### 5.6 String literals
#### 5.6.1 Use single quotes
Ordinary string literals must be delimited with single quotes (`'`), rather than double quotes (`"`).

> **Tip:** if a string contains a single quote character, consider using a template string to avoid having to escape the quote.

Ordinary string literals may not span multiple lines.

#### 5.6.2 Template strings
Template strings (delimited with `` ` ``) should be used over complex string concatenation, particularly if multiple string literals are involved. Template strings may span multiple lines.

If a template string spans multiple lines, it does not need to follow the indentation of the enclosing block, though it may if the added whitespace does not matter.

Example:
```js
function arithmetic(a, b) {
  return `Here is a table of arithmetic operations:
${a} + ${b} = ${a + b}
${a} - ${b} = ${a - b}
${a} * ${b} = ${a * b}
${a} / ${b} = ${a / b}`;
}
```

#### 5.6.3 No line continuations
_Line continuations_ (that is, ending a line inside a string literal with a backslash) must not be used in either ordinary or template string literals. Even though ES5 allows this, it can lead to tricky errors if any trailing whitespace comes after the slash, and is less obvious to readers.

Illegal:
```js
const longString = 'This is a very long string that far exceeds the 80 \
    column limit. It unfortunately contains long stretches of spaces due \
    to how the continued lines are indented.';

```

Instead, write
```js
const longString = 'This is a very long string that far exceeds the 80 ' +
    'column limit. It does not contain long stretches of spaces since ' +
    'the concatenated strings are cleaner.';
```

### 5.7 Number literals
Numbers may be specified in decimal, hex, octal, or binary. Use exactly `0x`, `0o`, and `0b` prefixes, with lowercase letters, for hex, octal, and binary, respectively. Never include a leading zero unless it is immediately followed by `x`, `o`, or `b`.

### 5.8 Control structures
#### 5.8.1 For loops
With ES6, the language now has three different kinds of `for` loops. All may be used, though `for`-`of` loops should be preferred when possible.

`for`-`in` loops may only be used on dict-style objects (see [5.3.3 Do not mix quoted and unquoted keys](#533-quoted-and-unquoted-keys-must-not-be-mixed)), and should not be used to iterate over an array. `Object.prototype.hasOwnProperty` should be used in `for`-`in` loops to exclude unwanted prototype properties. Prefer `for`-`of` and `Object.keys` over `for`-`in` when possible.

#### 5.8.2 Exceptions
Exceptions are an important part of the language and should be used whenever exceptional cases occur. Always throw `Error`s or subclasses of `Error`: never throw string literals or other objects. Always use `new` when constructing an `Error`.

Custom exceptions provide a great way to convey additional error information from functions. They should be defined and used wherever the native `Error` type is insufficient.

Prefer throwing exceptions over ad-hoc error-handling approaches (such as passing an error container reference type, or returning an object with an error property).

##### 5.8.2.1 Empty catch blocks
It is very rarely correct to do nothing in response to a caught exception. When it truly is appropriate to take no action whatsoever in a catch block, the reason this is justified must be explained in a comment.

```js
try {
    return handleNumericResponse(response);
} catch (ok) {
    // it's not numeric; that's fine, just continue
}
return handleTextResponse(response);
```

> **Deviation Note:** A confusing note related to `assertThrows` &ndash; which is present in Google's JavaScript style guide &ndash; was removed from this style guide.

#### 5.8.3 Switch statements
> **Terminology Note:** Inside the braces of a switch block are one or more statement groups. Each statement group consists of one or more switch labels (either `case FOO:` or `default:`), followed by one or more statements.

##### 5.8.3.1 Fall-through: commented
Within a switch block, each statement group must either terminate abruptly (with a `break`, `return` or `throw`n exception), or must be marked with a comment to indicate that execution will or might continue into the next statement group. Any comment that communicates the idea of fall-through is sufficient (typically `// fall through`). This special comment is not required in the last statement group of the switch block.

Example:
```js
switch (input) {
  case 1:
  case 2:
    prepareOneOrTwo();
  // fall through
  case 3:
    handleOneTwoOrThree();
    break;
  default:
    handleLargeNumber(input);
}
```

##### 5.8.3.2 The `default` case is present
Each switch statement must include a `default` statement group, even if it contains no code.

### 5.9 `this`
`this` may only be used in class constructors and methods, or in arrow functions defined within class constructors and methods. Any other uses of `this` must have an explicit `@this` declared in the immediately-enclosing function's JSDoc.

`this` must not be used to refer to the global object, the context of an `eval`, the target of an event, or unnecessarily `call()`ed or `apply()`ed functions.

### 5.10 Disallowed features
#### 5.10.1 `with`
The `with` keyword must not be used. It makes your code harder to understand and has been banned in strict mode since ES5.

#### 5.10.2 Dynamic code evaluation
`eval` or the `Function(...string)` constructor (except for code loaders) must not be used. These features are potentially dangerous and simply do not work in CSP environments.

#### 5.10.3 Automatic semicolon insertion
Statements must always be terminated with semicolons (except function and class declarations, as noted above).

#### 5.10.4 Non-standard features
Non-standard features must not be used. This includes old features that have been removed (e.g., `WeakMap.clear`), new features that are not yet standardized (e.g., the current TC39 working draft, proposals at any stage, or proposed but not-yet-complete web standards), or proprietary features that are only implemented in some browsers. Use only features defined in the current ECMA-262 or WHATWG standards. (Note that projects writing against specific APIs, such as Chrome extensions or Node.js, can obviously use those APIs). Non-standard language "extensions" (such as those provided by some external transpilers) are forbidden.

#### 5.10.5 Wrapper objects for primitive types
`new` must never be used on the primitive object wrappers (`Boolean`, `Number`, `String`, `Symbol`), nor included in type annotations.

Illegal:
```js
const /** Boolean */ x = new Boolean(false);
if (x) alert(typeof x);  // alerts 'object' - WAT?
```

The wrappers may be called as functions for coercing (which is preferred over using `+` or concatenating the empty string) or creating symbols.

Example:
```js
const /** boolean */ x = Boolean(0);
if (!x) alert(typeof x);  // alerts 'boolean', as expected
```

#### 5.10.6 Modifying built-in objects
Built-in types must never be modified, neither by adding methods to their constructors nor by adding methods to their prototypes. Avoid depending on libraries that do this. Note that the JSCompiler's runtime library will provide standards-compliant polyfills where possible; nothing else may modify builtin objects.

Symbols must not be added to the global object unless absolutely necessary (e.g. required by a third-party API).

## 6. Naming
### 6.1 Rules common to all identifiers
Identifiers must use only ASCII letters and digits, and, in a small number of cases noted below, underscores and very rarely (when required by frameworks like Angular) dollar signs.

Names must be as descriptive as possible, within reason. Do not worry about saving horizontal space as it is far more important to make your code immediately understandable by a new reader. Do not use abbreviations that are ambiguous or unfamiliar to readers outside your project, and do not abbreviate by deleting letters within a word.

```js
priceCountReader      // No abbreviation.
numErrors             // "num" is a widespread convention.
numDnsConnections     // Most people know what "DNS" stands for.
```

Illegal:
```js
n                     // Meaningless.
nErr                  // Ambiguous abbreviation.
nCompConns            // Ambiguous abbreviation.
wgcConnections        // Only your group knows what this stands for.
pcReader              // Lots of things can be abbreviated "pc".
cstmrId               // Deletes internal letters.
kSecondsPerDay        // Do not use Hungarian notation.
```

### 6.2 Rules by identifier type
#### 6.2.1 Package names
Package names must be all `lowerCamelCase`. For example, `my.exampleCode.deepSpace`, but not `my.examplecode.deepspace` or `my.example_code.deep_space`.

#### 6.2.2 Class names
Class, interface, record, and typedef names must be written in `UpperCamelCase`. Unexported classes are simply locals: they must not be marked `@private` and therefore must not be named with a trailing underscore.

Type names should typically be nouns or noun phrases. For example, `Request`, `ImmutableList`, or `VisibilityMode`. Additionally, interface names may sometimes be adjectives or adjective phrases instead (for example, `Readable`).

#### 6.2.3 Method names
Method names must be written in `lowerCamelCase`. Private methods' names must end with a trailing underscore.

Method names should typically be verbs or verb phrases. For example, `sendMessage` or `stop_`. Getter and setter methods for properties are never required, but if they are used they should be named `getFoo` (or optionally `isFoo` or `hasFoo` for booleans), or `setFoo(value)` for setters.

Underscores may also appear in JsUnit test method names to separate logical components of the name. One typical pattern is `test<MethodUnderTest>_<state>`, for example `testPop_emptyStack`. There is no One Correct Way to name test methods.

#### 6.2.4 Enum names
Enum names must be written in `UpperCamelCase`, similar to classes, and should generally be singular nouns. Individual items within the enum are named in `CONSTANT_CASE`.

#### 6.2.5 Constant names
Constant names must use `CONSTANT_CASE`: all uppercase letters, with words separated by underscores. There is no reason for a constant to be named with a trailing underscore, since private static properties can be replaced by (implicitly private) module locals.

##### 6.2.5.1 Definition of "constant"
Every constant is a `@const` static property or a module-local `const` declaration, but not all `@const` static properties and module-local `const`s are constants. Before choosing constant case, consider whether the field really feels like a _deeply immutable_ constant. For example, if any of that instance's observable state can change, it is almost certainly not a constant. Merely intending to never mutate the object is generally not enough.

Examples:
```js
// Constants
const NUMBER = 5;
/** @const */ exports.NAMES = ImmutableList.of('Ed', 'Ann');
/** @enum */ exports.SomeEnum = { ENUM_CONSTANT: 'value' };

// Not constants
let letVariable = 'non-const';
class MyClass { constructor() { /** @const */ this.nonStatic = 'non-static'; } };
/** @type {string} */ MyClass.staticButMutable = 'not @const, can be reassigned';
const /** Set<String> */ mutableCollection = new Set();
const /** ImmutableSet<SomeMutableType> */ mutableElements = ImmutableSet.of(mutable);
const Foo = require('my.Foo');  // mirrors imported name
const logger = log.getLogger('loggers.are.not.immutable');
```

Constants' names are typically nouns or noun phrases.

##### 6.2.5.1 Local aliases
Local aliases should be used whenever they improve readability over fully-qualified names. The same rules as `require`s ([3.3 `require` statements](#33-require-statements)) must be followed to maintain the last part of the aliased name. Aliases may also be used within functions. Aliases must be `const`.

Examples:

```js
const staticHelper = importedNamespace.staticHelper;
const CONSTANT_NAME = ImportedClass.CONSTANT_NAME;
const {assert, assertInstanceof} = asserts;
```

#### 6.2.6 Non-constant field names
Non-constant field names (static or otherwise) must be written in `lowerCamelCase`, with a trailing underscore for private fields.

These names should typically be nouns or noun phrases. For example, `computedValues` or `index_`.

#### 6.2.7 Parameter names
Parameter names must be written in `lowerCamelCase`. Note that this applies even if the parameter expects a constructor.

One-character parameter names should not be used in public methods.

**Exception**: When required by a third-party framework, parameter names may begin with a `$`. This exception does not apply to any other identifiers (e.g. local variables or properties).

#### 6.2.8 Local variable names
Local variable names must be written in `lowerCamelCase`, except for module-local (top-level) constants, as described above. Constants in function scopes must still be named in `lowerCamelCase`. Note that lowerCamelCase applies even if the variable holds a constructor.

#### 6.2.9 Template parameter names
Template parameter names should be concise, single-word or single-letter identifiers, and must be all-caps, such as `TYPE` or `THIS`.

### 6.3 Camel case: defined
Sometimes there is more than one reasonable way to convert an English phrase into camel case, such as when acronyms or unusual constructs like "IPv6" or "iOS" are present. To improve predictability, Wren Style specifies the following (nearly) deterministic scheme.

Beginning with the prose form of the name:
1. Convert the phrase to plain ASCII and remove any apostrophes. For example, "Müller's algorithm" might become "Muellers algorithm".
2. Divide this result into words, splitting on spaces and any remaining punctuation (typically hyphens).
    * _Recommended:_ if any word already has a conventional camel-case appearance in common usage, split this into its constituent parts (e.g., "AdWords" becomes "ad words"). Note that a word such as "iOS" is not really in camel case _per se_; it defies _any_ convention, so this recommendation does not apply.
3. Now lowercase _everything_ (including acronyms), then uppercase only the first character of:
    *   … each word, to yield _upper camel case_, or
    *   … each word except the first, to yield _lower camel case_
4. Finally, join all the words into a single identifier.

Note that the casing of the original words is almost entirely disregarded. Examples:

| Prose form                  | Correct             | Incorrect             |
| --------------------------- | ------------------- | --------------------- |
| "XML HTTP request"          | `XmlHttpRequest`    | `XMLHTTPRequest`      |
| "new customer ID"           | `newCustomerId`     | `newCustomerID`       |
| "inner stopwatch"           | `innerStopwatch`    | `innerStopWatch`      |
| "supports IPv6 on iOS?"     | `supportsIpv6OnIos` | `supportsIPv6OnIOS`   |
| "YouTube importer"          | `YouTubeImporter`   | `YoutubeImporter`*    |

*Acceptable, but not recommended.

> **Note:** Some words are ambiguously hyphenated in the English language: for example "nonempty" and "non-empty" are both correct, so the method names `checkNonempty` and `checkNonEmpty` are likewise both correct.

## 7. JSDoc
[JSDoc](https://developers.google.com/closure/compiler/docs/js-for-compiler) must be used on all classes, fields, and methods.

### 7.1 General form
The basic formatting of JSDoc blocks is as seen in this example:

```js
/**
 * Multiple lines of JSDoc text are written here,
 * wrapped normally.
 * @param {number} arg A number to do something to.
 */
function doSomething(arg) { ... }
```

or in this single-line example:
```js
/** @const @private {!Foo} A short bit of JSDoc. */
this.foo_ = foo;
```

If a single-line comment overflows into multiple lines, it must use the multi-line style with `/**` and `*/` on their own lines.

Many tools extract metadata from JSDoc comments to perform code validation and optimization. As such, these comments **must** be well-formed.

### 7.2 Markdown
JSDoc must be written in Markdown, though it may include HTML when necessary.

Note that tools that automatically extract JSDoc (e.g. [JsDossier](https://github.com/jleyba/js-dossier)) will often ignore plain text formatting, so if you did this:

```js
/**
 * Computes weight based on three factors:
 *   items sent
 *   items received
 *   last timestamp
 */
```

it would come out like this:
```
Computes weight based on three factors: items sent items received last timestamp
```

Instead, you should write a Markdown list:

```js
/**
 * Computes weight based on three factors:
 *  - items sent
 *  - items received
 *  - last timestamp
 */
```

### 7.3 JSDoc tags
Wren style allows a subset of JSDoc tags. See [9.1 JSDoc tag reference](#91-jsdoc-tag-reference) for links to the complete list. Most tags must occupy their own line, with the tag at the beginning of the line.

Illegal:
```js
/**
 * The "param" tag must occupy its own line and may not be combined.
 * @param {number} left @param {number} right
 */
function add(left, right) { ... }
```

Simple tags that do not require any additional data (such as `@private`, `@const`, `@final`, `@export`) may be combined onto the same line, along with an optional type when appropriate.

```js
/**
 * Place more complex annotations (like "implements" and "template")
 * on their own lines.  Multiple simple tags (like "export" and "final")
 * may be combined in one line.
 * @export @final
 * @implements {Iterable<TYPE>}
 * @template TYPE
 */
class MyClass {
    /**
     * @param {!ObjType} obj Some object.
     * @param {number=} num An optional number.
     */
    constructor(obj, num = 42) {
        /** @private @const {!Array<!ObjType|number>} */
        this.data_ = [obj, num];
    }
}
```

There is no hard rule for when to combine tags, or in which order, but tags must be consistent.

> **Deviation Note:** Compared to Google's JavaScript Style Guide, Google-specific guidance related to the closure compiler has been removed from this style guide.

### 7.4 Line wrapping
Line-wrapped block tags must be indented four spaces. Wrapped description text may be lined up with the description on previous lines, but this horizontal alignment is discouraged.

```js
/**
 * Illustrates line wrapping for long param/return descriptions.
 * @param {string} foo This is a param with a description too long to fit in
 *     one line.
 * @return {number} This returns something that has a description too long to
 *     fit in one line.
 */
exports.method = function(foo) {
    return 5;
};
```

A `@fileoverview` description must not be indented. 

### 7.5 Top/file-level comments
A file may have a top-level file overview. Author information and default [visibility level](#711-visibility-annotations) are optional. File overviews should be included whenever a file consists of more than a single class definition. The top level comment should be designed to orient readers unfamiliar with the code to what is in this file. If present, it may provide a description of the file's contents and any dependencies or compatibility information. Wrapped lines must not be indented.

Example:

```js
/**
 * @fileoverview Description of file, its uses and information
 * about its dependencies.
 * @package
 */
```

### 7.6 Class comments
Classes, interfaces and records must be documented with a description and any template parameters, implemented interfaces, visibility, or other appropriate tags. The class description should provide the reader with enough information to know how and when to use the class, as well as any additional considerations necessary to correctly use the class. Textual descriptions may be omitted on the constructor. `@constructor` and `@extends` annotations are not used with the `class` keyword unless the class is being used to declare an `@interface` or it extends a generic class.

```js
/**
 * A fancier event target that does cool things.
 * @implements {Iterable<string>}
 */
class MyFancyTarget extends EventTarget {
    /**
     * @param {string} arg1 An argument that makes this more interesting.
     * @param {!Array<number>} arg2 List of numbers to be processed.
     */
    constructor(arg1, arg2) {
        // ...
    }
};

/**
 * Records are also helpful.
 * @extends {Iterator<TYPE>}
 * @record
 * @template TYPE
 */
class Listable {
    /** @return {TYPE} The next item in line to be returned. */
    next() {}
}
```

### 7.7 Enum and typedef comments
Enums and typedefs must be documented. Public enums and typedefs must have a non-empty description. Individual enum items may be documented with a JSDoc comment on the preceding line.

```js
/**
 * A useful type union, which is reused often.
 * @typedef {!Bandersnatch|!BandersnatchType}
 */
let CoolUnionType;

/**
 * Types of bandersnatches.
 * @enum {string}
 */
const BandersnatchType = {
    /** This kind is really frumious. */
    FRUMIOUS: 'frumious',
    /** The less-frumious kind. */
    MANXOME: 'manxome',
};
```

Typedefs are useful for defining short record types, or aliases for unions, complex functions, or generic types. Typedefs should be avoided for record types with many fields, since they do not allow documenting individual fields, nor using templates or recursive references. For large record types, prefer `@record`.

### 7.8 Method and function comments
Parameter and return types must be documented. The `this` type should be documented when necessary. Method, parameter, and return descriptions (but not types) may be omitted if they are obvious from the rest of the method's JSDoc or from its signature. Method descriptions should start with a sentence written in the third person declarative voice. If a method overrides a superclass method, it must include an `@override` annotation. Overridden methods must include all `@param` and `@return` annotations if any types are refined, but should omit them if the types are all the same.

```js
/** This is a class. */
class SomeClass extends SomeBaseClass {
    /**
     * Operates on an instance of MyClass and returns something.
     * @param {!MyClass} obj An object that for some reason needs detailed
     *     explanation that spans multiple lines.
     * @param {!OtherClass} obviousOtherClass
     * @return {boolean} Whether something occurred.
     */
    someMethod(obj, obviousOtherClass) { ... }

    /** @override */
    overriddenMethod(param) { ... }
}

/**
 * Demonstrates how top-level functions follow the same rules.  This one
 * makes an array.
 * @param {TYPE} arg
 * @return {!Array<TYPE>}
 * @template TYPE
 */
function makeArray(arg) { ... }
```

Anonymous functions do not require JSDoc, though parameter types may be specified inline if the automatic type inference is insufficient.

```js
promise.then(
    (/** !Array<number|string> */ items) => {
        doSomethingWith(items);
        return /** @type {string} */ (items[0]);
    });
```

### 7.9 Property comments
Property types must be documented. The description may be omitted for private properties, if name and type provide enough documentation for understanding the code.

Publicly exported constants must be commented the same way as properties. Explicit types may be omitted for `@const` properties initialized from an expression with an obviously known type.

> **Tip:** A `@const` property's type can be considered "obviously known" if it is assigned directly from a constructor parameter with a declared type, or directly from a function call with a declared return type. Non-const properties and properties assigned from more complex expressions should have their types declared explicitly.

```js
/** My class. */
class MyClass {
    /** @param {string=} someString */
    constructor(someString = 'default string') {
        /** @private @const */
        this.someString_ = someString;

        /** @private @const {!OtherType} */
        this.someOtherThing_ = functionThatReturnsAThing();

        /**
         * Maximum number of things per pane.
         * @type {number}
         */
        this.someProperty = 4;
    }
}

/**
 * The number of times we'll try before giving up.
 * @const
 */
MyClass.RETRY_COUNT = 33;
```

### 7.10 Type annotations
Type annotations must be found on `@param`, `@return`, `@this`, and `@type` tags, and optionally on `@const`, `@export`, and any visibility tags. Type annotations attached to JSDoc tags must always be enclosed in braces.

#### 7.10.1 Nullability
The type system defines modifiers `!` and `?` for non-null and nullable, respectively. Primitive types (`undefined`, `string`, `number`, `boolean`, `symbol`, and `function(...): ...`) and record literals (`{foo: string, bar: number}`) are non-null by default. Do not add an explicit `!` to these types. Object types (`Array`, `Element`, `MyClass`, etc) are nullable by default, but cannot be immediately distinguished from a name that is `@typedef`'d to a non-null-by-default type. As such, all types except primitives and record literals must be annotated explicitly with either `?` or `!` to indicate whether they are nullable or not.

#### 7.10.2 Type Casts
In cases where type checking doesn't accurately infer the type of an expression, it is possible to tighten the type by adding a type annotation comment and enclosing the expression in parentheses. Note that the parentheses are required.

```js
/** @type {number} */ (x)
```

#### 7.10.3 Template Parameter Types
Template parameters must always be specified. This way compiler can do a better job and it makes it easier for readers to understand what code does.

Bad:
```js
const /** !Object */ users = {};
const /** !Array */ books = [];
const /** !Promise */ response = ...;
```

Good:
```js
const /** !Object<string, !User> */ users = {};
const /** !Array<string> */ books = [];
const /** !Promise<!Response> */ response = ...;

const /** !Promise<undefined> */ thisPromiseReturnsNothingButParameterIsStillUseful = ...;
const /** !Object<string, *> */ mapOfEverything = {};
```

Cases when template parameters should not be used:
*   `Object` is used for type hierarchy and not as map-like structure.

### 7.11 Visibility annotations
Visibility annotations (`@private`, `@package`, `@protected`) may be specified in a `@fileoverview` block, or on any exported symbol or property. Do not specify visibility for local variables, whether within a function or at the top level of a module. All `@private` names must end with an underscore.

### 7.12 Deprecation
Deprecated methods, classes or interfaces must be marked with `@deprecated` annotations. A deprecation comment must include simple, clear directions that describe the preferred replacement for the deprecated functionality.

> **Deviation Note:** This section of the style guide was moved from section 8.3 of Google's JavaScript Style Guide.

## 8. Policies
### 8.1 Issues unspecified by Wren Style: Be Consistent!
For any style question that isn't settled definitively by this specification, prefer to do what the other code in the same file is already doing. If that doesn't resolve the question, consider emulating the other files in the same package.

### 8.2 Compiler warnings
#### 8.2.1 Use a standard warning set
As far as possible projects should use `--warning_level=VERBOSE`.

#### 8.2.2 How to handle a warning
Before doing anything, make sure you understand exactly what the warning is telling you. If you're not positive why a warning is appearing, you should ask the Wren Security team for help or file an issue with us.

Once you understand the warning, attempt the following solutions in order:

1. **First, fix it or work around it.** Make a strong attempt to actually address the warning, or find another way to accomplish the task that avoids the situation entirely.
2. **Otherwise, determine if it's a false alarm.** If you are convinced that the warning is invalid and that the code is actually safe and correct, add a comment to convince the reader of this fact and apply the `@suppress` annotation.
3. **Otherwise, leave a TODO comment and file a ticket.** This is a **last resort**. If you do this, **do not suppress the warning.** The warning should be visible until it can be taken care of properly.

#### 8.2.3 Suppress a warning at the narrowest reasonable scope
Warnings are suppressed at the narrowest reasonable scope, usually that of a single local variable or very small method. Often a variable or method is extracted for that reason alone.

Example
```js
/** @suppress {uselessCode} Unrecognized 'use asm' declaration */
function fn() {
    'use asm';
    return 0;
}
```

Even a large number of suppressions in a class is still better than blinding the entire class to this type of warning.

### 8.3 Code not in Wren Style
You will occasionally encounter files in our codebase that is not in proper Wren Style. Typically, this is either legacy code that Wren inherited from ForgeRock, or code that was contributed to our project before Wren Style took a position on some issue.

#### 8.3.1 Reformatting existing code
When updating the style of existing code, follow these guidelines.

1. It is not required to change all existing code to meet current style guidelines. Reformatting existing code is a trade-off between code churn and consistency. Style rules evolve over time and these kinds of tweaks to maintain compliance would create unnecessary churn. However, if significant changes are being made to a file, the resulting file should be in Wren Style.
2. When making style-only changes as part of a larger change, the changes should be committed separately from logic or functionality changes, to make it easier for maintainers to understand your functionality changes without getting lost in style.
3. Be careful not to allow opportunistic style fixes to muddle the focus of a Pull Request. If you find yourself making a lot of style changes that are not critical to the central focus of a Pull Request, promote those changes to a separate Pull Request.

#### 8.3.2 Newly added code: use Wren Style
New files must use Wren Style, regardless of the style choices of other files in the same package.

When adding new code to a file that is not in Wren Style, reformatting the existing code first should be considered, subject to the advice in [Reformatting existing code](#831-reformatting-existing-code).

If this reformatting is not done, then new code should be as consistent as possible with existing code in the same file, but must not violate this style guide.

### 8.4 Generated code: mostly exempt
Source code generated by the build process is not required to be in Wren Style. However, any generated identifiers that will be referenced from hand-written source code must follow the naming requirements. As a special exception, such identifiers may contain underscores, which can help to avoid conflicts with hand-written identifiers.

When writing a code generator, you should strive for the code it generates to comply with this style guide whenever possible, to enhance project readability and maintainability.

## 9. Appendices
> **Deviation Note:** Compared to Google's JavaScript Style Guide, the version of this section in this style guide features only Wren-specific appendix information and links back to the original style guide where appropriate.

### 9.1 JSDoc tag reference
See section [9.1 of the Google JavaScript style guide](https://google.github.io/styleguide/jsguide.html#appendices-jsdoc-tag-reference).

### 9.3 Style-related tools
The following tools exist to support various aspects of Wren Style.

#### 9.3.1 The Google Closure Compiler
This program performs type checking and other checks, optimizations and other transformations (such as ECMAScript 6 to ECMAScript 5 code lowering).

#### 9.3.2 `clang-format`
This program reformats JavaScript source code into Wren Style, and also follows a number of non-required but frequently readability-enhancing formatting practices.

`clang-format` is not required. Authors are allowed to change its output, and reviewers are allowed to ask for such changes; disputes are worked out in the usual way. However, subtrees may choose to opt in to such enforcement locally.

#### 9.3.3 The Google Closure compiler linter
This program checks for a variety of missteps and anti-patterns.

#### 9.3.4 Conformance framework
The JS Conformance Framework is a tool that is part of the Google Closure Compiler that provides developers a simple means to specify a set of additional checks to be run against their code base above the standard checks. Conformance checks can, for example, forbid access to a certain property, or calls to a certain function, or missing type information (unknowns).

These rules are commonly used to enforce critical restrictions (such as defining globals, which could break the codebase) and security patterns (such as using `eval` or assigning to `innerHTML`), or more loosely to improve code quality.

For additional information see the official documentation for Google's [JS Conformance Framework](https://github.com/google/closure-compiler/wiki/JS-Conformance-Framework).

### 9.4 Exceptions for legacy platforms
> **Deviation Note:** Compared to Google's JavaScript Style Guide, in this style guide, Google-specific guidance related to `goog.provide`, `goog.require`, and `goog.scope` have been removed.

#### 9.4.1 Overview
This section describes exceptions and additional rules to be followed when modern ECMAScript 6 syntax is not available to the code authors. Exceptions to the recommended style are required when ECMAScript 6 syntax is not possible and are outlined here:

* Use of `var` declarations is allowed
* Use of `arguments` is allowed
* Optional parameters without default values are allowed

#### 9.4.2 Use `var`

##### 9.4.2.1 `var` declarations are NOT block-scoped
`var` declarations are scoped to the beginning of the nearest enclosing function, script or module, which can cause unexpected behavior, especially with function closures that reference `var` declarations inside of loops. The following code gives an example:

```js
for (var i = 0; i < 3; ++i) {
    var iteration = i;
    setTimeout(function() { console.log(iteration); }, i*1000);
}

// logs 2, 2, 2 -- NOT 0, 1, 2
// because `iteration` is function-scoped, not local to the loop.
```

##### 9.4.2.2 Declare variables as close as possible to first use
Even though `var` declarations are scoped to the beginning of the enclosing function, `var` declarations should be as close as possible to their first use, for readability purposes. However, do not put a `var` declaration inside a block if that variable is referenced outside the block. For example:

```js
function sillyFunction() {
    var count = 0;
    
    for (var x in y) {
        // "count" could be declared here, but don't do that.
        count++;
    }
    console.log(count + ' items in y');
}
```

##### 9.4.2.3 Use @const for constants variables
For global declarations where the `const` keyword would be used, if it were available, the `var` declaration must be annotated with `@const` instead (this is optional for local variables).

#### 9.4.3 Do not use block scoped functions declarations
Do **not** do this:

```js
if (x) {
  function foo() {}
}
```

While most JavaScript VMs implemented before ECMAScript 6 support function declarations within blocks it was not standardized. Implementations were inconsistent with each other and with the now-standard ECMAScript 6 behavior for block scoped function declaration. ECMAScript 5 and prior only allow for function declarations in the root statement list of a script or function and explicitly ban them in block scopes in strict mode.

To get consistent behavior, instead use a `var` initialized with a function expression to define a function within a block:
```js
if (x) {
  var foo = function() {};
}
```