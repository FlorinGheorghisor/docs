---
layout: postag
title: 'PRON'
shortdef: 'pronoun'
---

Traditional grammars of Slavic languages do not distinguish pronouns from pro-adjectives (determiners, [sla-pos/DET]()),
hence it is important to define a consistent borderline here. (Some authors, e.g. Sussex and Cubberley (2006) do use
the term _determiner_ in Slavic languages but they rely on common understanding without precisely delimiting them.)

In order to provide the broader picture, we describe both pronouns and determiners here;
the page [sla-pos/DET]() is empty.

## Personal pronouns

Non-possessive personal pronouns are tagged `PRON PronType=Prs` (see also the [sla-feat/PronType]() feature).
Third-person pronouns are formed as inflections on one stem and should have one lemma, the masculine singular nominative form.
(In fact there are two stems: one for the nominative and the other for the remaining cases. But the point is that the stems
do not change with gender or number.)
The first and second person pronouns are formed from different stems in singular and plural. However, to be consistent,
the singular nominative form should be used as lemma for both (all) numbers in the given person. Thus in [cs], the lemma
of _my_ is _já_ and the lemma of _vy_ is _ty._
Reflexive pronouns have their own lemma (one lemma for both clitic and non-clitic forms).
Since they lack the nominative form, the lemma should be the clitic accusative form, which is arguably the most frequent one.

List of nominative forms of personal pronouns (accusative for reflexives) in various languages:

* [cs] _já, ty, on, ona, ono, my, vy, oni, ony, ona, se_
* [sk] _ja, ty, on, ona, ono, my, vy, oni, ony, sa_
* [hsb] _ja, ty, wón, wona, wono/wone, mój, wój, wonaj, wonej, my, wy, woni, wone, so_
* [pl] _ja, ty, on, ona, ono, my, wy, oni, one, się_
* [ru] _я, ты, он, она, оно, мы, вы, они, ся_
* [sl] _jaz, ti, on, ona, ono, midva, vidva, onadva, mi, vi, oni, one, ona, se_
* [hr] _ja, ti, on, ona, ono, mi, vi, oni, one, ona, se_
* [bg] _аз, ти, той, тя, то, ние, вие, те, се_
* [cu] _азъ, тꙑ, мꙑ, вꙑ, и, сѧ_

## Possessive pronouns

The words that are traditionally called possessive pronouns are in fact possessive determiners and should be tagged
`DET Poss=Yes | PronType=Prs`. First and second person possessives, and the reflexive possessive, function like adjectives.
They precede the modified (possessed) noun and concord with it in gender, number and case.
In the South Slavic languages the same can be said also about third person possessives.
In the north, third person possessives evolved from (or are still identical to) the genitive form of the personal pronoun,
and they do not inflect.
However, they are traditionally distinguished from the personal pronoun, they are placed before the possessed noun
(unlike nominal genitive modifiers), and for consistency we tag them `DET` as well.
Similar to adjectives, one lemma covers all _inflections_ for gender, number and case, governed by the modified noun.
Inherent gender, number and person of the possessor do not play a role, i.e. _můj_ “my” and _náš_ “our” are two distinct lemmas.

* [cs] _můj, tvůj, jeho, její, náš, váš, jejich, svůj_
* [sk] _môj, tvoj, jeho, jej, náš, váš, ich, svoj_
* [hsb] _mój, twój, jeho, jeje, naš, waš, jich, swój_
* [pl] _mój, twój, jego, jej, nasz, wasz, ich, swój_
* [ru] _мой, твой, его, её, наш, ваш, их, свой_
* [sl] _moj, tvoj, njegov, njen, najin, vajin, njun, naš, vaš, njihov, svoj_
* [hr] _moj, tvoj, njegov, njezin/njen, naš, vaš, njihov, svoj_
* [bg] _мой, твой, негов, неин, наш, ваш, техен, свой_
* [cu] _мои, твои, его, еѩ, ею, нашь, вашь, ихъ, свои_

## Demonstratives

