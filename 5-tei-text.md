Text Encoding Initiative – Structuration du texte
===

Module obligatoire [`text structure`](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/DS.html)

**Structure générale du fichier TEI**
```xml
<text>
  <front>
    <titlePage/>
    <div type="?"/>
  </front>
  <body>
    <div/>
  </body>
  <back>
    <div type="?"/>
  </back>
</text>  
```
**NB.** Cas particuliers des collections de textes et des textes composites : `teiCorpus` (module `core`) et `group` (module `textstructure`).

**Divisions et subdivisions du texte**
```xml
<div type="?" xml:id="?" n="?">
  <head>Titre de la division</head>
  <div type="?" xml:id="?" n="?">
    <head>Titre de la subdivision</head>
    <p>Premier paragraphe</p>
    <p>Deuxième paragraphe</p>
  </div>
  <div type="?" xml:id="?" n="?">
    <head>Titre de la subdivision</head>
    <p>Premier paragraphe</p>
    <p>Deuxième paragraphe</p>
  </div>
</div>
```

**Quelques structures éditoriales de niveau bloc**
* paragraphe : `p`
* strophe et vers : `lg`, `l`
* liste : `list`et `item`
* tableau : `table`, `row`, `cell`
* image : `figure`, `graphic`
* bloc de code : `eg`
* note (de bas de page) : `note`(`@resp`, `@place`, etc.) – et en HTML ?

** Bloc ou caractère ?**
* citation : `quote` (voir [3.3.3 Quotation](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/CO.html#COHQQ)), `cit`
* référence bibliographique : `bibl`

**Quelques structures éditoriales de niveau caractère**
* typographie : `emph`, `hi` (`@rend`)
* segmentation : `seg`
* passage en langue étrangère : `foreign`

**structuration matérielle**
* changement de page : `pb` (`@n`, `@facs`)
* changement de colonne : `cb`
* changement de ligne : `lb`

**Entités nommées**
* personne : `author`, `persName`
* lieu : `placeName`
