# Android Style Guide

Still a work in progress!

Pretty cool Android guide: [Android Guide](https://github.com/nstevens/androidguide/wiki)

Basic Java styling from 61B (This class is the reason I documented the functions I wrote for ff): [Java Project Guide](https://inst.eecs.berkeley.edu/~cs61b/fa13/labs/guidelines.pdf)

Google's official [Android Style Guide](https://source.android.com/source/code-style.html)

And another one we can look through! [Another pdf] (http://courses.coreservlets.com/Course-Materials/pdf/android/Android-Coding-Style.pdf)

## Table of Contents

* [Setup](#setup)
* [Naming Conventions](#naming-conventions)
* [Imports](#imports)
* [Whitespace](#whitespace)
* [Blocks](#blocks)
* [Coding](#coding)
* [Class Design](#class-design)
* [Miscellaneous](#misc)

## Setup

* Install
  1. `Android Studio` -> `Preferences` -> `Plugins` -> Search for 'Checkstyle' -> Browse for non-bundled plugin -> Install CheckStyle-IDEA
  2. Restart Android Studio
  3. `Android Studio` -> `Preferences` -> `CheckStyle` -> Browse for local checks.xml file

* Running
  1. Analyze -> Inspect Code
  2. There are many different sets of code style (Android lint, CheckStyle, Spelling, etc.). We are using the CheckStyle portion.

* CheckStyle
  * The CheckStyle config file can be found [here](https://github.com/calblueprint/style-guides/edit/android_style/android/checks.xml).


## Naming Conventions
* List of naming conventions and corresponding regex can be found [here](http://checkstyle.sourceforge.net/config_naming.html).


## Imports

```XML
<module name="AvoidStarImport" />
```
* Checks that there are no import statements that use the `*` notation.
* To prevent local namespace cluttering and potential future conflicts.
<sup>[[link](http://checkstyle.sourceforge.net/config_imports.html#AvoidStarImport)]</sup>

```XML
<module name="RedundantImport" />
```
* Checks for redundant import statements.
<sup>[[link](http://checkstyle.sourceforge.net/config_imports.html#RedundantImport)]</sup>

## Whitespace

```XML
<module name="GenericWhitespace" />
```
* Checks that the whitespace around the Generic tokens (angle brackets) "`<`" and "`>`" are correct to the typical convention.
<sup>[[link](http://checkstyle.sourceforge.net/config_whitespace.html#GenericWhitespace)]</sup>

```XML
<module name="MethodParamPad" />
```
* Checks the padding between the identifier of a method definition, constructor definition, method call, or constructor invocation; and the left parenthesis of the parameter list.
<sup>[[link](http://checkstyle.sourceforge.net/config_whitespace.html#MethodParamPad)]</sup>

```XML
<module name="NoWhitespaceAfter" />
        <property name="tokens"
                value="BNOT, DEC, DOT, INC, LNOT" />
```
* Checks that there is no whitespace after specified tokens (bitwise complement, decimal, prefix decrement and increment, logical complement).
<sup>[[link](http://checkstyle.sourceforge.net/config_whitespace.html#NoWhitespaceAfter)]</sup>

```XML
<module name="NoWhitespaceBefore" />
```
* Checks that there is no whitespace before specified tokens (semicolons, postfix decrement and increment operators).
<sup>[[link](http://checkstyle.sourceforge.net/config_whitespace.html#NoWhitespaceBefore)]</sup>

```XML
<module name="OperatorWrap" />
```
* Checks the policy on how to wrap lines on operators.
<sup>[[link](http://checkstyle.sourceforge.net/config_whitespace.html#OperatorWrap)]</sup>

```XML
<module name="ParenPad" />
```
* Checks that there is no whitespace after a left parenthesis and before a right parenthesis.
<sup>[[link](http://checkstyle.sourceforge.net/config_whitespace.html#ParenPad)]</sup>

```XML
<module name="TypecastParenPad" />
```
* Checks that there is no whitespace after a left parenthesis and before a right parenthesis for typecasts.
<sup>[[link](http://checkstyle.sourceforge.net/config_whitespace.html#TypecastParenPad)]</sup>

```XML
<module name="WhitespaceAfter" />
```
* Checks that specified tokens are followed by whitespace (commas, semicolons, typecasts).
<sup>[[link](http://checkstyle.sourceforge.net/config_whitespace.html#WhitespaceAfter)]</sup>

```XML
<module name="WhitespaceAround" />
```
* Checks that specified tokens are surrounded by whitespace.
<sup>[[link](http://checkstyle.sourceforge.net/config_whitespace.html#WhitespaceAround)]</sup>


## Blocks

```XML
<module name="AvoidNestedBlocks" />
```
* Finds nested blocks, i.e. blocks that are used freely in the code.
<sup>[[link](http://checkstyle.sourceforge.net/config_blocks.html#AvoidNestedBlocks)]</sup>

```XML
<module name="EmptyBlock" />
```
* Checks for empty blocks.
<sup>[[link](http://checkstyle.sourceforge.net/config_blocks.html#EmptyBlock)]</sup>

```XML
<module name="LeftCurly" />
```
* Checks for the placement of left curly braces ('`{`') for code blocks.
* Should be located at eol & max line length 80.
<sup>[[link](http://checkstyle.sourceforge.net/config_blocks.html#LeftCurly)]</sup>

```XML
<module name="RightCurly" />
        <property name="tokens"
                value="LITERAL_TRY, LITERAL_CATCH, LITERAL_FINALLY, LITERAL_ELSE" />
```
* Checks the placement of right curly braces ('`}`') for `else`, `try`, and `catch` tokens.
* Should be located on the same line as `else`, `try`, and `catch` tokens.
<sup>[[link](http://checkstyle.sourceforge.net/config_blocks.html#RightCurly)]</sup>


## Coding

```XML
<module name="CovariantEquals" />
```
* Checks that classes that define a covariant `equals()` method also override `equals(java.lang.Object)`.
* To prevent potential unexpected behavior.
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#CovariantEquals)]</sup>

```XML
<module name="DefaultComesLast" />
```
* Check that the `default` is after all the `case`s in a `switch` statement.
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#DefaultComesLast)]</sup>

```XML
<module name="EmptyStatement" />
```
* Detects empty statements (standalone "`;`" semicolon).
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#EmptyStatement)]</sup>

```XML
<module name="EqualsHashCode" />
```
* Checks that classes that override `equals()` also override `hashCode()`.
* `equals()` requires that equal objects have the same hashCode.
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#EqualsHashCode)]</sup>

```XML
<module name="IllegalCatch" />
```
* Checks that certain exception types do not appear in a `catch` statement.
* `java.lang.Exception`, `java.lang.Throwable`, `java.lang.RuntimeException` are not descriptive and may catch unintended exceptions.
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#IllegalCatch)]</sup>

```XML
<module name="InnerAssignment" />
```
* Checks for assignments in subexpressions
* For readability.
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#InnerAssignment)]</sup>

```XML
<module name="MissingSwitchDefault" />
```
* Checks that `switch` statement has a "`default`" clause.
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#MissingSwitchDefault)]</sup>

```XML
<module name="OneStatementPerLine" />
```
* Checks that there is only one statement per line.
* For readability.
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#OneStatementPerLine)]</sup>

```XML
<module name="SimplifyBooleanExpression" />
```
* Checks for over-complicated boolean expressions.
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#SimplifyBooleanExpression)]</sup>

```XML
<module name="SimplifyBooleanReturn" />
```
* Checks for over-complicated boolean return statements.
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#SimplifyBooleanReturn)]</sup>

```XML
<module name="StringLiteralEquality" />
```
* Checks that string literals are not used with `==` or `!=`.
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#StringLiteralEquality)]</sup>

```XML
<module name="UnnecessaryParentheses" />
```
* Checks for the use of unnecessary parentheses.
<sup>[[link](http://checkstyle.sourceforge.net/config_coding.html#UnnecessaryParentheses)]</sup>


## Class Design

```XML
<module name="FinalClass" />
```
* Checks that a class which has only private constructors is declared as `final`.
<sup>[[link](http://checkstyle.sourceforge.net/config_design.html#FinalClass)]</sup>

```XML
<module name="HideUtilityClassConstructor" />
```
* Checks that utility classes (classes that contain only static methods or fields) do not have a public constructor.
* Utility classes should not be instantiated.
<sup>[[link](http://checkstyle.sourceforge.net/config_design.html#HideUtilityClassConstructor)]</sup>

```XML
<module name="VisibilityModifier">
        <property name="packageAllowed" value="true" />
        <property name="protectedAllowed" value="true" />
```
* Checks visiblity of class members.
* Non-static & non-final members should not be declared public to enforce encapsulation.
<sup>[[link](http://checkstyle.sourceforge.net/config_design.html#VisibilityModifier)]</sup>


## Miscellaneous

```XML
<module name="UncommentedMain" />
```
* Checks for uncommented `main()` methods.
<sup>[[link](http://checkstyle.sourceforge.net/config_misc.html#UncommentedMain)]</sup>

```XML
<module name="OuterTypeFilename" />
```
* Checks that the outer type name and the file name match.
<sup>[[link](http://checkstyle.sourceforge.net/config_misc.html#OuterTypeFilename)]</sup>

```XML
<module name="JavadocStyle" />
```
* Validates Javadoc comments to help ensure they are well formed.
<sup>[[link](http://checkstyle.sourceforge.net/config_javadoc.html#JavadocStyle)]</sup>

# Credits

[Checkstyle](http://checkstyle.sourceforge.net/).
[CheckStyle-IDEA](https://plugins.jetbrains.com/plugin/1065).
