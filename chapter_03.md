### Chapter 3

Selections and commentary from Aaron:


---

I'm reading Ellenberg's _How Not to Be Wrong_, and he says on page 49:
"In mathematics, you very seldom get the clearest account of an idea
from the person who invented it."

I have that feeling in connection with Gelman and Pearl (not sure they
completely invented things they're associated with, but still): I feel
like McElreath is doing a better job of explaining things, and it's
super nice.

Also Ellenberg:

> "If a tiny state like South Dakota experiences a rash of brain
> cancer, you might presume that the spike is in large measure due to
> luck, and you might estimate that the rate of brain cancer in the
> future is likely to be closer to the overall national number. You
> could accomplish this by taking some kind of weighted average of the
> South Dakota rate with the national rate. But how to weight the two
> numbers? That's a bit of an art, involving a fair amount of
> technical labor I'll spare you here." (pages 70-71)

I think he's referring to [multi-level modeling][], in the Gelman
style.

[multi-level modeling]: https://en.wikipedia.org/wiki/Multilevel_model


---

This common medical testing scenario appeared in a recent
LearnedLeague one-day on statistics:

> "Suppose that 1% of a population has a particular genetic mutation,
> and a test for the mutation is 99% accurate for both positive and
> negative cases. In other words, if someone with the mutation takes
> the test, there is a 99% chance that the test comes back positive;
> if someone without the mutation takes the test, there is a 99%
> chance that the test comes back negative. If a randomly-selected
> person takes the test and gets a positive result, what is the
> probability that the person actually has the mutation? (Express your
> answer as a fraction in lowest terms.)"

I solved it by seeing that 0.01 * 0.99 == 0.99 * 0.01, which is sort
of like what McElreath says is called "frequency format" or "natural
frequencies." I definitely thought of it in terms of "quantity," but
as percentages rather than counts. I was surprised when Erica referred
to the problem as "the Bayesian" problem, because I hadn't thought of
it that way. So I agree with McElreath that it isn't uniquely Bayesian.


---

> "Changing the representation of a problem often makes it easier to
> address or inspires new ideas that were not available in an old
> representation. In physics, switching between Newtonian and
> Lagrangian mechanics can make problems much easier. In evolutionary
> biology, switching between inclusive fitness and multilevel
> selection sheds new light on old models. And in statistics,
> switching between Bayesian and non-Bayesian representations often
> teaches us new things about both approaches." (page 50)


---

> "I avoid discussing the analytical approach
> [of conjugate priors, etc.] in this book, because very few problems
> are so simple that they have exact analytical solutions like this
> [the beta-binomial conjugate prior]." (page 560, note for page 51)


---

The "Why statistics can't save bad science" box on page 51 is neat.


---

Just to establish equivalence between R and Python...

```r
dbinom(6, size=9, prob=0.5)
## [1] 0.1640625
```

```python
import scipy.stats
scipy.stats.binom(n=9, p=0.5).pmf(6)
## 0.16406250000000006
```


---

Interesting: using "compatibility interval" rather than "credible
interval" (or "confidence interval") in the sense of "compatible with
the model and data." (page 54)


---

> "Overall, if the choice of interval type
> [percent interval or highest posterior density interval] makes a big difference, then you shouldn't be using intervals to summarize the posterior." (page 58)


---

> "There is no way to really be sure that software works correctly."
> (page 64)


---

Hmm; his HPDI (Highest Posterior Density Interval) [implementation][]
itself relies on the implementation in [coda][]...

[implementation]: https://github.com/rmcelreath/rethinking/blob/3b48ec8dfda4840b9dce096d0cb9406589ef7923/R/utilities.r#L106
[coda]: https://cran.r-project.org/package=coda

How hard is this really to implement? If you have a histogram or just
sorted counts, every left point determines one interval, so you could
do it in one pass with a little farting around to find the right point
each time, and a running smallest interval... Really not so
computation-intensive.


---

```r
birth1 <- c(1,0,0,0,1,1,0,1,0,1,0,0,1,1,0,1,1,0,0,0,1,0,0,0,1,0,
0,0,0,1,1,1,0,1,0,1,1,1,0,1,0,1,1,0,1,0,0,1,1,0,1,0,0,0,0,0,0,0,
1,1,0,1,0,0,1,0,0,0,1,0,0,1,1,1,1,0,1,0,1,1,1,1,1,0,0,1,0,1,1,0,
1,0,1,1,1,0,1,1,1,1)
birth2 <- c(0,1,0,1,0,1,1,1,0,0,1,1,1,1,1,0,0,1,1,1,0,0,1,1,1,0,
1,1,1,0,1,1,1,0,1,0,0,1,1,1,1,0,0,1,0,1,1,1,1,1,1,1,1,1,1,1,1,1,
1,1,1,0,1,1,0,1,1,0,1,1,1,0,0,0,0,0,0,1,0,0,0,1,1,0,0,1,0,0,1,1,
0,0,0,1,1,1,0,0,0,0)
table(birth1, birth2)
##        birth2
##  birth1  0  1
##       0 10 39
##       1 30 21
```

So really, what _is_ up with this data?
