---
title: Missing Female Births Calculation
subtitle: The correct way to compuate missing female births
summary: The correct way to compuate missing female births
authors:
- Christophe Z Guilmoto
- Alex R. Cook
- admin
tags: [missing female birth]
categories: []
date: "2019-05-01T00:00:00Z"
featured: false
draft: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: "Missing female births around the world during 1970--2017 (see [PNAS Fig.3](https://www.pnas.org/content/116/19/9303))"
  focal_point: ""

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: [sex ratio at birth]

---
![Missing female births around the world during 1970--2017 (see [PNAS Fig.3](https://www.pnas.org/content/116/19/9303))](./featured.png)

## Background
Our PNAS Correction highlighted the updated number of missing female birhts using the correct method. We explore in this post why our previous method is wrong (which is not trivial to figure out).

## The Introduction of the ``Missing Female'' Calculation
We believe that the first known computation of missing women is introduced by Dreze and Sen in 1989 in their book [_Hunger and Public Action_](https://www.oxfordscholarship.com/view/10.1093/0198283652.001.0001/acprof-9780198283652), introducing the basic following equation:
$$\text{missing}= \text{expected} - \text{estimate}$$

![_Hunger and Public Action_ laid the foundation of quantifying female deficits](./jean-sen_book.jpg)


Demographic methods have since improved in the way the expected number is computed and Christophe Z Guilmoto introduced for instance in [UNFPA 2012 report](https://www.unfpa.org/sites/default/files/pub-pdf/Sex%20Imbalances%20at%20Birth.%20PDF%20UNFPA%20APRO%20publication%202012.pdf) the method where the expected number at age $a$ is computed with $R(a,e)$, the average SR observed at age $a$ among non-discriminating and non-migrating populations with the same life expectancy $e$ (method improved in [Bongaarts & Guilmoto 2015](http://www.demographie.net/guilmoto/pdf/PDR%202015%20Bongaarts_Guilmoto.pdf)):
$$N_f^E(a)= \frac{N_m(a)}{R(a,e)}$$
where $N_f^E(a)$ refers to the expected number of females at age $a$, $N_m(a)$ refers to the observed (i.e. actual) number of males at age $a$.

## The Right and Wrong Methods
When applied the method to compute the number of missing female births, we have:
$$B_f^E = \frac{B_m}{R^E}$$
where $B_f^E$ is the expected number of female births, $B_m$ is the observed number of male births, and $R^E$ is the sex ratio at birth under natural circumstance. The number of missing female births based on the correct method is:
$$B_f^* = B_f^E - B_f$$
where $B_f$ is the observed number of female births.

In our PNAS paper before the correction, we used the following method to compute the number of missing female births:
$$B_f^{E'} = \frac{B}{1+R^E}$$
where $B_f^{E'}$ denotes the expected female births based on our previous method which is wrong. $B$ refers to the total number of observed birhts (i.e. male plus female births). The number of missing female births based on the wrong method is: $B_f^{*'} = B_f^{E'} - B_f$.

## Decipher the Wrong Method
P. M. Kulkarni (a renowned demographer and former Professor of Centre for Study in Regional Development ([CSRD](https://www.jnu.ac.in/sss/csrd)) in Jawaharlal Nehru University, New Delhi) pointed out that the method to compute $B_f^{E'}$ was incorrect because it simply postulated a redistribution of existing births, and not a net decrease of births due to gender discrimination.

And here is the catch: if you examine the observed SRB under a veil of ignorance (a la John Rawls), you would have be perfectly entitled to use the $B_f^{E'}$ method. In fact, according to [Laurent Toulemon](https://www.ined.fr/en/research/researchers/Toulemon+Laurent) from INED, one could very well imagine that people could have more boys thanks to the use of special pills or sexual positions. Maybe he had in mind [the novel by Amin Maalouf](https://www.wikiwand.com/en/The_First_Century_after_Beatrice) in which people start bearing sons thanks to a mysterious drug. 

![_The First Century after Beatrice_ by Amin Maalouf](./maalouf_book.jpg)

But the fact is that when we come to the $B_f^{E'}$, we tend to forget that this method also yields a mysterious surplus of male births ($SMB$). And doing the maths will show you in fact that $SMB = B_f^{*'}$. You may further notice that the correct calculation $B_f^*$ is about twice of the wrong one $B_f^{*'}$:
$$SMB + B_f^{*'} = 2 \times B_f^{*'} > B_f^* = B_f^{*'} \times (1+\frac{1}{R^E}).$$
But there is no contradiction here in this lack of equality between $SMB+ B_f^{*'}$ and $B_f^*$. In fact, if you convert this EMB into FB, you get EMB/srb, which summed up with MFB1 yields
$$\frac{B_f^{*'}}{R^E} + B_f^{*'} = B_f^{*'} (1+\frac{1}{R^E}) = B_f^*.$$

But we are talking about deliberate sex selection of girls, not about selective procreation of boys (though the latter may be happening at small scale in _laissez-faire_ countries like the US or Taiwan). This process of discrimination works through (fetal) birth _reduction_.  In fact, it is very close to the process of ``selective reduction'' in multiple pregnancies which artificially inflate the number of multiple births. The surplus of missing births is therefore only apparent and results in fact from the elimination of female births.


### A Statistacian's view
One of the counterintuitive example to show that the wrong method is indeed wrong is the China's one-child policy. Here, we are looking at an extreme case, such that given the number of families that are able to give births, the total number of births is fixed regardless the existence of sex-selective abortions. So it gives the dellusion that the wrong method is ``correct'' in the sense that the total number of births is unchanged.

Assume that there are 100 families plan to have babies. Let $m_i$ be the number of male pregnancies and $f_i$ the number of female pregnancies initiated by family $i$. Let the baseline (i.e. reference level) sex ratio at birth for China be $R^E=1.06$ according to the [PNAS paper](https://www.pnas.org/content/116/19/9303). The probability of conceiving a boy [^1], $\pi_b$, is then
$$\pi_b = \frac{\sum_i^{100}m_i}{\sum_i^{100}(m_i+f_i)} = \frac{R^E}{1+R^E} = \frac{1.06}{1+1.06} \approx 0.515.$$

If we assume that a fraction $\theta$ of families would abort any daughters they have until they get a son, then for such families the number of aborted females follows a geometric distribution $\mathcal{G} (\pi_b)$ with mean
$$\frac{\pi_g}{\pi_b} = \frac{1-\pi_b}{\pi_b} = \frac{1-0.515}{0.515} \approx 0.943,$$
where we assume $\pi_g=1-\pi_b$. Hence, each such family has lost an average of 0.943 female births. Let $M_i$ and $F_i$ be the number of male and female births for family $i$ respectively. Assume that for one-child policy, for each family, we have $M_i+F_i=1$. Then, the fraction of families that have a boy is:
$$Pr(M_i=1)=\pi_b (1-\theta)+\theta = p_b.$$
$p_b$, the actual proportion of male births among all births in a population, is a function of the actual (or in China's case masclinized) sex ratio at birth be $R$ which is for example's sake 1.20, i.e. 120 male births for every 100 female births. We have:
$$p_b = \frac{R}{1+R} = \frac{1.2}{1+1.2} \approx 0.545.$$

Given the values of $\pi_b$ and $p_b$, we can solve $\theta$. This means that for the 100 families, the number of aborted baby girls due to the desire for a baby boy for our example is:
$$\theta \cdot \frac{\pi_g}{\pi_b} \cdot 100 \approx 0.064 \times 0.943 \cdot 100 \approx 6.$$
Hence, the 100 children that families had was in fact the results of many 106 ``attempts'' (not the correct methodology) out of which 6 female births were prevented.

We end up with the same result by using the direct approach to compute the number of missing female births:
$$B_f^E = 54.5/1.06 = 51.4$$
$$B_f = 100 - 54.5 = 45.5$$
$$B_f^* = 51.4 - 45.5 \approx 6.$$


[^1] The reasoning in terms of sex ratio at conception may take us into troubled waters. First, we would also have to factor in the sex differentials in fetal survival (male intrauterine mortality is higher than the female), and the resulting equation will be less elegant. Second, this primary sex ratio is still one of the biologists' holy graal for lack of solid data. And when you examine current hypotheses, things look indeed pretty messy (see [PNAS here](https://www.pnas.org/content/112/16/E2102.short)).