All demonstrative “pronouns” inflect for gender and can modify nouns, which places them in the `DET` category.
If the noun phrase is missing, it can be explained by ellipsis, at least for the masculine and feminine forms.
Certain neuter singular forms ([cs] _to, toto, tohle, tamto_)
are also frequently used to refer to unspecified or general entities, that is, they are used in these situations more
like pronouns than like determiners.

There are two possible solutions:

1. Tag all demonstratives `DET PronType=Dem`. The lemma is always masculine singular nominative.
2. As 1., with the exception that selected neuter singular forms are ambiguous and may also appear as `PRON PronType=Dem`.
   Then the lemma is neuter singular nominative. Disambiguation has to be done by context: if it pre-modifies
   a noun phrase and concords with it in gender, number and case, it is determiner; otherwise it is pronoun.

* [cs] _ten, tento, tenhle, tamten, onen, takový, týž, tentýž_

## Pronouns derived from “who, what”

These are always `PRON` and never `DET`. They fall into various pronominal types:
interrogatives, relatives (“who, what”), indefinites (“somebody, something, anybody, anything”) and negatives (“nobody, nothing”).
They inflect for case but not for gender and number;
“who” functions as singular masculine,
“what” as singular neuter.

(TO CHECK: Even in Bulgarian?)

* [cs] _kdo, co, což, někdo, něco, kdokoli, cokoli, nikdo, nic_
* [sk] _kto, čo, niekto, niečo, nikto, nič_
* [hsb] _štó, što, štóž, štož, kiž, něchtó, něšto, něchtóžkuli, něštožkuli, nichtó, ničo_
* [pl] _kto, co, ktoś, coś, nikt, nic_
* [ru] _кто, что, кто-нибудь, что-нибудь, никто, ничто_
* [sl] _kdo, kaj, nekdo, nekaj, nihče, nič_
* [hr] _tko, što, neki, nešto, nitko, ništa_
* [bg] _кой, кое, някой, нещо, никой, нищо_
* [cu] _къто, чьто, нѣкъто, нѣчьто, никътоже, ничьтоже_

## Determiners derived from “which, whose”, total and other determiners

In some Slavic languages there are two interrogative pronouns/determiners corresponding to [en] “which”:
one that represents a selection, “which one” ([cs] _který_);
and one that queries a quality, “what kind of” ([cs] _jaký_).
Both can be used as relative pronouns/determiners, too.
Their inflection is fully adjectival, therefore they should be tagged `DET`,
despite the fact that when they are used as relative determiners,
the modified noun is not there and its absence cannot be explained by ellipsis
(but it is the noun modified by the entire relative clause).

In addition, there is a possessive interrogative determiner corresponding to [en] “whose” ([cs] _čí_).

There are also derived indefinite and negative determiners, using the same affixes as with “who, what”;
only the negative determiner “no” corresponding to “which” contains a different stem ([cs] _žádný_).

We also include the total determiner “every” ([cs] _každý_) here, although it is quite frequently used
without the modified noun, with the meaning “everybody, everyone”; the decisive factor here is its
undoubtedly adjectival inflection.
In contrast, we do not include the total pronoun “all / everything” ([cs] _všichni / všechno_),
see below.

* [cs] _který, jaký, čí, některý, nějaký, něčí, kterýkoli, jakýkoli, každý, nijaký, ničí, žádný_
* [sk] _ktorý, aký, čí, niektorý, nejaký, niečí, ktorýkoľvek, akýkoľvek, každý, nijaký, ničí, žiaden/žiadny_
* [hsb] _kotry, kajki, čeji, kotryž, kajkiž, čejiž, někotry, někajki, něčeji, někotryžkuli, někajkižkuli, něčejižkuli, kóždy, ničeji, žadyn_
* [pl] _który, jaki, któryś, jakiś, każdy, żaden_
* [ru] _который, какой, чей, некоторый, который-нибудь, какой-нибудь, чей-нибудь, каждый, никакой, ничей_
* [sl] _kateri, kak, čigav, kakršen, nekateri, nek, nekakšen, nikakršen, noben_
* [hr] _koji, kakav, čiji, nekakav, nikakav_
* [bg] _кой, какъв, чий, който, какъвто, чийто, някой, някакъв, нечий, никой, никакъв_
* [cu] _которꙑи, кꙑи, каковъ, чии, нѣкꙑи, никоторꙑиже, никꙑиже_

