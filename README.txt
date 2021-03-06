
KRKbib bibliography README file
v. 0.02b 
Jacek Grela 19.01.2016

This readme file contains most of the information needed to use and maintain the krkbib bibliography file in a consistent manner. 

      I. Getting started
        a) compile the template
        b) basic bib(la)tex commands
      II. Bibtex files
        a) structure of the files
        b) modify the bibtex file (with JabRef)
      III. Tips & Troubleshooting
      IV. Files description



I. Getting started


	a) compile the template

      bibtemp.tex is the template file useful in setting up your favourite latex editor. A standard procedure to run latex+biblatex is the same as bibtex and can contains three compilation steps:


    latex foobar.tex
    bibtex foobar.aux
    latex foobar.tex


      which first produces a file foobar.aux and only afterwards the foobar.dvi - a rendered document file. We encourage to set up your favourite latex editor so that the bibtemp.tex gets compiled without errors. 



	b) basic biblatex commands

      * First, biblatex needs a package of the same name:


    \usepackage[backend=bibtex,style=phys]{biblatex}


      * Second, a bibliography file is needed:


    \addbibresource{krkbib2015.bib}


      * Lastly, to print the bibliography we use:


    \printbibliography[title={Bibliography}]


      which will include all citations in the text. For advanced options check ftp://sunsite.icm.edu.pl/pub/CTAN/macros/latex/contrib/biblatex/doc/biblatex.pdf

    

