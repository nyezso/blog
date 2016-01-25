---
layout: post
title: Semantische Sicherheit
author: Martin Thoma
date: 2013-04-28 15:06:53.000000000 +02:00
categories:
- German posts
tags:
- IT-Security
- Theoretical computer science
featured_image: 2013/04/cryptography-thumb.png
---
In der <a href="http://www.iks.kit.edu/fileadmin/User/Lectures/Sicherheit/SoSe13/Sicherheit_VL03.pdf">Vorlesung vom 25.04.2013</a> hat Prof. Hofheinz gesagt, dass man semantische Sicherheit praktisch nicht beweisen kann, da man zuerst $\mathcal{P} \neq \mathcal{NP}$ beweisen müsste. Warum das so ist, versuche ich nun zu erläutern.

<h2>Einwegfunktionen und $\mathcal{P} \neq \mathcal{NP}$</h2>
<div class="definition">
Sei $f:X \rightarrow Y$ eine Funktion.
$f$ hei&szlig;t eine Einwegfunktion, genau dann wenn für alle $x \in X$ gilt:
<ul>
  <li>$y := f(x)$ kann in Polynomialzeit berechnet werden</li>
  <li>Für die Berechnung eines Urbildes $x$ aus $y$ existiert kein randomisierter Algorithmus, der in Polynomialzeit läuft.</li>
</ul>
</div>

Es gilt: Wenn eine Einwegfunktion $f$ existiert, dann gilt $\mathcal{P} \neq \mathcal{NP}$.

Warum?

Nun, angenommen es gibt eine Einwegfunktion $f$. Dann sei die formale Sprache $L_f$ definiert durch:

$L_f := \{(\bar x, y) | \exists x: \bar x \text{ ist Präfix von } x \text{ und } y = f(x)\}$

Es gilt: $L_f \notin \mathcal{P}$, da für ein gegebenes $y$ das zugehörige $x$ in polynomialzeit bestimmt werden könnte (wie will man sonst prüfen, ob $\bar x$ ein Präfix von $x$ ist?)

Falls jemanden diese Begründung nicht ausreicht ist hier noch ein Beweis von Prof. Hofheinz (Danke!)

<strong>Beh.:</strong> $L_f \notin \mathcal{P}$
<strong>Bew.:</strong> durch Widerspruch
<u>Annahme.:</u> $L_f \in P$
$\Rightarrow$ Es existiert ein Polyzeit-Algorithmus $\mathcal{A}$ für $L_f$, der bei Eingabe $(\bar x, y)$ entscheidet, ob ein $x$ mit $f(x)=y$ und Präfix $\bar x$ existiert oder nicht. Dann können wir einen Algorithmus $\mathcal{B}$ aus $\mathcal{A}$ bauen, der $f$ invertiert.

Gegeben $y$ verfährt $\mathcal{B}$ wie folgt:
$\mathcal{B}$ ruft $\mathcal{A}(0,y)$ auf und erfährt so, ob ein Urbild $x$ von $y$ mit Anfangsbit $0$ existiert. Wenn ja, ruft $\mathcal{B}$ den Algorithmus $\mathcal{A}(00,y)$ auf, wenn nein ruft $\mathcal{B}$ den Algorithmus $\mathcal{A}(10,y)$ auf usw.

So wird ein Urbild $x$ bitweise bestimmt. Ein solches $\mathcal{B}$ findet also effizient Urbilder, im Widerspruch zur Einwegannahme über $f \blacksquare$

Aber: Wenn das $x$ gegeben ist, dann ist es einfach zu zeigen, dass $y= f(x)$ gilt und damit auch, ob $\bar x$ ein Präfix von $x$ ist. Damit ist $L_f \in \mathcal{NP}$.

Damit gilt: $L_f \in \mathcal{NP} \setminus \mathcal{P}$.
Wenn aber $\mathcal{NP} \setminus \mathcal{P} \neq \emptyset$, dann gilt insbesondere $\mathcal{P} \neq \mathcal{NP}$.

An dieser Stelle sollte man also einsehen, dass eine Einwegfunktion nach obiger Definition nur existieren kann, wenn $\mathcal{P} \neq \mathcal{NP}$ gilt.

<h2>Semantische Sicherheit</h2>
<a href="http://de.wikipedia.org/wiki/Sicherheitseigenschaften_kryptografischer_Verfahren#Semantische_Sicherheit">Wikipedia</a> gibt folgende Beschreibung von semantischer Sicherheit:

<blockquote>Ein Verschlüsselungsverfahren ist semantisch sicher, wenn jeder Angreifer jede Information, die er aus einem Chiffrat über die Nachricht ableiten kann, bereits dann ableiten kann, wenn er nur die Länge des Chiffrats kennt. Ein Chiffrat verrät also nichts über eine Nachricht als ihre Länge.</blockquote>



Herr Prof. Hofheinz hat folgende informelle Definition von Semantischer Sicherheit in der Vorlesung gegeben:

<div class="definition">
Ein symmetrisches Verschlüsselungsverfahren ist semantisch sicher, wenn es für jede $M$-Verteilung, jede Funktion $f$ und jeden PPT-Algorithmus $\mathcal{A}$ einen PPT-Algorithmus $\mathcal{B}$ gibt, so dass

$Pr \left [\mathcal{A}^{\text{Enc}(K, \cdot)}(\text{Enc}(K, M)) = f(M) \right ] - Pr [\mathcal{B}(\varepsilon) = f(M)]$

vernachlässigbar (als Funktion im Sicherheitsparameter $K$) ist.
</div>

Hier ist 
<ul>
  <li>$M$ eine Nachricht (Message),</li>
  <li>$\text{Enc(K, M)}$  die Verschlüsselung einer konkreten Nachricht $M$ mit dem Schlüssel $K$,</li>
  <li>$\varepsilon$ eine triviale Information (ich glaube das ist z.B. die Länge des Ciphertextes) und</li>
  <li>$f$ extrahiert beliebige Informationen aus dem Plaintext</li>
</ul>

Die erste Wahrscheinlichkeit bezeichnet die Möglichkeit, aus dem Ciphertext Informationen der Art $f$ über den Plaintext $M$ zu erhalten.
Die zweite Wahrscheinlichkeit bezeichnet die Möglichkeit &bdquo;aus dem Nichts&ldquo; Informationen über eine Nachricht zu erhalten. Damit will man triviale Informationen eliminieren. Insgesamt gibt es also die Wahrscheinlichkeit an, nicht-triviale Informationen aus einer Verschlüsselten Nachricht zu erhalten. Mit effizient ist vermutlich in Polynomialzeit gemeint.

Wenn es nun mehrfach benutzbare semantisch sichere Verfahren gibt, dann kann man dieses Verfahren als Einwegfunktion nutzen. Wenn eine Einwegfunktion existiert, gilt $\mathcal{P} \neq \mathcal{NP}$. Also folgt:

Wenn es nun mehrfach benutzbare semantisch sichere Verfahren existieren, gilt $\mathcal{P} \neq \mathcal{NP}$. Dies ist aber eines der <a href="http://de.wikipedia.org/wiki/Millennium-Probleme">Millennium-Probleme</a> und noch nicht geklärt.