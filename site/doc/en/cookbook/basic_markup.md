Problem
-------

Use the basic HTML markup : bold, italic, headers...


Solution
--------


<table width="100%">
<tr>
<td style="width:50%;">

    <html>
    <head>
    <script src="brython.js"></script>
    </head>
    <body onload="brython()">
    
    <script type="text/python">
    from browser import document, html
    
    document['zone'] <= html.H1("Introducing Brython")
    document['zone'] <= html.H4(html.I("Python in the browser"))
    document['zone'] <= html.B("Hello world !")
    </script>
    
    </body>
    </html>

<button id="fill_zone">Test it</button>
</td>
<td id="zone" style="background-color:#FF7400;text-align:center;">Initial content<p>
</td>
</tr>
</table>

<script type="text/python3">
from browser import document, html

def fill_zone(ev):
    document['zone'] <= html.H1("Introducing Brython")
    document['zone'] <= html.H4(html.I("Python in the browser"))
    document['zone'] <= html.B("Hello world !")

document['fill_zone'].bind('click', fill_zone)
</script>

`B` is a function defined in the module `browser.html`, matching the HTML tag `<B>` (bold)

`B("text")` returns an object matching the HTML `<b>text</b>`

All HTML tags have their own function : `I, H1, H2,...`. You can nest functions, as shown in the second line :

    document <= html.H4(html.I("Python in the browser"))

