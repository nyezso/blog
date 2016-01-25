---
layout: post
title: How to create UML class diagrams
author: Martin Thoma
date: 2012-05-06 20:38:01.000000000 +02:00
categories:
- My bits and bytes
tags:
- LaTeX
- MetaUML
- UML
- Dia
featured_image: 2012/05/UML-thumb.png
---
<h2>Dia</h2>
Creating UML diagrams with Dia works like a charm! It provides some default tools. You should simply try it. Dia is a free tool.

Take a look at these screenshots:
{% caption align="aligncenter" width="231" caption="Create a class for a class diagram in Dia" url="../images/2012/05/dia-create-class.png" alt="Create a class for a class diagram in Dia"  height="611" class="size-full wp-image-24211" %}

{% caption align="aligncenter" width="676" caption="Edit class properties in Dia" url="../images/2012/05/dia-class-properties.png" alt="Edit class properties in Dia"  height="589" class="size-full wp-image-24221" %}

{% caption align="aligncenter" width="454" caption="Customizing associations in Dia - adding multiplicities is so much easier in Dia than in MetaUML!" url="../images/2012/05/dia-association.png" alt="Customizing associations in Dia"  height="447" class="size-full wp-image-24231" %}

{% caption align="aligncenter" width="519" caption="A quick example for a class diagram created with Dia" url="../images/2012/05/Dia-ClassDiagram.png" alt="A quick example for a class diagram created with Dia"  height="104" class="size-full wp-image-24251" %}

<h2>LaTeX</h2>
I only know MetaUML for creating class diagrams entirely in LaTeX. Does anybody know something different? 

Of course, you can include a diagram created with Dia:
<ol>
  <li>Export the diagram as PNG (antialized)</li>
  <li>Add something like that to your tex-file: \includegraphics[width=180mm]{myDiagramm.png}</li>
</ol>


<h3>MetaUML</h3>
A MetaUML class diagram looks like that in code (saved as myMetaDiagram.mp):

{% highlight text %}input metauml;
beginfig(1);
	Class.World("World")
		   ("-age: int",
			"#ressources: List") 
		   ("+sayHello(): void");

	Class.NoHuman("Human")
		   ("-birthday: Date",
			"-nickname: String",
			"-secret: String") 
		   ("+code(language: Language): Program");

	leftToRight(50)(World, NoHuman);
	drawObjects(World, NoHuman);

	link(aggregation)(NoHuman.w -- World.e);
	item(iAssoc)("1")(obj.n     = .2[World.e,NoHuman.w]);
	item(iAssoc)("has >")(obj.n = .5[World.e,NoHuman.w]);
	item(iAssoc)("0..*")(obj.n  = .8[World.e,NoHuman.w]);

endfig;
end{% endhighlight %}

You have to execute mpost before you can compile LaTeX. A working example is in this <a href='../images/2012/05/UML.zip'>UML Archive</a>.

It looks like that in your generated PDF file:
{% caption align="aligncenter" width="676" caption="MetaUML class diagram" url="../images/2012/05/MetaUML-class-diagram.png" alt="MetaUML class diagram"  height="161" class="size-full wp-image-24271" %}

<h2>See also</h2>
<ul>
  <li>Wikipedia: <a href="http://en.wikipedia.org/wiki/Class_diagram">Class diagram</a>, <a href="http://en.wikipedia.org/wiki/Dia_(software)">Dia</a></li>
  <li>Dia:  <a href="http://www.wspiegel.de/infogk12/oops/dia_einf.html#py16_2">Dia und UML</a></li>
  <li><a href="http://ftp.fernuni-hagen.de/ftp-dir/pub/mirrors/www.ctan.org/graphics/metapost/contrib/macros/metauml/doc/metauml_manual_0.2.5.pdf">MetaUML: Tutorial, Reference and Test Suite</a></li>
  <li>Freies Magazin, Mai 2012: <a href="http://www.freiesmagazin.de/freiesMagazin-2012-05">Astah &ndash; Kurzvorstellung des UML-Programms</a> (German)</li>
</ul>