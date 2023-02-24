title: Activate all languages on pages created via API

----

version: 1.0.1

----

authors: dragan

----

tags: pages, multilanguage

----

problem:
You have a multi-language setup and just created pages via api, but only the default language is activated on them.

----

solution:
If you want to activate all languages, use this after your page-creation API script. In this real-life scenario I had to import product pages, hence the template-selector below.
```PHP
$pages->setOutputFormatting(false);
$pag = $pages->find("template='product'");
foreach($pag as $p) {
    foreach($languages as $lang) {
      if($lang->isDefault()) continue;
      $p->set("status$lang", 1);
      $p->save();
    }
}
```

----

resources:
* [Dragan's ProcessWire code snippets](https://github.com/dragan1700/pw/blob/master/activateAllLanguages.php)
