---
layout: post
title: Eclipse f&uuml;r SWT I einrichten
author: Martin Thoma
date: 2012-04-25 22:25:11.000000000 +02:00
categories:
- German posts
tags:
- KIT
- Java
- svn
- SWT I
- eclipse
featured_image: 2012/04/eclipse-logo.png
---
<div class="info">SWT I ist das Modul Softwaretechnik I am <a href="http://de.wikipedia.org/wiki/Karlsruher_Institut_f%C3%BCr_Technologie">KIT</a>. Dieser Blogpost richtet sich also vor allem an Studenten des KIT von Herrn <a href="http://www.ipd.uka.de/Tichy/people.php?id=15">Prof. Dr. Tichy</a>. Ich arbeite au&szlig;erdem mit Ubuntu Linux. Die momentan aktuellste Version nennt sich Oneiric Ocelot und kann bei <a href="http://wiki.ubuntuusers.de/Downloads/Oneiric_Ocelot">UbuntuUsers</a> heruntergeladen werden. Das System k&ouml;nnte z.B. in <a href="http://wiki.ubuntuusers.de/VirtualBox">VirtualBox</a> installiert werden.</div>
<a id="more"></a><a id="more-22911"></a>

<h2>Installation</h2>
F&uuml;r die Installation von Java, Subversion (SVN), Eclipse und Checkstyle samt Dokumentation muss folgendes in der Konsole eingegeben werden:
{% highlight bash %}sudo apt-get install openjdk-6-jre openjdk-6-jdk openjdk-6-source openjdk-6-demo openjdk-6-doc openjdk-6-jre-headless openjdk-6-jre-lib subversion libapache2-svn eclipse checkstyle checkstyle-doc{% endhighlight %}

Dann werden etwa 276 MB an Archiven heruntergeladen und 662 MB an zus&auml;tzlichen Packeten installiert. Bei meiner Internetverbindung (DSL 1000 :-( ) hat das ca 40 Minuten gedauert.

<h2>CheckStyle</h2>
Siehe eclipse-cs.sourceforge.net mit <a href="http://eclipse-cs.sourceforge.net/downloads.html">detaillierten Installationsanweisungen</a>. 

<h2>Subversive</h2>
Siehe eclipse.org: <a href="http://www.eclipse.org/subversive/downloads.php#indigo_stable">Download Suversive</a>.
Diese Erkl&auml;rung ist aber nicht so toll.

Nach der Installation und dem Neustart von Eclipse muss man das "Subversive Connector Kit" ausw&auml;hlen. Kurz in der Konsole {% highlight bash %}svn --version{% endhighlight %} eingeben. Bei mir ist anscheinend Subversion in der Version 1.6.12 installiert. Also w&auml;hle ich "SVN Kit 1.3.7".

Zuerst muss man den SVN Connector installieren:
{% highlight text %}http://community.polarion.com/projects/subversive/download/eclipse/2.0/update-site/{% endhighlight %}
Das macht man wie mit CheckStyle.

Dann muss man Subversive installieren:
{% highlight text %}http://download.eclipse.org/technology/subversive/0.7/update-site/{% endhighlight %}
Auch hier macht man es wie mit CheckStyle.

Sobald alles klappt, sieht es etwa so aus:
{% caption align="aligncenter" width="666" caption="Subversive plugin in Eclipse" url="../images/2012/04/eclipse-subversive.png" alt="Subversive plugin in Eclipse"  height="434" class="size-full wp-image-23271" %}

{% caption align="aligncenter" width="300" caption="Commit mit Subversive unter Eclipse" url="../images/2012/04/subversive-300x290.png" alt="Commit mit Subversive unter Eclipse"  height="290" class="size-medium wp-image-23751" %}

<h2>Grundeinstellungen</h2>
Als erstes sollte man mal auf "Window" -> "Open Perspective" -> "Java" klicken.

<h2>Siehe auch</h2>
<ul>
  <li><a href="http://wiki.ubuntuusers.de/Downloads">Ubuntu Downloads</a></li>
  <li><a href="http://wiki.ubuntuusers.de/Java/Installation/Oracle_Java">Oracle Java - Manuelle Installation unter Ubuntu</a>.</li>
  <li>Weitere UbuntuUsers Artikel: <a href="http://wiki.ubuntuusers.de/Eclipse">Eclipse</a>, <a href="http://wiki.ubuntuusers.de/Subversion">Subversion</a></li>
  <li><a href="../software-versioning-cheat-sheet/" title="Software Versioning Cheat Sheet">Software Versioning Cheat Sheet (Subversion / GIT)</a></li>
  <li>Wikipedia: <a href="http://de.wikipedia.org/wiki/Eclipse_(IDE)">Eclipse</a>, <a href="http://de.wikipedia.org/wiki/Apache_Subversion">Subversion</a></li>
  <li>Wiki Books: <a href="http://de.wikibooks.org/wiki/Java_Standard:_Erste_Schritte">Java Standard: Erste Schritte</a> (habe ich NICHT gelesen! Aber f&uuml;r unsere Physiker ist das eventuell hilfreich.)</li>
</ul>