Note: In [sl], the pronoun _kar_ corresponds to [cs] _který_. Its inflection is not adjectival
(the treebank contains only four forms: _kar_ (`Nom`, `Acc`), _česar_ (`Gen`), _čemer_ (`Loc`) and _čimer_ (`Ins`)),
hence it is pronoun and not determiner.

## Pronominal quantifiers

All pronominal quantifiers are tagged `DET`.
They are morphologically and syntactically different from adjectives and other determiners.
They are much closer to cardinal numerals but they cannot get the `NUM` tag, which is reserved for definite quantities.

Note that the meaning of [pl] _tylko_ has shifted towards “only”, which makes it an adverb rather than a demonstrative quantifier.
A similar shift may have happened in some of the other languages, too.
The interrogative _kolik_ may be used as relative, except in [hsb] and [bg].
Occasionally it may be also used as indefinite ([pl] _kilka_).

* [cs] _kolik, tolik, několik_
* [sk] _koľko, toľko, niekoľko_
* [hsb] _kelko, kelkož, telko_
* [pl] _kilka_
* [ru] _сколько, столько, несколько_
* [sl] _koliko_
* [hr] _koliko_
* [bg] _колко, колкото_
* [cu] _колико_

## Indefinite quantifiers and adverbs of degree

There is a relatively small group of words that lie on the borderland between [adverbs](sla-pos/ADV), [numerals](sla-pos/NUM)
and pronouns/determiners: [cs] _mnoho_ “many”, _hodně_ “much”, _málo_ “little, few”. They may denote the degree of
an adjective or verb, and they can be compared: _více_ “more”, _nejvíce_ “most”, _méně_ “less, fewer”, _nejméně_ “least, fewest”.
These are typical properties of adverbs.
However, they can also denote an indefinite quantity when they take a genitive nominal argument.
This follows the typical behavior of numerals. The whole phrase (numeral + noun) works like a noun phrase, can become
argument of a verb and some of the numerals even inflect for case: _s mnoha body_ “with many points” (`Case=Ins`).
When it acts as subject, it is regarded as neuter singular for subject-verb agreement.

~~~ sdparse
Trenér sázel mnohem více na herní stránku než na kondici .
advmod(více, mnohem)
advmod(sázel, více)
dobj(sázel, stránku)
nmod(více, kondici)
~~~

As adverb, _více_ is comparative form of lemma _hodně_.
As indefinite numeral, it is its own lemma (but I found only two occurrences in UD Czech).

~~~ sdparse
Bude vybráno více zájemců .
nsubjpass(vybráno, zájemců)
det:numgov(zájemců, více)
~~~

The two syntactic functions are not compatible.
The words in this group should thus receive two different tags, disambiguated by context.
When they denote quantity, their tag will be `DET NumType=Card | PronType=Ind`.
When they denote degree, their tag will be `ADV`.

* [cs] _mnoho, moc, dost, příliš, hodně, více, nejvíce, málo, méně, nejméně, nemnoho, nemálo_
* [sk] _veľa, viac, najviac, málo, menej, najmenej_
* [pl] _dużo, wiele, więcej, najwięcej, mało, mniej, najmniej_
* [sl] _mnogo, veliko, več, največ, malo, manj, najmanj, zelo, bolj, najbolj, dosti_
* [hr] _mnogo, više, najviše, malo, manje, najmanje, vrlo, dosta_
* [bg] _много, повече, най-вече_

## References

* Roland Sussex, Paul Cubberley. 2006. _The Slavic Languages._ Cambridge: Cambridge University Press.
