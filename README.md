<p align="center"><img src="preview.jpg?v=4" /></p>
<h1 align="center">language-de</h1>
<p align="center">German translations for WonderCMS</p>
<p align="center">Translation author: Masha Pogorevc</p>

<br><br>

This plugin adds German translations to the WonderCMS Settings/admin area.

![](https://images.stanisic.nl/5oBG9Zaw/qU1dXIyr)

## How to use
1. Login to your WonderCMS website.
2. Click "Settings" and click "Plugins".
3. Find plugin in the list and click "install".

## How this works

The translations are all in the de.csv file. Why in CVS? That's how all
other major CMSes do it, so there must be a good reason for it.

You will see something like this a lot: 

```
SECTION NAME
	"> Some text","> Wat tekst"
```

The 'parser' skips all lines that are not equal to two values, so SECTION NAME (contains one value) is skipped.
All the pairs are in the `preg_replace` regex format. That's all this does. The prepending of `>` and `> ` makes sure that we only match the contents of a tag.

This way, `> Security` will match in 
```
<a href="#security" aria-controls="security" role="tab" data-toggle="tab" class="nav-link">Security</a>
```
and it won't match in
```
<div class="btn-group w-50"><button type="submit" class="btn btn-success" name="betterSecurity" value="on">ON (warning: may break your website)</button></div>
<div class="btn-group w-50"><button type="submit" class="btn btn-danger" name="betterSecurity" value="off">OFF (reset htaccess to default)</button></div>
```