II. Bibtex files
	

	a) structure of the files

      Bibtex files have the following naming structure:


    krkbibYEAR.bib


      where YEAR is the year of krkbib existence. Authors are encouraged to add references to the current-year file. 
      
      Bibtex file contains of records of mainly three types: @Article (articles), @Book (whole books) and @Unpublished (preprints). The general naming scheme of references is the following


	  AuthorsYear:DESCRIPTION


      * "Authors" part
        
        We use abbreviated last names of all authors (if few) as appears in the paper or use "etal" in case of large collaborations. The length of abbreviations are as follows:

        1 authors - three letters of the last name
        2-4 authors - one letter for each author
        more than 4 authors - one letter of first three authors and "+" sign in the end

        It is advisable to drop this naming scheme if there is any confusion arising f.e. if two different groups has the same initials.

      * "Year" field
        
        It is the publication year (in case of articles and books) or, in case of preprints, the publication on the arxiv.

      * "DESCRIPTION" field

        It is given in CAPITAL letters and should succinctly describe the paper in one or two words.
        We describe below properties for each type of entry:


      We provide examples:

    CM1998:EIGENVECTOR

      for a paper on eigenvectors of two authors Chalker and Mehlig published in 1998.

    BGN+2015:HERMDETS

      this paper on hermitian determinants was published by 4 authors: Blaizot, Grela, Nowak and Warchol. Date of publication is 2015.


      Below we describe the most popular entries and the COMPULSORY properties for each type of entry. Some optional items are also listed however with the OPTIONAL caption.
      It is possible to add more information however one should be especially careful around certain fields. The policy is that more information is almost always better.

	      1. @Article:

          Title - title as appeared in the journal/arxiv
          Author - authors in the  preferable format: "Lastname, Firstname and Lastname2, Firstname2. and Lastname3, Firstname3", irst name can be abbreviated if unknown
          Doi (OPTIONAL) - digital object identification number (check the validity at https://www.doi.org/), often non-existent for older articles
          Journal - journal title in the abbreviated form i.e. Phys. Rev. E or J. Math. Phys. (check jourabbr for popular journals)
          Keywords - keywords identifying the content (check keywords file for a list)
          Number - journal number or issue (WARNING: a similar "Issue" property should NOT be used)
          Pages - first page of the article
          Url (OPTIONAL) - an external url to the page with the article. Most often the sources are available from aps.org, sciencedirect.com, iop.org and springer.com 
          Volume - volume of the journal 
          Year - publication year
          Owner - identifier of the reference creator
          Timestamp - modification date

        Example:

          @Article{Sni2002:BROWNMEASURE,
            Title                    = {Random Regularization of Brown Spectral Measure},
            Author                   = {\'Sniady, Piotr},
            Doi                      = {10.1006/jfan.2001.3935},
            Journal                  = {J. Funct. Anal.},
            Keywords                 = {brown,freeprob},
            Number                   = {2},
            Pages                    = {291},
            Url                      = {http://www.sciencedirect.com/science/article/pii/S0022123601939357},
            Volume                   = {193},
            Year                     = {2002},
            Owner                    = {grela},
            Timestamp                = {2016.01.13}
          }



        2. @Book

          Title - book title
          Author - authors of the book
          Edition - arabic number of edition
          Publisher - publisher of the book
          Year - editions' publication date
          Owner - see @Article
          Timestamp - see @Article

        Example:

          @Book{AnAsRo1999:SPECIALFUNC,
            Title                    = {Special Functions},
            Author                   = {Andrews, G. E. and Askey, G. and Roy, R.},
            Edition                  = {1},
            Publisher                = {Cambridge University Press},
            Year                     = {1999},
            Owner                    = {grela},
            Timestamp                = {2016.01.10}
          }



        3. @Unpublished

          Title - preprint's title
          Arxivid - id number on the arxiv.org
          Author - authors
          Keywords - keywords identifying the content (check keywords file for a list)
          Note - note of the form: "unpublished, arXiv:NUMBER" where NUMBER should be the same as in the entry Arxivid.
          Url - URL of the preprint as on arxiv
          Year - publication date
          Owner - as in @Article
          Timestamp - as in @Article

        Example:

          @Unpublished{AlBuBo2014:HERMEV,
            Title                    = {The eigenvectors of Gaussian matrices with an external source},
            Arxivid                  = {1412.7108},
            Author                   = {Allez, Romain and Bun, Joël and Bouchaud, Jean-Paul},
            Keywords                 = {rmt,eigenvector,externalsource},
            Note                     = {unpublished, arXiv:1412.7108},
            Url                      = {http://arxiv.org/abs/1412.7108},
            Year                     = {2014},
            Owner                    = {grela},
            Timestamp                = {2016.01.10}
          }



      One may also need (less-popular) entries like:

        4. @InProceedings (to refer to articles appearing in conference proceedings)

          Title - self-explanatory
          Author - self-explanatory
          Booktitle - proceedings title (full, as it is a book)
          Keywords - keywords identifying the content (check keywords file for a list)
          Year - publication year
          Editor (OPTIONAL) - editors of the proceedings
          Pages - first page of the article
          Publisher - publisher
          Owner - as in @Article
          Timestamp - as in @Article

        Example:

          @Inproceedings{Spo1998:DYSON,
            Title                    = {Dyson's model of interacting Brownian motions at arbitrary coupling strength},
            Author                   = {Spohn, Herbert},
            Booktitle                = {Markov Proc. Rel. Fields},
            Keywords                 = {brown},
            Year                     = {1998},
            Pages                    = {649},

            Owner                    = {grela},
            Timestamp                = {2016.01.13}
          }



        5. @InBook (to cite chapters/parts of a book)

          Title - title of the chapter
          Author - author of the chapter
          Chapter (OPTIONAL) - which chapter
          Pages - which page
          Publisher - who published
          Year - publication year
          Volume (OPTIONAL) - which volume, if applicable
          Booktitle - title of the book
          Owner - as in @Article
          Timestamp - as in @Article

        Example:

          @InBook{For1998:LOGGAS,
            Title                    = {Random matrices, log-gases and the Calogero-Sutherland model},
            Author                   = {Forrester, Peter J.},
            Pages                    = {97},
            Publisher                = {The Mathematical Society of Japan},
            Year                     = {1998},
            Volume                   = {1},
            Booktitle                = {Quantum Many-Body Problems and Representation Theory},
            Doi                      = {10.2969/msjmemoirs/00101C020},
            Owner                    = {grela},
            Timestamp                = {2016.01.14},
            Url                      = {http://dx.doi.org/10.2969/msjmemoirs/00101C020}
          }



	b) modify the bibtex file (using JabRef)

    Although manual addition of records is possible, authors are encouraged to add to the existing bibliography by the use of an external referencing tool i.e. JabRef ( http://www.jabref.org/ ). 
    It is a cross-platform, Java-based tool whose sole purpose is to ease the management of bibliographies. To run the whole process one needs export the preferences contained in the jabrefset.xml file. 

    We shall briefly describe useful JabRef features:

    * able to import databases (in particular from webpages)

      References are most easily extracted from pages like aps.org, sciencedirect.com, iop.org and springer.com. We can simply copy&paste them into JabRef and modify accordingly.

    * journal abbreviation

      Toggle abbreviation button shortens the names of journals appropriately. It uses and needs the jourabbr file.

    * automatic naming (BibTex key generation)

      The naming described in Sec. IIa is implemented automatically under Tools -> Autogenerate BibTex keys, the description can be changed manually if need be.

    * groups

      Groups or categories are implemented in JabRef and written inside the bibtex file as @comment entries. A very useful feature to create sets of papers cited in your own research.



III. Tips and troubleshooting:

  1. Be sure that new entries does not contain UTF-8 coded greek letters. Instead use math-environment i.e. {$\alpha$} instead of α. 
  Although no problems should occur when compiling, UTF-8 greek letters won't be properly interpreted by latex.

  2. Math environment inside records need parentheses i.e. {$\alpha$}. Absence of these parentheses will produce compiling errors:

	  ! Extra }, or forgotten $.
	  <recently read> }

  3. Make sure only standard hyphen is used i.e. 

    U+002D -

  non standard hyphens include:

    U+2010 ‐
    U+2011 ‑
    U+2012 ‒
    U+2013 –
    U+2014 —
    U+2015 ―

  among others. These will almost surely be wrongly interpreted by latex as can be checked by compiling the bib-all.tex file. 

  4. Altogether avoid the abstract field which is almost always added when entries are imported from various websites. 
  This field remains the main source of problems with coding discussed before. 


IV. File description

  Files contained in the krkbib directory are the following:

    bib-all.tex - a tex file with all (uses biblatex)
    temp-biblatex.tex - template file with the bibliography set up (uses biblatex)
    temp-revtex.tex - template file with the bibliography set up, compatible with revtex (uses bibtex)
    jabrefset.xml - JabRef standard settings (used by JabRef)
    jourabbr - journal abbreviation (used by JabRef)
    keywords - list of keywords used to group the entries
    krkbib2015.bib - main bibliography file, this file contains all information needed for external projects
    README.txt - this readme file
