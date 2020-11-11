### Chapter 6: The Haunted DAG & The Causal Terror

Selections and commentary from Aaron:


---

On page 161 he starts with Berkson's Paradox, suggesting
"selection-distortion effect" as a better name. Dave suggested a nice
example: shorter basketball players in the NBA are better 3 point
shooters.


---

> "Let's bein with the least of your worries: multicollinearity."
> (page 163)

This can "smear out" your estimates, because it isn't clear which
variables to put beta weight on.


---

Section 6.2 (page 170) uses "post-treatment bias" to refer to what I
might call a mediator, and what he later calls a "pipe" situation
(page 185).


---

> "The "d" [in d-separation] stands for _directional_." (page 174)

> "You'll often see the "d" in d-separation defined as "dependency."
> That would certainly make more sense. But the term d-separation
> comes from a more general theory of graphs. Directed graphs involve
> d-separation and undirected graphs involve instead u-separation."
> (page 563)


---

> "No statistical procedure can substitute for scientific knowledge
> and attention to it." (page 175)


---

> "If a procedure cannot figure out the truth in a simulated example,
> we shouldn't trust it in a real one." (page 177)


---

> "So I'm sorry to say that we also have to consider the possibility
> that our DAG may be haunted." (page 180)

The thing haunting it (as in the title of the chapter) is unmeasured
causes that induce collider bias, which means conditioning on things
we have can induce bias about effects we're trying to measure.


---

I like "the four elemental confounds" on page 185. They're pretty
similar to the cases I included in
[What should be in your regression?][].

[What should be in your regression?]: https://planspace.org/20200912-what_should_be_in_your_regression/


---

The explanation of shutting the back-door on pages 184-185 is better
than others I've seen, I think. And then on page 186 he shows how
everybody's favorite [dagitty][] can do it automatically.

Front-door isn't mentioned until page 460.


---

On page 186, he says "Conditioning on C is the better idea, from the
perspective of efficiency, since it could also help with the precision
of the estimate of X➔Y." This seems reasonable since C is closer to Y,
but I feel like a little more explanation wouldn't have been a bad
thing here.


---

> "In fact, domain specific structural causal models can make causal
> inference possible even when a DAG with the same structure cannot
> decide how to proceed." (page 188)

Say more? Like, a footnote? An endnote? Some kind of reference to more
information? Seems so mysterious!


---

> "Sometimes, in order to avoid multicollinearity, people inspect
> pairwise correlations among predictors before including them in a
> model. This is a bad procedure, because what matters it the
> conditional association, not the association before the variables
> are included in the model." (page 189)
