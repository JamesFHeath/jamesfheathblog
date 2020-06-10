---
layout: post
title:  "Basic JSON Tokenizer in Haskell: First Go"
categories: haskell programming
tags: haskell programming json
---

### Motivation
I've spent the last year on and off trying to learn Haskell.
This has involved reading books, listening to podcasts, watching videos, and writing very simple programs.
Despite the effort, it's taken me a long time to make progress.
I thought a JSON tokenizer, then parser, would be an achievable challenge. 

### Limitations 
Tokenizing JSON is realtively simple, as the syntax has relatively few characters. 
I decided not to strictly follow the [specification](https://www.json.org/json-en.html), and instead limited myself to brackets, double quotes, integers, identifiers, colons, commas, whitespace and booleans.
This excludes escape characters, exponentials, floating point, hex, etc. 
My goal was to learn, not create a perfect implementation. 

### Data Model
I modeled the data as sum type called *token*, and created a function that took a string and returned a list of tokens.

{% highlight haskell %}
    data Token = 
        OpenBracket | CloseBracket |
        OpenBrace | CloseBrace |
        DoubleQuote |
        Comma |
        Colon |
        JsonNumber Int |
        JsonIdentifier String |
        JsonString String |
        JsonBool Bool
        deriving (Show)

    tokenize :: String -> [Token]
    tokenize "" = []
    tokenize (j:js)
        | j == ' ' = [] ++ tokenize js
        | j == '{' = [OpenBracket] ++ tokenize js
        | j == '}' = [CloseBracket] ++ tokenize js
        | j == '[' = [OpenBrace] ++ tokenize js
        | j == ']' = [CloseBrace] ++ tokenize js
        | j == '"' = [DoubleQuote] ++ tokenize js
        | j == ',' = [Comma] ++ tokenize js
        | j == ':' = [Colon] ++ tokenize js
        | ord j >= 48 && ord j <= 57 = 
        -- | ord j >= 48 && ord j <= 57 = [fst . tokenizeNumber $ j:js] ++ (tokenize . snd . tokenizeNumber $ j:js)
        -- | otherwise = [fst . tokenizeIdentifier $ j:js] ++ (tokenize . snd . tokenizeIdentifier $ j:js)
        where jsonNumber = 

    tokenizeNumber :: String -> (Token, String)
    tokenizeNumber (n:ns) = (JsonNumber 5, "")

    tokenizeIdentifier :: String -> (Token, String)
    tokenizeIdentifier (j:js) = (JsonIdentifier "myId", "")
{% endhighlight %}

The single characters were a breeze, and I was making plenty of progress. 
However, once I got to numbers and identifiers, things slowed down. 

*Hopefully* to be continued...