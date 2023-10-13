# The Basics to Regex (Regular Expressions: Matching a URL)

Regex, or Regular Expressions, might sound like a complex and cryptic code language, but it's actually a powerful tool that helps you find and manipulate text patterns in a wide range of applications. Think of regex as a secret decoder for text, allowing you to search for specific words, phrases, or even patterns of characters within a sea of text. Whether you're a beginner or an experienced programmer, understanding regex can be incredibly useful. In this tutorial, we'll take a step-by-step journey into the world of regex, breaking down its core components and demystifying its seemingly mysterious symbols. By the end, you'll have the skills to wield regex with confidence and unlock a whole new level of text-processing.

## Summary

In this tutorial we will take a further look at some components of Regex, or Regular Expressions. Regex helps you find specific words or patterns in text. In this tutorial we will cover a regex tutorial when matching a URL, anchors, quantifiers, grouping constructs, bracket expressions, character classes, the OR operator, flags, and last but not least character escapes. This may seem a bit overwhelming, take a deep breath. We are only getting started on our coding journey. It'll all make sense soon. Thank you for stopping by, let's get started!

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Matching a URL with Regex](#matching-a-url-with-regex)

## Regex Components

First and foremost, a regex is considered a literal. Meaning the pattern must be wrapped in slash charecters `/`. In this tutorial, we will explore the fundamental components and concepts of regular expressions (regex). Each section will focus on a specific aspect of regex, explaining its purpose and how it can be used. Below are the topics of what we'll cover to get a better understanding:

### Anchors

Anchors are special characters that allow you to match patterns at specific positions within a string. We'll delve into the use of `^` and `$` to anchor your regex searches at the beginning and end of a line.

To explain a bit further, the `$` anchor is like a marker that shows a string should finish with the characters just before it. It's kind of like a full stop at the end of a sentence. Similar to the `^` character we talked about earlier, you can use it with an exact set of characters or a range of possible matches that you expect to see at the end of the string.

### Quantifiers

Quantifiers help you define the quantity of characters or groups you want to match. You'll learn how to use `*`, `+`, `?`,`{}`, and more to specify how many times a character or group should appear.

Quantifiers are like rules that tell your regex how much or how many of something to look for in a piece of text. It's like saying, 'I want to find at least this many, but no more than that many.' They're kind of like counting tools. But here's the thing: quantifiers are a bit greedy. That means they try to find as many of those things as possible in your text, like grabbing as much candy as they can from a jar. Like an unsupervised child on Halloween. So, if you say 'find at least three,' they might find even more if there are more to be found!

### Grouping Constructs

Grouping allows you to apply regex operators to a set of characters. We'll explore the use of parentheses for creating groups and how they can be employed for complex pattern matching.

When it comes to regular expressions, grouping constructs are like magical parentheses `(` and `)`that help you organize and simplify your text-searching spells. They allow you to group together characters, words, or even complex patterns, so you can treat them as a single unit. Imagine you want to find names in a list with both first and last names. Grouping constructs enable you to capture each name part separately, making it easy to work with and extract that specific information from a overload of text you have.

### Bracket Expressions

Bracket expressions, often referred to as character classes, enable you to match specific sets of characters. You'll discover how to use `[ ]` to match characters or ranges efficiently. ANYTHING inside a set of square brackets represents a range of characters that we want to match. 

When it comes to bracket expressions imagine square brackets as your way of picking out specific characters you want to find in a bunch of text. We call this a 'bracket expression' or 'positive character group.' Basically, you're making a list of the characters you're interested in, and when you use these square brackets, they help you match those characters in the text you're searching through. It's like telling your computer, 'Hey, find me any of these characters I've listed inside these square brackets.' So, you can include all the characters you're looking for in this little 'character club' inside the brackets. (Note: You'll commonly see a hyphen used between alphanumeric characters to represent a range of those possible characters. For example, `[r-t]` and `[rst]` will look for the exact same thing).

### Character Classes

Character classes are predefined sets of characters that simplify regex patterns. We'll cover common character classes like `.`, `\d`, `\w`, and `\s`. 

In regex, a 'character class' is like a special group of characters that we want to find in some text. It's like having a list of characters, and any one of them can be a match in the text we're searching through. We've actually talked about character classes already without even realizing it! Those 'bracket expressions' we mentioned earlier, both the positive ones and the negative ones, are what we call 'character classes.' So, when you see a character class in regex, it means we're looking for any of the characters in that special group.

### The OR Operator

The OR operator (`|`) provides a way to match multiple alternatives in a single pattern. We'll show you how to create conditional patterns with this powerful feature. For example `(gray|grey)` would contain both gray OR grey. 

### Flags

Regex flags modify how your regex pattern is processed. We'll explain the significance of flags like `i`(case-insensitive search), `g`(global search), and `m`(multi-line search) and how they affect matching.

* Flags
    * i - Case-insensitive search: the case should be ignored during the attempt to match the string.
    * m - Multi-line search: this string should be treated as if they were multiple llines.
    * g - Global search: should test against all matches in string.

### Character Escapes

Character escapes allow you to match characters with special meanings, such as `.`, `*`, or `+`, literally. We'll guide you through escaping these characters to match them in your regex patterns.

Now that we have covered some things you may see along the way. Let's go ahead and dive into each of these components one by one. This starter information should've made regex more approachable and comprehensible. 

### Matching a URL with Regex

In this tutorial so far we have covered a lot of what contributes to the creation and make up of regular expressions(regex). Let's jump in a bit further and take a detailed look at how we can go about matching a URL with regex. We're going to break it down step by step, the provided regex pattern we have to work with for matching a URL is:

```
^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$
```

Overwhelmed? So was I, the bark is louder than the bite. Let's go ahead and break this down. 

* Regex Pattern Explanation

    * `^` - This means the start of a line.

    * `(https?:\/\/)?` - This part matches the "http://" or "https://" protocol at the beginning of a URL. The question mark means it's optional.

    * `([\da-z\.-]+)` - This part matches the main part of the website address. It can have lowercase letters, numbers, dots, or hyphens. This is capturing the domain name part of the URL.

    * `\.([a-z\.]{2,6})` - This part matches the ending part of the website, like ".com" or ".org." It has to be 2 to 6 letters or dots. This captures the top-llevel domain(TLD) part.

    * `([\/\w \.-]*)*` - This part finds the part after the main website address. It can be a path or query. It can contain letters, numbers, slashes, spaces, dots, and hyphens.

    * `\/?$` - This matches the optional trailing slash and ensures that the URL ends with an optional `/`.

Now that we have broken down the symbol meanings in our regex pattern, lets take a look at how we would use this pattern.

* Using the Regex Pattern

    * Import a regex library if you're working in a programming language. For example, in Python, you can use the re library.

    * Define your regex pattern as a string. In our case, it's the pattern we explained earlier:

    ```
    ^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$
    ```

    * Apply the regex pattern to your input text. If you're using a programming language, you can use a function like re.match or re.findall to find the URLs in your text.

    * The matched URLs will be returned as a result, and you can then use them as needed in your application.

Last but not least, suppose you have a text containing URLs..

* Example

```
Here is a sample URL: https://www.jiujitsucarrot.com/
And another one: http://subdomain.example.co.uk
This is not a URL: just some text
```

You can use the regex pattern to find and extract URLs from this text. Just like that, we made it! You now know how to explain a regex pattern for matching a URL, as well as using the pattern. Well done! Regular expressions are a powerful tool for text pattern matching, and this tutorial should help you get started with matching URLs in your text.

Below are some Basic examples listed of what you may see when it comes to Regex. Happy Coding!

```
    hello - contains {hello}
    
    gray|grey - contains {gray, grey}
    
    gr(a|e)y - contains {gray, grey}
    
    gr[ae]y - contains {gray, grey}
    
    b[aeiou]bble - contains {babble, bebble, bibble, bobble, bubble}
    
    [b-chm-pP]at|ot - contains {bat, cat, hat, mat, nat, oat, pat, Pat, ot}
    
    colou?r - contains {color, colour}
    
    rege(x(es)?|xps?)	- contains {regex, regexes, regexp, regexps}
    
    go*gle - contains {ggle, gogle, google, gooogle, goooogle, ...}
    
    go+gle - contains {gogle, google, gooogle, goooogle, ...}
    
    g(oog)+le	- contains {google, googoogle, googoogoogle, googoogoogoogle, ...}
    
    z{3} - contains {zzz}
    
    z{3,6} - contains {zzz, zzzz, zzzzz, zzzzzz}
    
    z{3,}	- contains {zzz, zzzz, zzzzz, ...}
    
    [Bb]rainf\*\*k - contains {Brainf**k, brainf**k}
    
    \d - contains {0,1,2,3,4,5,6,7,8,9}
    
    \d{5}(-\d{4})? - contains a United States zip code
    
    1\d{10} - contains an 11-digit string starting with a 1
    
    [2-9]|[12]\d|3[0-6] - contains an integer in the range 2..36 inclusive
    
    Hello\nworld - contains Hello followed by a newline followed by world
    
    mi.....ft	- contains a nine-character (sub)string beginning with mi and ending with ft (Note: depending on context, the dot stands either for “any character at all” or “any character except a newline”.) Each dot is allowed to match a different character, so both microsoft and minecraft will match.
    
    \d+(\.\d\d)? - contains a positive integer or a floating point number with exactly two characters after the decimal point.
    
    [^i*&2@] - contains any character other than an i, asterisk, ampersand, 2, or at-sign.
    
    //[^\r\n]*[\r\n] - contains a Java or C# slash-slash comment
    
    ^dog - begins with "dog"
    
    dog$ - ends with "dog"
    
    ^dog$ - is exactly "dog"
```

## Author

Thank you once again for stopping by to get some basic information on Regex, or Regular Expression listed in this basic tutorial. My name is Tanner Norris, I am currently a junior developer in the ASU Full Stack Web Development program. Always eager to get tips from those in the industry as well as network to grow as a developer. Below I have attached the URL to my GitHub account. Once again, happy coding!

* https://github.com/jiujitsucarrot

### Source Links

* https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial

* https://cs.lmu.edu/~ray/notes/regex/

* https://www.rexegg.com/regex-anchors.html

* https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp