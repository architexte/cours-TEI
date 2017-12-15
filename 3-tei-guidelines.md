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
* Repérer la documentation sur l’encodage des textes dramatiques (théâtre).
* Identifier (lister) les éléments et attributs utiles pour l’encodage de notre première page du *Misanthrope*.

# TEI, un format pivot pour les éditions académiques ?
TODO
––IMAGE––  
––lister les initiatives––

# Bibliographie
TODO
