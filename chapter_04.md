### Chapter 4

Selections and commentary from Aaron:


---

> "Linear regression is the geocentric model of applied statistics."
> (page 71)


---

Frank's [The common patterns of nature][] seems pretty neat, getting
into how common distributions come from processes and information
considerations...

[The common patterns of nature]: https://onlinelibrary.wiley.com/doi/pdf/10.1111/j.1420-9101.2009.01775.x


---

> "Multiplying small numbers is approximately the same as addition."
> (page 74)


---

On page 76 he shows "precision" as τ, meaning 1/σ^2, and it shows up
in the equation for the Gaussian with π, which is an example of
notation that doesn't work particularly well with
[the tau manifesto][].

[the tau manifesto]: https://tauday.com/


---

"procrustean" (on page 77): "(especially of a framework or system)
enforcing uniformity or conformity without regard to natural variation
or individuality."


---

I like the [spark][] histograms!

[spark]: https://en.wikipedia.org/wiki/Sparkline

Oh, neat, they're even [called][] "histosparks"...

[called]: https://github.com/rmcelreath/rethinking/blob/f9c16bb7faec8a9883d976a769824b1764d12540/R/precis.r#L72

And I might have guessed... they're [from][] Hadley.

[from]: https://rdrr.io/github/hadley/precis/src/R/histospark.R

So there are unicode characters that do blocks of various sizes, by
eighths... It looks like Hadley only uses some of them:

```r
sparks <- c("\u2581", "\u2582", "\u2583", "\u2585", "\u2587")
#             1/8       2/8       3/8       5/8       7/8
```

Can look these up for example here: https://www.fileformat.info/info/unicode/char/2581/index.htm

" ▁▂▃▄▅▆▇█" has all the heights, with a normal blank at the beginning.

So why does Hadley only use some of the available heights? Not sure.

Oh look at that! In my terminal those all look fine, but in a browser (maybe it depends on font?) the half and full blocks go lower than the others! Still doesn't explain why 6/8 is missing from Hadley's list... Maybe it looks bad in other fonts?

Let's try it fixed-width:

```
 ▁▂▃▄▅▆▇█
```

Yup, looks much nicer in fixed width.

Here's another nice place to see these: https://en.wikipedia.org/wiki/Block_Elements


---

> "E. T. Jaynes (1922-1988) called this the _mind projection fallacy_,
> the mistake of confusing epistemological claims with ontological
> claims." (page 81)

And a fun reference to [Monkeys, Kangaroos, and N](https://bayes.wustl.edu/etj/articles/cmonkeys.pdf):

> "... I think you will find that 90% of the past confusions and
> controversies in statistics have been caused, not by mathematical
> errors or even ideological differences; but by the technical
> difficulty that the two parties had different problems in mind, and
> failed to realize this. Thinking along different lines, each failed
> to perceive at all what the other considered too obvious to
> mention." (Jaynes)


---

> "There's also a tradition called _dimensionless analysis_ that
> advocates constructing variables so that they are unit-less ratios."
> (page 94)

I haven't heard about this as such, I think. Dimension_al_ analysis is
more well known, but not quite the same thing...


---

Interesting to recall that in the first edition, what's now called
`quap` (quadratic approximation posterior / a posteriori?) was called
`map` (maximum a posteriori?)


---

> "My experience is that many natural and social scientists have
> naturally forgotten whatever they once knew about logarithms." (page
> 98)


---

> "... most social and natural scientists have never had much training
> in probability theory and tend to get very nervous around ∫'s."
> (page 106)


---

He repeats it in different ways here and there, but I noted it again
on page 107: I like his effort at clarity between "small world" and
"large world" claims, where small world is "assuming the model" or "in
the world of the model."


---

When doing the quadratic example, he z-scores but does not
decorrelate... The default behavior in R (using [poly][]) is to
"compute orthogonal polynomials"... I'm not sure how common that is
elsewhere.

[poly]: https://www.rdocumentation.org/packages/stats/versions/3.6.2/topics/poly

Okay I'll look at sklearn... Here's somebody with a nice Python
implementation:
http://davmre.github.io/blog/python/2013/12/15/orthogonal_poly But as
far as I can tell there isn't anything "built in" for Python...


---

page 111: `weight.s` is used in one listing, while `weight_s` is used
in another, which is a very mild kind of inconsistency. ([PR][])

[PR]: https://github.com/rmcelreath/rethinking/pull/279


---

> "We should feel embarrassed to use [linear models], just so we don't
> become satisfied with the phenomenological explanations they
> provide." (page 113)


---

I really liked section 4.5.2 on splines; I don't think I ever saw a
good explanation of splines before.


---

> "Matrix algebra is a stressful topic for many scientists." (page 119)


---

In both R listings 4.76 and 4.79, it's a little unintuitive to me in
that it doesn't seem obvious that `w` is a vector. In `w ~ dnorm(0,
10)`, that `dnorm` returns just one number. Somewhere `quap` is
figuring out how many elements it needs, I guess?


---

For question 4H8 on page 122, it asks what else would have to change
if the intercept was removed from the model. I think the answer is
just the priors on the other coefficient(s), since they'd have to get
the mean all the way to where it needs to be by themselves then.
And/or maybe the data couldn't be centered, because making the mean
zero would really hurt the ability to have the result be right? It
would still be okay if both x and y were centered, at least for simple
designs.
