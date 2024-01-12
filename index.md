Let's try to reboot this page once again, as usual every other year.

### Building an interpreter for a simple language @ UniBo
I was invited to give a three-hour talk/demo for the bachelor Programming Languages course at UniBo, showcasing how to build an interpreter for a small language.
The `Demo` language is a concurrent extension to the classic WHILE language, adding procedures and concurrent execution go-style.
I used Java as host language and ANTLR 4 as a parser generator.
The most interesting part in my view is however describing how to implement the language semantics starting from a formal one in the structural operational style (big step variant).
Slides describing the construction process, the semantics and some interesting details (nontermination modelled as an infinite proof) will be made available.
The code can be found [here](https://github.com/annopaolo/demo).

### Erlang, Elixir, Gleam and Friends devroom @ FOSDEM 2024

We’re excited to announce that the Erlang, Elixir, Gleam and Friends Devroom is back for FOSDEM 2024!

[FOSDEM](https://fosdem.org/2024/) is one of the largest conferences in the world and fully dedicated to open-source software.
It that wasn't enought, it's also free!

You can find the Call for Talks [here](https://beam-fosdem.dev/call-for-talks/).
Me and [Davide Bettio](https://blog.uninstall.it/) are the devroom managers, with many more helping us, especially [Riccardo Binetti](https://rbino.com/)!

Whether you’re submitting your talk proposal, or you’re just attending the event, we hope to see you in Brussels in February on the 3rd of February, 2024!

### Fighting the Behemoth
> He is the first of God’s works [...]
  He can restrain the river from its rushing;
  He is confident the stream will gush at his command.
  Can he be taken by his eyes?
  Can his nose be pierced by hooks?

Job, 40:15.23-24

Last week I did a lighting talk at [Code BEAM EU](https://codebeameurope.com/) in Berlin!
The focus of the talk was the current refactoring process of an outrageous piece of code
in the [Astarte](https://github.com/astarte-platform) codebase, the ill-famed [impl.ex](https://github.com/astarte-platform/astarte/blob/master/apps/astarte_data_updater_plant/lib/astarte_data_updater_plant/data_updater/impl.ex).

Largely written somewhere between 5 and 6 years ago, when most of the Astarte team was learning
Elixir (*the first of Astarte's works*), it is a perfect example of how to write code that works, runs fast, can be relied upon (*confident the stream will gush at his command*)
but is also absolutely unreadable and dreadful to maintain.
Being the maintainer, I had to do something!

I will make the slides available in the next days, for the moment the brief summary of this
WIP refactoring is:
- Divide the functional, (mostly) pure core from the imperative shell: keep domain complexity separate (and typed, and tested) from the machinery complexity
- As in everything, big and disomogeneous state is a mess: keep it as little as feasible, possibly also by splitting it in its different subcomponents
- Elixir's `with` work better if there is no `else`, keeping the code monadic
- Tests of the functional core should be readable, repeatable and randomized
