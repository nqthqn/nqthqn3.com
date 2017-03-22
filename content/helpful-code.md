+++
date = "2017-03-19T19:08:21-07:00"
menu = "main"
title = "Helpful Code"
type = "page"

+++

Invert the colors on a page.

```
javascript:(function(){var b = document.getElementsByTagName('body')[0]; b.style.filter = "invert(100%)"; b.style.background="#000"; var imgs = document.getElementsByTagName('img'); for (var i=0; i<=imgs.length; i++) {imgs[i].style.filter = "invert(100%)"; } })()
```

Make json pretty using python.

```
python -m json.tool ugly.json > pretty.json
```

