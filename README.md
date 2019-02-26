# LCS: Bonnie Dorr's LCS Database

The LCS data is stored in file verbs-English.lcs.

----------------------------- REFERENCES --------------------------

Dorr, Bonnie J., "Large-Scale Dictionary Construction for Foreign
Language Tutoring and Interlingual Machine Translation,"
Machine Translation, 12:4, pp. 271--322, 1997.
http://www.umiacs.umd.edu/users/bonnie/Publications/icall-97.pdf

Dorr, Bonnie J. and Mari Broman Olsen, "Multilingual Generation: The
Role of Telicity in Lexical Choice and Syntactic Realization", Machine
Translation, 11:1-3, pages 37-74, 1996. 
URL = http://www.umiacs.umd.edu/users/bonnie/Publications/lex-choice-96.pdf

Dorr, Bonnie J. and Douglas Jones, "Acquisition of Semantic Lexicons:
Using Word Sense Disambiguation to Improve Precision", in Breadth and
Depth of Semantic Lexicons, Evelyne Viegas (ed.), Kluwer Academic
Publishers, pages 79-98, Norwell, MA, 1999.
URL = http://www.umiacs.umd.edu/users/bonnie/Publications/kluwer-00.pdf

Fellbaum, Christiane, WordNet: An Electronic Lexical Database,
MIT Press, 1998.
URL = http://mitpress.mit.edu/books/wordnet

Green, Rebecca, Lisa Pearl, Bonnie J. Dorr, and Philip Resnik,
"Lexical Resource Integration across the Syntax-Semantics Interface",
in Proceedings of the NAACL Workshop on WordNet and Other Lexical
Resources: Applications, Customizations, Carnegie Mellon University,
Pittsburg, PA, pages 71-76, 2001a.
URL = http://www.umiacs.umd.edu/users/bonnie/Publications/naacl-01.pdf

Green, Rebecca, Lisa Pearl, Bonnie J. Dorr, and Philip Resnik,
"Mapping WordNet Senses to a Lexical Database of Verbs", in
Proceedings of the 39th Annual Meeting of the Association for
Computational Linguistics, Toulouse, France, pages 244-251, 2001b.
URL = http://www.umiacs.umd.edu/users/bonnie/Publications/acl-01.pdf

Levin, Beth, "English Verb Classes and Alternations: A Preliminary 
Investigation", University of Chicago Press, Chicago, IL, 1993.

Olsen, Mari Broman, Bonnie J. Dorr, and Scott C. Thomas, "Toward
Compact Monotonically Compositional Interlingua Using Lexical Aspect,"
in Proceedings of the Workshop on Interlinguas in MT, MT Summit, New
Mexico State University Technical Report MCCS-97-314, San Diego, CA,
pages 33-44, 1997.
URL = http://www.umiacs.umd.edu/users/bonnie/Publications/il-97.pdf

Palmer, Martha, Joseph Rosenzweig and Scott Cotton,
"Automatic Predicate Argument Analysis of the Penn TreeBank," in
Proceedings of HLT 2001, First International Conference on Human 
Language Technology Research, J. Allan, ed., Morgan Kaufmann, 
San Francisco, 2001. 
http://hlt2001.org/papers/hlt2001-10.pdf

************************************************************************

NOTES ON THE ENTRIES

This is a lisp-readable file of property lists, each with
slots such as:

 :DEF_WORD      The surface word in the language of interest
 :ROMAN         A romanized form of that word
 :GLOSS         An English gloss for the word
 :GLOSS_HEAD    The head of the english gloss
 :CLASS         The Levin class from Levin (1993)
 :WN_SENSE      A hand-tagged WordNet sense by Dorr and Jones (1996)
 :PROPBANK      1 or more comparable PropBank-style role-list strings
 :THETA_ROLES   A thematic grid produced by Dorr (1994-1996) 
                with augmentations by Dorr, Olsen, Thomas (1997-1999)
 :LCS           An LCS representation automatically produced by
                routines written by Dorr (1997) with 
                augmentations by Thomas
 :VAR_SPEC      Featural information about variable positions in the LCS 
                by Dorr (1997)
 :COLLOCATIONS  Collocations 

 *Any* of the slots may be missing, though meaningful entries
 will have :DEF_WORD, :THETA_ROLES and :LCS slots.

 Slots such as :WN_SENSE, :VAR_SPEC and :COLLOCATIONS, if missing,
 are equivalent to NIL. 

 If :ROMAN or :GLOSS are missing, they are equivalent to :DEF_WORD.
 If :GLOSS_HEAD is missing, it is equivalent to :GLOSS.


The `Grid line' is a line of #-separated fields, used as input to
the LCS-generation process. It is included in some LCS files mainly
for debugging purposes. Its format is:

 cl-no#g-no#grid#wd#rom#gloss#cnsts#wn-senses#field-etc#incorps#comments

where

 cl-no     = verb-class number
 g-no      = grid number
 wd        = the word, in some language-specific encoding
 rom       = romanization of the word
 gloss     = English gloss of the word
 cnsts     = `constants' utilized in creating the LCS
 wn-senses = word-net offsets
 field-etc = other info for creating the LCS, such as semantic field
 incorps   = other material to be incorporated into the LCS
 comments  = arbitrary comments on this entry, as desired

*Any* of the fields may be blank. I.e., 

 ##########

is a valid grid line, though in practice, at least the `word' and
field-etc' fields must be present for a usable LCS entry to be
created. (Older subroutines in the LCS-generation code require
the `class-number' and `word' fields.)

In some LCS files (i.e., lisp readable files), these grid lines 
are prepended with the string `;; Grid: '. A lisp-readable form 
with the corresponding LCS should follow, except in cases where
the LCS-generation process failed on the given grid line,
for whatever reason.


Release Data:
 LCS_0_17 (1.1)
 English_Lexicon_0_15 (1.1)
 AD-verbs-English.edited-grid,v 1.2 2001/10/24 19:28:40 (UTC)
 BJDMAP-verbs-English.edited-grid,v 1.2 2001/10/24 19:28:40 (UTC)
 EM-verbs-English.edited-grid,v 1.2 2001/10/24 19:28:40 (UTC)
 NR-verbs-English.edited-grid,v 1.2 2001/10/24 19:28:41 (UTC)
 SZ-verbs-English.edited-grid,v 1.2 2001/10/24 19:28:41 (UTC)

