### Chapter 5: The Many Variables & The Spurious Waffles

Selections and commentary from Aaron:


---

> "... introduce graphical causal models as a way to design and
> interpret regression models." (page 124)


---

> "About one thing, however, there is general agreement: Causal
> inference always depends upon unverifiable assumptions." (page 124)


---

> "Think before you regress" (page 128)

In the first paragraph of 5.1.1, I don't really see how Figure 5.2
tells us that only one of the predictor variables has a causal
influence...


---

I really like [dagitty][]. Learning about it is one of the best things
in the book, in that I was wishing to find such software while reading
[The Book of Why][] but didn't.

[dagitty]: http://www.dagitty.net/
[The Book of Why]: https://planspace.org/20200917-book_of_why/

It is a little weird that the web interface uses ⊥ (falsum)... Hmm;
[looking it up][], it seems it's the same symbol as `\perp`, which is
used for independence. Ah! The "double tack up" (⫫) is for conditional
independence! The web interface still uses ⊥ for both kinds of
independence.

[looking it up]: https://en.wikipedia.org/wiki/Up_tack


---

> "This is very weird notation and any feelings of annoyance on your
> part are justified." (page 130)


---

The `coeftab` visualization (see page 133) is pretty nice.


---

It took me a little bit to understand what he was getting at with the
"predictor residual plots" (page 135) but I'm glad I did, since it
connects to one of his main points about how multiple regression is
about how much a variable adds given all the other variables.


---

> "Usually answers to large world questions about truth and causation
> depend upon information not included in the model." (page 139)


---

The section 5.2 "Masked relationship" is neat.


---

> "Taking the log of a measure translates the measure into
> magnitudes." (page 148)

What use of "magnitude" is this? Hmm... Looks like star brightness is
done via a log that is called magnitude... Just weird, because in
other domains "magnitude" refers to the _un_-logged value...


---

> "A set of DAGs with the same conditional independencies is known as
> a Markov equivalence set." (page 151)


---

I was unfamiliar with [Melanesia][].

[Melanesia]: https://en.wikipedia.org/wiki/Melanesia


---

One page 155, he makes index variables seem fundamentally different
from indicator variables. Their notation in `quap` is different (and
nicer) but fundamentally the only difference is with index variables
you drop the intercept term (or equivalently, you have separate
intercept terms for each thing). Just reading through, I initially
thought his index variables were a real novelty, but they're not. (I'm
still curious about where he says on page 156 "It is also important to
get used to index variables, because multilevel models (Chapter 13)
depend upon them.")


---

> "The mistake of accepting the null hypothesis." (page 158)


---

Question 5E3 on page 159 jokes (I think?) about the effects of amount
of funding and size of laboratory on time to PhD, but I'm not sure I
know what he thinks is funny...
