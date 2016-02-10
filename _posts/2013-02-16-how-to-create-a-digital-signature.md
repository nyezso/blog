---
layout: post
title: How to create a digital signature
author: Martin Thoma
date: 2013-02-16 11:34:54.000000000 +01:00
categories:
- Cyberculture
tags:
- LaTeX
- Inkscape
- GIMP
- signature
- SVG
featured_image: 2013/02/inkscape-remove-nodes-thumb.png
---
At first, you have to write your signature on a white sheet of paper. You might have to make several tries:

{% caption align="aligncenter" width="512" caption="Some tries for a nice signature" url="../images/2013/02/signature-tries.jpg" alt="Some tries for a nice signature"  height="230" class="size-full wp-image-57241" %}

Then you should scan it in a high quality. Now crop the image to the size you like. I have used <a href="http://www.gimp.org/">GIMP</a> for this task:

{% caption align="aligncenter" width="300" caption="Crop the image to the correct section with GIMP" url="../images/2013/02/crop-to-selection-300x216.png" alt="Crop the image to the correct section with GIMP"  height="216" class="size-medium wp-image-57251" %}

Now you should have an image like this one:
{% caption align="aligncenter" width="300" caption="Cropped signature" url="../images/2013/02/max-mustermann-cropped-signature-300x60.jpg" alt="Cropped signature"  height="60" class="size-medium wp-image-57261" %}

<h2>Inkscape</h2>
Open it with <a href="http://inkscape.org/download">Inkscape</a>, click on the image go to the menu "Path > Trace Bitmap":

{% caption align="aligncenter" width="300" caption="Trace Bitmap in Inkscape" url="../images/2013/02/inkscape-trace-bitmap-300x244.png" alt="Trace Bitmap in Inkscape"  height="244" class="size-medium wp-image-57271" %}

Now choose "Colors", check "Remove background" and click on "Update":
{% caption align="aligncenter" width="300" caption="Trace Bitmap: Settings" url="../images/2013/02/trace-bitmap-settings-300x216.png" alt="Trace Bitmap: Settings"  height="216" class="size-medium wp-image-57291" %}

Close the window and look closely at the image. It should now look like this:
{% caption align="aligncenter" width="300" caption="Traced bitmap in Inkscape" url="../images/2013/02/traced-bitmap-in-inkscape-300x73.png" alt="Traced bitmap in Inkscape"  height="73" class="size-medium wp-image-57301" %}

You have to click at a part of the image that is currently not selected and then hit the remove key. 

Now select the "Edit path by nodes" tool:
{% caption align="aligncenter" width="300" caption="Edit path by nodes" url="../images/2013/02/edit-path-by-nodes-300x167.png" alt="Edit path by nodes"  height="167" class="size-medium wp-image-57311" %}

Click on the gray area. The image will look like this:
{% caption align="aligncenter" width="300" caption="Remove nodes" url="../images/2013/02/remove-nodes-in-inkscape-300x204.png" alt="Remove nodes"  height="204" class="size-medium wp-image-57321" %}

Remove nodes of areas that have to many or where you don't want to have this gray area. This will take some time.
{% caption align="aligncenter" width="300" caption="Some nodes you should remove" url="../images/2013/02/inkscape-remove-nodes-300x247.png" alt="Some nodes you should remove"  height="247" class="size-medium wp-image-57331" %}

As soon as you're finished, you should save your signature as SVG (if you want to edit it later) and as PDF (for LaTeX).

<h2>LaTeX</h2>

```latex
\documentclass[a4paper,12pt]{article}
\usepackage{pdfpages}  % needed for includepdf

\begin{document}
\section*{Some Text}
Lorem ipsum dolor sit amet, pro discere accusam detraxit ei. Ei 
maluisset definitiones ius. Ut quo persius reprimique, sed ea 
postulant consulatu, essent tibique et cum. Usu ne etiam facilis, 
eam everti eruditi ea, his ad eros sententiae. Cu amet admodum 
recteque mei.

Postea aeterno officiis pri in, per te quis numquam, ius ei veri 
consul. Ei sententiae constituam vix, ad quidam noster bonorum mel. 
Eu ius rebum disputationi, invenire signiferumque mei ea. Euripidis 
expetendis argumentum sit eu, viris latine persecuti mel at. Mel ut 
clita fabellas laboramus, an discere inermis est.

Nulla liberavisse usu in. Augue comprehensam ut pro, ne vel dicit 
oblique. Vel dico omnium et, vis an tota solum argumentum. Eam 
omnes quidam in. Eu eam illum malorum diceret, nonumes mentitum 
repudiare eam et.\\

\noindent Yours faithfully\\
\\
\includegraphics[height=10mm]{max-mustermann-cropped-signature.pdf}\\
Max Mustermann
\end{document}
```

<h2>Result</h2>
The result looks like this:

{% caption align="aligncenter" width="300" caption="A signed document, created with LaTeX" url="../images/2013/02/latex-signed-300x141.png" alt="A signed document, created with LaTeX"  height="141" class="size-medium wp-image-57351" %}

It looks even better if you make the image a little bit darker in the first step with GIMP.