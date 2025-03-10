---
title: "Ruby Text Adventure Engine: Commander"
---
Developing this gem did not prove to be a problem.

Basically because it relies on 2 very common functionalities in software development:

- [Lexer](https://en.wikipedia.org/wiki/Lexical_analysis): Analyze which symbols are allowed in a text string.
- [Parser](https://en.wikipedia.org/wiki/Parsing): Analyze which sets of symbols “mean something”.

These two components are, in fact, the basis of programming languages.

The Lexer class would look like this:

```rb
class Lexer
  def self.get_recognized_symbols(allowed_symbols, input)
    recognized_symbols = []
    input_array = input.gsub(/[^a-zA-Z\s]/, "").split(" ")
    input_array.each do |word|
      recognized_symbols << word.upcase if allowed_symbols.include?(word.upcase)
    end
    recognized_symbols
  end
end
```

<div class="notice">
Check the  <a target="_blank" href="https://github.com/devcarlosmolero/text-adventure-commander">Github repository</a>.
</div>