---
layout: post
title: A New Ruby Gem -- LoweredExpectations
---

Pushed a new Ruby Gem today that lets you apply Gemfile-like expectations syntax to command line tools: [lowered-expectations](https://rubygems.org/gems/lowered-expectations). It'll check to make sure you have the tool in your environment, query it for the version and then compare the extracted version to a expected version pattern to make sure it falls within the expected range.

It lets you do nice things like fail if the version of `curl` on the system is less than `7.3` but greater-than-or-equal-to `8.0`:

    require 'lowered/expectations'
    LoweredExpectations.expect('curl', "~> 7.3")
    # If I get to here I know I have a version of curl I can use

If you're doing system scripts in Ruby I think you'll find this one handy to have. It should run in Ruby <2.0.0 though I haven't tested it there yet. And it should also run on Windows though, again, I don't use Windows so it may not function 100% correctly there yet (though I'm pretty certain my [which](https://github.com/ianchesal/loweredexpectations/blob/master/lib/lowered/expectations.rb#L39) implementation is Windows-friendly).

If you're not familiar with Ruby Gem version matching semantics, please see: http://stackoverflow.com/a/3416289/259811 and http://guides.rubygems.org/patterns/#semantic-versioning

You can contribute to the project here: https://github.com/ianchesal/loweredexpectations

And for those born post-1995 wondering about the name: http://www.poprewind.com/90s-moments-you-forgot-lowered-expectations/
