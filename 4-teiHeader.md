Text Encoding Initiative – `teiHeader`
===

# Modules
* [`header`](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/HD.html) (obligatoire)
* Certains modules optionnels peuvent compléter la définition du contenu du `teiHeader`, pour des emplois spécialisés :
  * `variantEncoding` (module `textcrit`)
  * `msDesc` (module `msdescription`)
Certaines métadonnées sont donc obligatoires pour TOUS les documents TEI. Mais le modèle de métadonnées est à définir (calibrer) pour chaque projet, selon ses besoins spécifiques.

Très grande expressivité. Comparer les choix faits par différents projets (BVH, Elec, BFM, )…  
Enjeux de la spécification ?  
Implémentation de référence ?

# `teiHeader` Obligatoire
```xml
<teiHeader>
  <fileDesc>
    <titleStmt>
      <title>Title</title>
    </titleStmt>
    <publicationStmt>
      <p>Publication Information</p>
    </publicationStmt>
    <sourceDesc>
      <p>Information about the source</p>
    </sourceDesc>
  </fileDesc>
</teiHeader>
```
* [`fileDesc`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-fileDesc.html) : description bibliographique du fichier ([2.2 The File Description](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/HD.html#HD2))
* [`titleStmt`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-titleStmt.html) : mention de titre ([2.2.1 The Title Statement](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/HD.html#HD21))
* [`publicationStmt`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-publicationStmt.html) : mention de publication ([2.2.4 Publication, Distribution, Licensing, etc.](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/HD.html#HD24))
* [`sourceDesc`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-sourceDesc.html) : description de la source ([2.2.7 The Source Description](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/HD.html#HD3))

## Des règles de nommage
* `*Stmt` : contenu structuré en sous-éléments (type « base de données »).
* `*Desc` : description, en prose courante, pouvant être structurée en sous-éléments.

On trouvera aussi :
* `*Decl` : série de déclarations, associant structuration en sous-éléments et description en prose.

## Les métadonnées nécessaires pour partager les textes / les corpus.
D’autres initiatives permettent de réfléchir…  
Détour par [OAI](http://www.openarchives.org/).
> L'***Open Archives Initiative*** **(initiative pour des archives ouvertes)**, généralement abrégée en **OAI**, est un projet qui vise à faciliter l'échange et la valorisation d'archives numériques. Elle permet à des fournisseurs de services de moissonner des métadonnées sur les sites de fournisseurs de données. Il est ainsi possible d'utiliser un protocole OAI pour créer un outil de recherche simultanée dans plusieurs bases de données bibliographiques.  
[...]  
L'implémentation technique de ce concept est définie dans l'*Open Archives Initiative Protocol for Metadata Harvesting* (OAI-PMH). Ce protocole, basé sur XML et le **[Dublin Core](https://fr.wikipedia.org/wiki/Dublin_Core#Liste_des_.C3.A9l.C3.A9ments_et_raffinements)** permet l'échange de métadonnées entre fournisseurs de données et fournisseurs de services. La dernière version disponible est la 2.0.  
–– <cite>https://fr.wikipedia.org/wiki/Open_Archives_Initiative</cite>

La documentation d’une telle implémentation peut nous guider dans la définition des champs obligatoires et aussi (et surtout) de la normalisation des valeurs. Par ordre alphabétique :
* `dc:contributor` : obligatoire ? xpath ? datatype ?
* `dc:creator` : obligatoire ? xpath ? datatype ?
* `dc:date` : obligatoire ? xpath ? datatype ?
* `dc:description` : obligatoire ? xpath ? datatype ?
* `dc:identifier` : obligatoire ? xpath ? datatype ?
* `dc:language` : obligatoire ? xpath ? datatype ?
* `dc:publisher` : obligatoire ? xpath ? datatype ?
* `dc:rights` : obligatoire ? xpath ? datatype ?
* `dc:subject` : obligatoire ? xpath ? datatype ?
* `dc:title` : obligatoire ? xpath ? datatype ?

On pourrait explorer avec profit d’autres mapping (Unimarc ? Onix ?)

## Reprise
```txt
teiHeader
  fileDesc
    titleStmt
      title
      author (@key, @ref)
    publicationStmt
      publisher
      date (@when)
      availability (@status)
        licence (@target)
      idno
    sourceDesc
      bibl
        title, author, date, etc.
  profileDesc
    creation
      date (@when, @notBefore, @notAfter)
    langUsage
      language (@ident)
```

```xml
<teiHeader>
  <fileDesc>
    <titleStmt>
      <title>Dissertation sur la condemnation des théâtres</title>
      <author key="Aubignac, François Hédelin (1604-1676 ; abbé d')">Abbé d'Aubignac</author>
      <editor key="Mainardi, Chiara">Chiara Mainardi</editor>
    </titleStmt>
    <publicationStmt>
      <publisher>Université Paris-Sorbonne</publisher>
      <date when="2014"/>
      <idno>http://obvil.paris-sorbonne.fr/corpus/haine-theatre/aubignac_dissertation_1666/</idno>
      <availability status="restricted">
        <licence target="http://creativecommons.org/licenses/by-nc-nd/3.0/fr/"/>
      </availability>
    </publicationStmt>
    <sourceDesc>
      <bibl><author>D'Aubignac</author>, <title>Dissertation sur la condemnation des théâtres</title>, <pubPlace>Paris</pubPlace>, <publisher>N. Pépingué</publisher>, <date>1666</date>.</bibl>
    </sourceDesc>
  </fileDesc>
  <profileDesc>
    <creation>
      <date when="1666"/>
    </creation>
    <langUsage>
      <language ident="fr"/>
    </langUsage>
  </profileDesc>
</teiHeader>
```

# Les choses se compliquent vite…
* `sourceDesc/msDesc`
* `sourceDesc/biblFull` ?
* Pourquoi inscrit-on ces métadonnées ?

Un `sourceDesc` détaillé : dans le cas d’une rétro-numérisation, on peut souhaiter exprimer les principaux champs de la notice bibliographique du livre source (grâce à un import MarcXML ou ONIX depuis un OPAC).
```xml
<sourceDesc>
  <bibl>Marc Bloch, <title>Apologie pour l’histoire ou métier d’historien</title>, Cahier des Annales, 3, Librairie Armand Colin, Paris, 2<hi rend="sup">e</hi> édition, 1952, 112 pages. (1<hi rend="sup">ère</hi> éd. 1949).</bibl>
  <biblFull>
    <titleStmt>
      <title>Apologie pour l’histoire ou métier d’historien</title>
      <author>Marc Bloch</author>
    </titleStmt>
    <seriesStmt>
      <title ref="http://www.sudoc.fr/001027468">Cahier des Annales</title>
      <idno type="ISSN">0755-1487</idno>
      <biblScope type="vol">3</biblScope>
    </seriesStmt>
    <publicationStmt>
      <publisher>Librairie Armand Colin</publisher>
      <pubPlace>Paris</pubPlace>
      <date when="1952"/>
    </publicationStmt>
    <extent ana="pp" n="112"/>
    <notesStmt>
      <note type="abstract">
        <ref type="ppn" n="010052690" target="http://www.sudoc.fr/010052690"/>
        <ref type="worldcat" n="422040961" target="http://www.worldcat.org/search?q=no%3A422040961"/>
      </note>
    </notesStmt>
  </biblFull>
</sourceDesc>
```

# `teiHeader` Optionnel
## préciser `fileDesc`
* `editor`,?
* `seriesStmt`
* `notesStmt`

## préciser `publicationStmt`
* `address`
* `distributor`

## préciser `profileDesc`
* `textClass`, `keywords`, etc.

```xml
<textClass>
  <keywords scheme="http://data.bnf.fr/liste-rameau">
    <term type="subject" key="http://data.bnf.fr/ark:/12148/cb133199588">Langages de balisage</term>
    <term type="subject" key="http://data.bnf.fr/ark:/12148/cb131774360">XML (langage de balisage)</term>
  </keywords>
  <keywords scheme="http://id.loc.gov/authorities/subjects.html">
    <term type="subject" key="http://id.loc.gov/authorities/subjects/sh95002796">Document markup languages</term>
    <term type="subject" key="http://id.loc.gov/authorities/subjects/sh97007825">XML (Document markup language)</term>
  </keywords>
</textClass>
</profileDesc>
```

## `editionStmt`
```xml
<editionStmt>
  <edition>ENC</edition>
  <respStmt>
    <name xml:id="CD">Camille Desenclos</name>
    <resp when="2010">Relecture, édition XML-TEI</resp>
  </respStmt>
  <respStmt>
    <name xml:id="JBC">Jean-Baptiste Camps</name>
    <resp when="2017">Informatique éditoriale</resp>
    <resp when="2016">Restructuration TEI</resp>
  </respStmt>
</editionStmt>
```

## `encodingDesc`: description de l'encodage
Discuter les [examples](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/examples-encodingDesc.html).
Notamment `editorialDecl/correction`
