*Text Encoding Initiative* – introduction
===

# Partager des balises, échanger des fichiers
* 1987 : établissement de la *Text Encoding Initiative*.
* 1990 : [TEI P1 (proposal 1)](http://www.tei-c.org/Vault/Vault-GL.html), dir. Michael Sperberg-McQueen et Lou Burnard.
* 1992-1993 : TEI P2, expansion.
* 1994 : [TEI P3](http://www.tei-c.org/Vault/GL/P3/index.htm), première version complète.
* 2000 : naissance du TEI Consortium.
* 2001-2004 : TEI P4, introduction du XML.
* 2007-... : [TEI P5](http://www.tei-c.org/Guidelines/P5/), abandon de SGML.

# Les “principes de Poughkeepsie” (1987)
Proposer des *Guidelines* (recommandations) avec pour objectifs :
1. **Provide a standard format for data interchange** in humanities research.
2. **Suggest principles for the encoding of texts** in the same format.
3. Define (a) a **recommended syntax** for the format, (b) a **metalanguage for the description of text-encoding schemes**, (c) describe the new format and representative existing schemes **both in that metalanguage and in prose** ;
4. propose sets of coding conventions suited for **various applications**.
5. include a **minimal set of conventions** for encoding new texts in the format.
6. The guidelines are to be drafted by **committees** on text documentation, text representation, text interpretation and analysis, metalanguage definition and description of existing and proposed schemes, coordinated by a steering committee of representatives of the principal sponsoring organizations.
7. **Compatibility with existing standards will be maintained as far as possible**.
8. A number of large text archives have agreed in principle to support the guidelines in their function as an interchange format. We encourage funding agencies to support development of tools to facilitate this interchange.
9. Conversion of existing machine-readable texts to the new format involves the translation of their conventions into the syntax of the new format. No requirements will be made for the addition of information not already coded in the texts.

# Un *Consortium*
Fondation interdisciplinaire à but non lucratif, financée par ses membres
* [TEI Board of Directors](http://www.tei-c.org/Board/)
* [TEI Technical Council](http://www.tei-c.org/Activities/Council/index.xml)
* [Membres institutionnels et individuels](http://members.tei-c.org/)
* [TEI Workgroups](http://www.tei-c.org/Activities/Workgroups/), par ex. :
  * [TEI Manuscripts Special Interest Group](http://www.tei-c.org/Activities/SIG/Manuscript/)
  * [Correspondence SIG](http://www.tei-c.org/Activities/SIG/Correspondence/)
* [Special Interest Groups](http://www.tei-c.org/Activities/SIG/)
* Une liste de diffusion : [TEI-L mailing list](https://listserv.brown.edu/?A0=TEI-L)
* Une liste francophone :  [TEI-FR](https://groupes.renater.fr/sympa/info/tei-fr) et un wiki
* des members meetings (congrès) annuels, de Pise 2001 à Lyon 2015, la publication d'une revue, la jTEI (Journal of the Text Encoding Initiative, http://jtei.revues.org/)
* Des congrès annuels : [TEI Conference](http://www.tei-c.org/Membership/Meetings/)
* Une revue : [*Journal of the Text Encoding Initiative*](http://jtei.revues.org/)
* Last but not least: les **[Guidelines](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/index.html)** ("recommandations") qui documentent notamment chaque élément.

# Lire et comprendre les *Guidelines*
![Page d’accueil des Guidelines TEI](./img/guidelines_accueil.png)

![Documentation de l’élément msIdentifier](./img/guidelines_msIdentifier.png)


## Les modules : des réservoirs d’éléments
La TEI P5 comporte des centaines d’éléments [(569)](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/REF-ELEMENTS.html), regroupés en [modules](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ST.html#STMA).  
Chaque module est documenté par un chapitre des *Guidelines*.

**4 modules sont obligatoires** (communs à tous les documents TEI) :
* `tei` : [1 The TEI Infrastructure](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ST.html) (définition des classes, macros et types de données)
* `header` : [2 The TEI Header](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/HD.html) (métadonnées communes)
* `core` : [3 Elements Available in All TEI Documents](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/CO.html)
* `textstructure` : [4 Default Text Structure](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/DS.html) (éléments de base pour structurer un texte de type livre)

Les modules sont relatifs à un type d'objet, une approche, une discipline, par ex. :
* `analysis` : [analyse linguistique](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/AI.html)
* `drama` : [textes d’art dramatique](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/DR.html)
* `gaiji` : [caractères non standard et glyphes](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/WD.html)
* `linking` : [liens, segmentation, alignements](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/SA.html)
* `msdescription` : [description des manuscrits](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/MS.html)
* `namesdates` : [noms, dates, lieux](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ND.html)
* `textcrit` : [apparat critique](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/TC.html)
* `transcr` : [transcription des sources primaires](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/PH.html)

## Les classes
cf. [*Guidelines, 1 The TEI Infrastructure*](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ST.html#STEC)

Les classes permettent d’organiser les éléments du modèle.  
Les éléments **héritent** des propriétés de la classe à laquelle ils appartiennent, mais aussi de la classe de cette classe (`superclass`), etc.  
**NB.** Une compréhension de base des classes du schéma TEI est essentielle pour bien lire les *Guidelines* et pour personnaliser un schéma.

Deux types de classes :
* **classes d'attributs** (`att.`) : "A class is known as an *attribute class* if its members share attributes".  
Par ex., la classe [`att.global`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-att.global.html), regroupe les attributs communs à tous les éléments dans le système de codage TEI (`@xml:id`, `@xml:lang`, etc.)


* **classes du modèle** (`model.`) : "[A class is known] as a *model class* if its members appear in the same locations." Ces classes regroupent des éléments qui ont un même emplacement dans la structure hiérarchique d’un document TEI.  
Par ex., [`model.divPart`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-model.divPart.html) regroupe des éléments de niveau paragraphe apparaissant directement dans des divisions (`p`, `lg`, `l`, etc.) ; [`model.phrase`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-model.phrase.html) regroupe des éléments qui apparaissent au niveau des mots isolés ou des groupes de mots (`hi`, `title`, `foreign`, etc.).

Ces *Model Classes* sont autant que possible des groupements sémantiques. Par ex., [`model.nameLike`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-model.nameLike.html) regroupe des éléments qui nomment une personne, un lieu ou une organisation (`name`, `orgName`, `persName`, etc.) ; [`model.biblPart`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-model.biblPart.html) regroupe des éléments qui sont des composantes d’une description bibliographique (`bibl`, `author`, `editor`, etc.).

## Les macros
Les [macros](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ST.html#STmacros) sont comme des raccourcis pour les modèles de contenu les plus fréquents.  
Elles sont utilisées pour :
* Représenter des modèles de contenu fréquemment utilisés (*Standard Content Models*).  
Par ex., [`macro.paraContent`](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-macro.paraContent.html) définit le contenu des paragraphes (`p`) et des éléments similaires.
* Désigner des types d'attributs de données (*Datatype Specifications*).  
Par ex., [`teidata.certainty`](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/ref-teidata.certainty.html) définit la plage des valeurs d'attributs exprimant un degré de certitude : `teidata.certainty = "high" | "medium" | "low" | "unknown"`

Nous passons un peu vite et reviendrons sur ces concepts de l’*Infrastructure TEI* quand nous parlerons de la personnalisation de schémas.


# *Interoperability / Interchange* ?
> P5: Guidelines for Electronic Text Encoding and **Interchange** (cf. http://www.tei-c.org/Vault/P5/2.2.0/doc/tei-p5-doc/en/html/index.html)

TEI (All) n’est pas un schéma à proprement parler.  
Mais plutôt un *framework*, utile à la conception de son propre schéma.

Il est fortement déconseillé d’utiliser un schéma englobant l’intégralité de la TEI : une phase importante d’un projet est la conception d’un modèle adapté aux données et au projet, à l’exploitation des documents.

Documenter pour rendre ces choix lisibles et réexploitables par un groupe plus large ou d’autres chercheurs.

# Exercice. Documentation
* Repérer dans les [*Guidelines*](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/index.html) la documentation sur l’encodage des textes dramatiques (théâtre).
* Identifier (lister) les éléments et attributs TEI utiles pour l’encodage de notre première page du *Misanthrope*.
* Convertir notre fichier [misanthrope.xml](./docs/misanthrope.xml) en TEI ([misanthrope-tei.xml](./docs/misanthrope-tei.xml)) (remplacer nos balises "maison" par les balises TEI et **veiller à la validité** du fichier produit).
* **Bonus 1.** Reprendre notre [première DTD](https://github.com/editions/cours-TEI/blob/master/2-xml-regles.md#exercice-3-correction) pour construire le schéma TEI et valider [misanthrope-tei.xml](./docs/misanthrope-tei.xml).
* **Bonus 2.** Exprimer en TEI (dans le `teiHeader`) quelques métadonnées : 1. titre de l’œuvre, 2. auteur de l’œuvre, 3. date de création de l’œuvre, 4. auteur de l’encodage, 4. licence, 5. identifiant du fichier TEI.
* **Aide.** [Structure minimale d’un document TEI P5 valide](./docs/teiAll-empty.xml) (vous permettra d’insérer conformément votre transcription et de réfléchir à la question des métadonnées).

**[Début du] Corrigé – à compléter avec les élèves** : Documentation in [3.12.1 Core Tags for Verse 3](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/CO.html#CODV), [7 Performance Texts](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/DR.html), [Verse](http://www.tei-c.org/release/doc/tei-p5-doc/en/html/VE.html)
* `<piece>` => [`<TEI>`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-TEI.html) ([4 Default Text Structure](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/DS.html))
* `<acte>` => [`<div type="act" n="1">`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-div.html)
* `<scene>` => [`<div type="scene" n="1">`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-div.html)
* `<titre>` => [`<head>`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-head.html)
* `<casting>` => [`<stage>`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-stage.html)
* `<tourDeParole>` => [`sp[@who]/speaker`]()
* `<didascalie>` => [`<stage>`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-stage.html)
* `<vers>` => [`<l>`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-l.html), [`<lg>`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-lg.html) ?
* `@aligner` => [`@rend`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-att.global.rendition.html), [`@part`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-att.fragmentable.html)
* `@xml:lang` => [`@xml:lang`](http://www.tei-c.org/release/doc/tei-p5-doc/fr/html/ref-att.global.html)

```xml
<TEI xmlns="http://www.tei-c.org/ns/1.0" xml:lang="fr">
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
  <text>
    <body>
      <head rend="uc">Le misanthrophe</head>
      <div xml:id="I" type="act">
        <head>Acte Premier</head>
        <div type="scene" xml:id="I01">
          <head>Scène Première</head>
          <stage>Philinte, Alceste</stage>
          <sp who="philinte" xml:id="I01-1">
            <speaker>Philinte</speaker>
            <l n="1" xml:id="l1" part="I">Qu’est-ce donc ? qu’avez-vous ?</l>
          </sp>
          <sp who="alceste" xml:id="I01-2">
            <speaker>Alceste</speaker>
            <l part="F">Laissez-moi, je vous prie.</l>
          </sp>
          <sp who="philinte" xml:id="I01-3">
            <speaker>Philinte</speaker>
            <l n="2" xml:id="l2">Mais, encor, dites-moi, quelle bizarrerie...</l>
          </sp>
          <sp who="alceste" xml:id="I01-4">
            <speaker>Alceste</speaker>
            <l n="3" xml:id="l3">Laissez-moi là, vous dis-je, et courez vous cacher.</l>
          </sp>
          <sp who="philinte" xml:id="I01-5">
            <speaker>Philinte</speaker>
            <l n="4" xml:id="l4">Mais on entend les Gens, au moins, sans se fâcher.</l>
          </sp>
          <sp who="alceste" xml:id="I01-6">
            <speaker>Alceste</speaker>
            <l n="5" xml:id="l5">Moi, je veux me fâcher, et ne veux point entendre.</l>
          </sp>
          <sp who="philinte" xml:id="I01-7">
            <speaker>Philinte</speaker>
            <l n="6" xml:id="l6">Dans vos brusques chagrins, je ne puis vous comprendre ;</l>
            <l n="7" xml:id="l7">Et quoique amis, enfin, je suis tout des premiers...</l>
          </sp>
          <sp who="alceste" xml:id="I01-8">
            <speaker>Alceste</speaker>
            <l n="8" xml:id="l8">Moi, votre ami ? rayez cela de vos papiers.</l>
            <l n="9" xml:id="l9">J’ai fait jusques ici, profession de l’être ;</l>
            <l n="10" xml:id="l10">Mais après ce qu’en vous, je viens de voir paraître,</l>
          </sp>
        </div>
      </div>
    </body>
  </text>
</TEI>
```
# TEI, un format pivot pour les éditions académiques ?
TODO
––IMAGE––  
––lister les initiatives––

# Bibliographie
TODO
