KRKbib bibliography 
v. 0.01b
readme by Jacek Grela 10.01.2016

This readme file serves mainly as the reference on the desirable format of entries in the krkbib.bib file. Authors are encouraged to follow these rules to attain a reasonable overall database homogenity.

The title of all types of entries is of the form:

	AuthorsYear:DESCRIPTION

Below we describe each part separately:

* "Authors" field
We use abbreviated last names of all authors (if few) as appears in the paper or use "etal" in case of large collaborations. The length of abbreviations are as follows:

1-2 authors - three letters
3 authors - two letters
more than 3 authors - one letter

* "Year" field
It is the publication year (in case of articles and books) or, in case of preprints, the publication on the arxiv.

* "DESCRIPTION" field
It is given in CAPITAL letters and should succinctly describe the paper in one or two words.

We provide simple examples:

1. 
	ChaMeh1998:EIGENVECTOR

for a paper on eigenvectors of two authors Chalker and Mehlig published in 1998.

2. 
	BGNW2015:HERMDETS

this paper on hermitian determinants was published by 4 authors: Blaizot, Grela, Nowak and Warchol. Date of publication is 2015.

There are two main types of entries used:

1. @article type
2. @unpublished type
3. @book


Fields for @article:
title
	Title as appeared in the journal/arxiv
author
	authors in the format:
	Lastname, F. and Lastname2, G. and Lastname3, H.
journal
	journal title in the abbreviated form i.e.
	Phys. Rev. E
	J. Math. Phys.
volume
	journal volume
issue (optional)
	if applicable
pages
	only first page of the article
year
	publication year
url
	url to the article (preferably on aps pages)
doi
	DOI number

template:

@article{AlBo2012:HERMEV,
  title = {Eigenvector dynamics: General theory and some applications},
  author = {Allez, R. and Bouchaud, J.-P.},
  journal = {Phys. Rev. E},
  volume = {86},
  issue = {4},
  pages = {046202},
  year = {2012},
  doi = {10.1103/PhysRevE.86.046202},
  url = {http://link.aps.org/doi/10.1103/PhysRevE.86.046202}
}



Fields for @unpublished:

title
	Title as appeared in the journal/arxiv
author
	authors in the format:
	Lastname, F. and Lastname2, G. and Lastname3, H.
journal
	leave blank
volume
	leave blank
issue (optional)
	leave blank
pages
	leave blank
year
	preprint publication year
url
	arXiv link
doi
	leave blank
note
	note on the unpublished nature of the paper i.e.
	unpublished, arXiv:xxx.xxxx

template:

@unpublished{AlBuBo2014:HERMEV,
   title = {The eigenvectors of Gaussian matrices with an external source},
   author = {Allez, R. and Bun, J. and Bouchaud, J.-P.},
   journal = {},
   volume = {},
   issue = {},
   pages = {},
   year = {},
   doi = {},
   url = {http://arxiv.org/abs/1412.7108},
   note = "unpublished, arXiv:1412.7108",
}


Fields for @book:

title
	Title of the book

author
	authors of the book in the format:
	Lastname, N.
publisher
	book's publisher
year
	year published
edition
	edition in a numeric form


@book{Moi2011:NHQMBOOK,
   author = {Moiseyev, N.}, 
   title = {Non-Hermitian Quantum Mechanics},
   publisher = {Cambridge University Press},
   year = {2011},
   edition = {1},
}

