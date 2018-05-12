# highlight-linedivs

Generate line divs using Jekyll's highlight tag.

## What?

This plugin injects a new option `linedivs` into the `highlight` tag. This will cause each line of source code output by the `highlight` tag to be contained within a `div`.

## Why?

There were no good options for displaying line numbers in Jekyll source code. Wrapping each line inside a `div` makes it pretty easy. I'm writing a blog post on how to do that.

## How?

Add the gem `rouge-lines` to your `Gemfile`:

```ruby
group :jekyll_plugins do
  gem "rouge-lines", "3.2.3"
end
```

and run `bundle update`. (Or is it `bundle install`? I'm not a Ruby guy.)

Then take the `highlight-linedivs.rb` file and push it somewhere else! (To the `_plugins` folder.)

## Background

I submitted a [PR](https://github.com/jneen/rouge/pull/897) to Rouge which creates a new formatter for outputting line divs. The scope of the PR is a bit broader than that of this plugin, so not all of it may get through, but I'll try to get line divs accepted as a bare minimum.

Once that PR gets accepted, I'll just have to submit another PR to Jekyll to enable the new option in the `highlight` tag.

Unfortunately, it looks like Rouge is not being actively maintained at the moment, so we're already stuck. That's why I made this plugin -- you can get the functionality without waiting for the Rouge devs to awaken from slumber. Once `linedivs` is in Rouge and Jekyll, I'll deprecate this plugin.
