---
layout: post
title: Statistik - Klausur
slug: statistik-vorlesung
author: Martin Thoma
date: 2017-01-15 17:30
category: German posts
tags: Klausur, Statistik
featured_image: logos/klausur.png
---
<div class="info">Dieser Artikel beschäftigt sich mit der Vorlesung &bdquo;Statistik&ldquo; am KIT. Er dient als Prüfungsvorbereitung. Ich habe die Vorlesungen bei <a href="http://www.math.kit.edu/stoch/~klar/de">Herrn Prof. Dr. Bernhard Klar</a> im Wintersemester 2016 / 2017 gehört. Der Artikel ist noch am Entstehen</div>

## Behandelter Stoff

### Vorlesung

<table>
<tr>
    <th>#</th>
    <th>Datum</th>
    <th>Kapitel</th>
    <th>Inhalt</th>
</tr>
<tr>
    <td>?</td>
    <td>09.01.2017</td>
    <td>Kapitel 5.4</td>
    <td>Tests im klassischen linearen Modell: Überflüssige Parameter in Regressionsmodellen entfernen</td>
</tr>
</table>


### Kapitel 1: Parameterschätzung

<dl>
    <dt><dfn>Stichprobenraum</dfn></dt>
    <dd>Der Stichprobenraum $\mathfrak{X}$ ist eine Menge von Daten.</dd>
    <dt><dfn>Statistisches Modell</dfn></dt>
    <dd>Ein Tupel $(\mathfrak{X}, (P_\theta)_{\theta \in \Theta})$ heißt
        <i>statistisches Modell</i>, wenn $\mathfrak{X}$ ein Stichprobenraum
        und $(P_\theta)_{\theta \in \Theta}$ eine Familie von
        Verteilungen $P_\theta$ ist, welche durch $\theta \in \Theta$
        parametrisiert ist.
        </dd>
    <dt><dfn>Schätzer</dfn></dt>
    <dd>Sei $(\mathfrak{X}, (P_\theta)_{\theta \in \Theta})$ ein statistisches
        Modell und $T: \mathfrak{X} \rightarrow \tilde{\Theta}$ eine Abbildung.
        Dann heißt $T$ ein Schätzer für $\theta$.</dd>
    <dt><dfn>Maximum-Likelihood-Schätzer</dfn></dt>
    <dd>TODO</dd>
    <dt><dfn>Momentenschätzer</dfn></dt>
    <dd>TODO</dd>
    <dt><dfn>Starkes Gesetz großer Zahlen</dfn></dt>
    <dd>TODO</dd>
    <dt><dfn>Score-Funktion</dfn></dt>
    <dd>TODO</dd>
    <dt><dfn>Fisher-Information</dfn></dt>
    <dd>TODO</dd>
    <dt><dfn>Cramér-Rao Ungleichung</dfn></dt>
    <dd>TODO</dd>
    <dt><dfn>Cauchy-Schwarz Ungleichung</dfn></dt>
    <dd>TODO</dd>
    <dt><dfn>Zentraler Grenzwertsatz</dfn></dt>
    <dd>TODO</dd>
    <dt><dfn>Verteilungskonvergenz</dfn></dt>
    <dd>TODO</dd>
    <dt><dfn>Score-Gleichung</dfn></dt>
    <dd>TODO</dd>
</dl>


### Kapitel 2: Konfidenzbereiche

<dl>
    <dt><dfn>Konfidenzintervall</dfn> (<dfn>Vertrauensintervall</dfn>)</dt>
    <dd>TODO</dd>
</dl>


### Kapitel 3: Statistische Tests

TODO


### Kapitel 4: 2-Stichproben Vergleiche (NV)

TODO


### Kapitel 5: Lineare Regression
TODO

<dl>
    <dt>Satz 5.4.1</dt>
    <dd>Unter $H_0$ ist die Teststatistik $F = \frac{(RSS_r - RSS)/(p-r)}{RSS/(n-p)}$ Fischer-verteilt mit $p-r$ Zähler- und $n-p$ Nenner-Freiheitsgraden.</dd>
</dl>


### Kapitel 6: Varianz- und Kovarianzanalyse
TODO

### Kapitel 7: Kategoriale Daten
TODO

### Kapitel 8: Nichtparametrische Verfahren
TODO


## Symbolverzeichnis

<table class="table">
    <tr>
        <th>Symbol</th>
        <th>Bedeutung</th>
    </tr>
    <tr>
        <td>$\mathcal{N}(\mu, \sigma^2)$</td>
        <td>Normalverteilung mit Mittelwert $\mu$ und Standardabweichung $\sigma$</td>
    </tr>
    <tr>
        <td>$Pois(\lambda)$</td>
        <td>Poisson-Verteilung</td>
    </tr>
    <tr>
        <td>$\mathfrak{X}$</td>
        <td>Stichprobenraum</td>
    </tr>
    <tr>
        <td>$X \sim A$</td>
        <td>Die Zufallsvariable $X$ ist $AB$-Verteilt.</td>
    </tr>
</table>


## Verteilungen

