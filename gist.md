# Matching a URL With Regular Expressions

This tutorial will briefly go over how we can use regular expressions, or regex, to check for a valid URL.

## Summary

In this tutorial, we will use the following regex as an example: `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`. A regular expression is a pattern that allows you to match specific string combinations. 

## Table of Contents

- [Matching a URL With Regular Expressions](#matching-a-url-with-regular-expressions)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
    - [Anchors](#anchors)
    - [Quantifiers](#quantifiers)
    - [Character Classes](#character-classes)
    - [Grouping and Capturing](#grouping-and-capturing)
  - [Author](#author)

## Regex Components

### Anchors
Anchors are special characters that specify where in the text the regex should match. They do not match characters themselves but instead a position in the string.

`^` matches the start of the line.

`$` matches the end of the line

### Quantifiers

Quantifiers match a specified number of instances of a character. 

The `?` quantifier matches either 0 or 1 instances of the specified character.

The `+` quantifier matches one or more instances of the specified character.

The `*` quantifier matches 0 instances.

The `{n}` quantifier matches exactly n number of instances where n is a given number.

The `{n,}` quantifier matches n or more number of instances.

The `{n, x}` quantifier matches a range of instances from n to x where n is the minimum and x is the maximum.

In our example, we use `?` for `https?` where s can be optional in the protocol of a URL.

We also use `?` for the capture group `(https?:\/\/)?` indicating that the entirety of the protocol is optional.

We use `?` again towards the end of the regex with `/?` indicating an optional forward slash at the end of the protocol

We use `+` in the character class `[\da-z\.-]+` for our domain indicating that the specified characters in the class can be used any number of times.


### Character Classes

A character class is a way to define a set of characters that matches any of the enclosed characters in square brackets `[]`. Character classes can be specified with a range of characters using a hyphen or special escape to indicate what kind of character we want to match. 

In our example we have the character class `[\da-z\.-]` for our domain name. in this character class we use `/d` to indicate any digit. `a-z` indicates any letter between a and z. `\.` indicates a period and `-` includes hyphens in our allowed characters since it appears at the end of our character class. 

Other examples of character classes is the singular `\` witch can be used to specify a literal character match such as `\/`. This references matching specifically the `/` character. 

We also use `\w` which matches any alphanumeric character in the alphabet including the underscore. 

### Grouping and Capturing

Grouping allow you to organize certain sections of your text that match different parts of the expression. Groups are defined by using parentheses `()`. 

We use multiple groups in our regex one being `([\da-z\.-]+)`. This group is specific to the domain of the website. 

We can use groups to extract or capture text that we can use later in our code. For example, we can use the `match()` method to match the specific group to a string. 


## Author

Made by Jake Provard
GitHub: [https://github.com/provardjake](https://github.com/provardjake)