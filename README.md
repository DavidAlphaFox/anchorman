# Anchorman [![Travis-CI](https://api.travis-ci.org/ostera/anchorman.svg)](https://travis-ci.org/ostera/anchorman)
⚓👨 An Erlang library for broadcasting information

## Installation

Simply include in your `rebar.config` as:

```erlang
{deps, [
  % ...
  {anchorman, {git, "https://github.com/ostera/anchorman", {tag, "0.1.0"}}}
  % ...
]}.
```

## Usage

```erlang
Eshell V7.3  (abort with ^G)
1> application:start(anchorman).
[anchorman@mirror] I look fantastic today...ok
3> anchorman:broadcast(<<"system.status">>, "60% of the time, it works every time").
[anchorman@mirror] {broadcast,<<"system.status">>,"60% of the time, it works every time"}ok
```

## Motivation

When building [pry](https://github.com/ostera/pry) I found myself in the need for publishing information
from inside the BEAM to the outside world with a unified interface that could let me plug more transports
as I see need, and doesn't incur in much overhead or any refactor in my current code.

And this clearly had nothing to do with gaining insight of an existing system, so I factored it out
into a separate application/library.

This way, either by manually starting an `anchorman_server` with a set of handlers, or by configuring
it in your `app.src` file, you get to publish the same data to as many places as you want without rewriting
a line of code. What? Neat? Yup.

## Contributing

Fork, make a topic branch, and send a Pull Request. Travis will let you know if
it's good to go, and from the on we can review, retouch, and merge.

Included here is a `Makefile` with handy targets. Run `make` to execute the complete
battery of tests.

## Next Steps

See the [issues page](https://github.com/ostera/anchorman/issues?q=is%3Aopen+is%3Aissue+label%3Aenhancement) for a list of planned enhancements and features.

## License

See [LICENSE](https://github.com/ostera/anchorman/blob/master/LICENSE).