<table>
    <tr>
        <th>Verteilung</th>
        <th>Schreibweise</th>
        <th>$\mathbb{E}(X)$</th>
        <th>$Var(x)$</th>
        <th>Bemerkung</th>
    </tr>
    <tr>
        <td><a href="https://de.wikipedia.org/wiki/Binomialverteilung">Binomial-Verteilung</a></td>
        <td>$X \sim Bin(n, p)$</td>
        <td>$n \cdot p$</td>
        <td>$n \cdot p \cdot (1-p)$</td>
        <td>$n$-maliges Bernoulli-Experiment</td>
    </tr>
    <tr>
        <td><a href="https://de.wikipedia.org/wiki/Poisson-Verteilung">Poisson-Verteilung</a></td>
        <td>$X \sim Pois(\lambda)$</td>
        <td>$\lambda$</td>
        <td>$\lambda$</td>
        <td></td>
    </tr>
    <tr>
        <td><a href="https://de.wikipedia.org/wiki/Exponentialverteilung">Exponential-Verteilung</a></td>
        <td>$X \sim Exp(\lambda)$</td>
        <td>$\frac{1}{\lambda}$</td>
        <td>$\frac{1}{\lambda^2}$</td>
        <td>Zerfall-Prozess</td>
    </tr>
    <tr>
        <td><a href="https://de.wikipedia.org/wiki/Normalverteilung">Normalverteilung</a></td>
        <td>$X \sim \mathcal{N}(\mu, \sigma^2)$</td>
        <td>$\mu$</td>
        <td>$\sigma^2$</td>
        <td></td>
    </tr>
    <tr>
        <td><a href="https://de.wikipedia.org/wiki/Gleichverteilung">Gleichverteilung</a></td>
        <td>$X \sim U[a, b]$</td>
        <td>$\frac{b-a}{2}$</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td><a href="https://de.wikipedia.org/wiki/Chi-Quadrat-Verteilung">$\chi^2$-Verteilung</a></td>
        <td>$X \sim \chi^2_n$</td>
        <td>$n$</td>
        <td>$2n$</td>
        <td>Summe von $n$ normalverteilugen Zuvallsvariablen $X_1, \dots, X_n$</td>
    </tr>
    <tr>
        <td><a href="https://de.wikipedia.org/wiki/Studentsche_t-Verteilung">$t$-Verteilung</a></td>
        <td>$X \sim t_k$</td>
        <td>$n$</td>
        <td>$2n$</td>
        <td>$X = \frac{N}{\sqrt{\frac{Y}{k}}}$ mit $Y \sim \chi^2_k$ und $N \sim \mathcal{N}(0, 1)$</td>
    </tr>
    <tr>
        <td><a href="https://de.wikipedia.org/wiki/F-Verteilung">$F$-Verteilung</a></td>
        <td>$X \sim F_{m,n}$</td>
        <td>$\frac{n}{n-2}$ für $n > 2$</td>
        <td>$\frac{2n^2 (m+n-2)}{m(n-2)^2 (n-4)}$ für $n > 4$</td>
        <td>$X = \frac{\frac{1}{r}R}{\frac{1}{s}S}$ mit $R \sim \chi^2_r$, $S \sim \chi^2_s$</td>
    </tr>
</table>


## Python

You might want to look into [`scipy.stats`](https://docs.scipy.org/doc/scipy/reference/stats.html)
as it offers many convenient functions.

For example, if you have to find the 95%-Quantile of the $F_{k=3,n=19}$ distribution,
this is what you do:

```python
import scipy.stats

# Create a variable representing the distribution
rv = scipy.stats.f(dfn=3, dfd=19)

# Percent point function
rv.ppf(0.95)  # gives 3.1273500051133989
```

## Klausur Aufbau

* Momentenschätzer bestimmen
* ML-Schätzer bestimmen
* asymptotisch Erwartungstreue / konsistenz von Schätzern
* MQA
* Score-Funktion / Fischer-Information
* Cramer-Rao-Schranke
* Exp-Verteilung
* 1-Stichproben t-Test
* Neymann-Pearson-Test
* Zentraler GWS
* kleinser Quadrate Schätzer
* Binomial-Verteilung
* Satz von Student
* F-Tests
* Rechenregeln:
    * $C(U_1 + U_2, V) = C(U_1, V) + C(U_2, V)$
    * $C(AU, B^T V) = A C(U, V) B$



## Material und Links

* [Vorlesungswebsite](http://www.math.kit.edu/stoch/lehre/stat2016w/)
* [Illias](https://ilias.studium.kit.edu/ilias.php?ref_id=603377&cmd=frameset&cmdClass=ilrepositorygui&cmdNode=75&baseClass=ilRepositoryGUI)
* StackExchange
    * [Percentile vs quantile vs quartile](http://stats.stackexchange.com/q/156778/25741)
    * [When is Fishers exact test used; when are approximative tests used?](http://math.stackexchange.com/q/2120746/6876)


## Literatur

* [<a href="#ref-bic01-anchor" name="ref-bic01">Bic01</a>] P.J. Bickel and K.A. Doksum. Mathematical statistics, 2nd ed.
* [<a href="#ref-cza11-anchor" name="ref-cza11">Cza11</a>] C. Cazado and T. Schmidt. Mathematische Statistik.


## Übungsbetrieb

Übungsblätter sind freiwillig.


## Termine und Klausurablauf

**Datum**: 01.03.2017, 7:30 - 9:30 Uhr (Quelle: <a href="http://www.math.kit.edu/stoch/lehre/stat2016w/event/statklausur1/">Vorlesungswebsite</a> - Ja, es ist wirklich so früh!)<br/>
**Ort**: <a href="https://www.kithub.de/map/2086">Benz-Hörsaal Geb. 10.21</a><br/>
**Punkte**: TODO<br/>
**Zeit**: TODO<br/>
**Punkteverteilung**: TODO<br/>
**Bestehensgrenze**: TODO<br/>
**Übungsschein**: gibt es nicht<br/>
**Bonuspunkte**: gibt es nicht<br/>
**Erlaubte Hilfsmittel**: TODO