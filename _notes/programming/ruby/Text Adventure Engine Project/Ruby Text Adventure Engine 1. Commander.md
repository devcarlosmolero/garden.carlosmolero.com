---
title: Ruby Text Adventure Engine 1. Commander
---
Developing this gem did not prove to be a problem.

Basically because it is based on 2 very common components in software development:

- [Lexer](https://en.wikipedia.org/wiki/Lexical_analysis): Analyze which symbols are allowed in a text string.
- [Parser](https://en.wikipedia.org/wiki/Parsing): Analyze which sets of symbols “mean something”.

These two components are, in fact, the basis of programming languages.

## Some design choices:

- I decided that it was more convenient to have the allowed symbols generated from the commands available in each scene of the game:

```ruby
  def initialize(commands)
    allowed_symbols = []
    commands.keys.map do |key|
      key.to_s.split("_").each do |part|
        allowed_symbols << part
      end
    end

    @allowed_symbols = allowed_symbols.uniq
    @parser = Parser.new(commands)
  end
```

That's why the initialize method expects a series of commands that can be used in a particular scene in the following format:

```yaml
commands:
 - OPEN_FIRST:
	type: navigation
	to: level_0#scene_1
```

*This will make more sense when you read [[Ruby Text Adventure Engine 2. Level Manager]].*

- As usual in this type of text-based games, the commands are composed of 2 words, the first one being, generally, a verb. So I followed this convention.
- The way the Lexer and Parser classes work together is very simple. The Lexer delivers an array with the allowed symbols it was able to recognize in the user input, for example: `[“GO”, “RIGHT”, “LANTERN”, “TAKE”]` and the Parser groups it in arrays of 2 words to decide if the order is correct. In this particular case, only the command `GO_RIGHT` is given as valid.
- I also decided to provide the developer with two helper methods: `#get_command` and `#print_available_commands`. The first one gets the rest of the command information and the second one prints the available commands for that scene.

<div class="notice">
Check the  <a target="_blank" href="https://github.com/devcarlosmolero/text-adventure-commander">Github repository</a>.
</div>

