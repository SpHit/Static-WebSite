# Paper-Now

[paper-now](https://github.com/PeerJ/paper-now) makes it easy to create, edit and display an online journal/scientific article, entirely in GitHub. 

> ... Paper Now is an experiment to see where the future may go with scholarly communication. Initially, it may be that co-authors collaborate either privately or publicly on GitHub and then proceed to submitting to PeerJ or other journals for formal peer-review or preprinting. Or perhaps this is where the traditional medium of publication begins to diverge. There is no end goal other than to see what the academic community wants, which is why this is completely open to fork, extend, and build upon.

Hugo [Paper-Now](https://github.com/eueung/hugo-paper-now) is a port of `PeerJ/paper-now` for use within Hugo. 

![Screenshot](https://raw.githubusercontent.com/eueung/hugo-paper-now/master/images/screenshot.png)

## Demo

- [Sample Article](//eueung.github.io/hugo-paper-now/)

## Installation

Inside the folder of your Hugo site run:

    $ cd themes
    $ git clone https://github.com/eueung/hugo-paper-now.git paper-now

For more information read the official [setup guide](//gohugo.io/overview/installing/) of Hugo.

## Sample Configuration

The following `config.toml` is used for the demo site mentioned above.

```toml
baseurl         = "https://eueung.github.io/hugo-paper-now/"
theme           = "paper-now"
languageCode    = "en-us"
title           = "Site Title | Hugo Paper-Now"
canonifyurls    = true

[params]
  googleAnalytics   = ""
  pageNotFoundTitle = "404 - Page not found"
  
  articleTitle= "Human, AI &amp; Exoplanets"
  publishDate = "2016-12-18"
  doi         = ""
  github      = ""

[[params.authors]]
    id    = "alice-exemplar"
    name  = "Alice Exemplar"
    email = "alice.exemplar@example.com"
    url   = "http://example.com/authors/1"
    orcid = "0000-0002-9298-3168"

[[params.authors]]
    id    = "bob-exemplar"
    name  = "Bob Exemplar"
    email = ""
    url   = ""
    orcid = "0000-0002-9341-7985"

[[params.authors]]
    id    = "em-exemplar"
    name  = "EM Exemplar"
    url   = "https://eueung.github.io"

[[params.affiliations]]
    name       = "Stanford University"
    department = "Department of Mathematics"
    location   = "Stanford, California, USA"
    url        = "http://mathematics.stanford.edu/"
    members    = ["alice-exemplar","bob-exemplar"]

[[params.affiliations]]
    name       = "Harvard University"
    department = "Department of Molecular and Cellular Biology"
    location   = "Cambridge, MA, USA"
    url        = ""
    members    = ["alice-exemplar"]

[[params.affiliations]]
    name       = "Institut Teknologi Bandung"
    department = "School of Electrical Engineering and Informatics"
    location   = "Bandung, Indonesia"
    url        = "https://stei.itb.ac.id/id/"
    members    = ["em-exemplar"]

[[params.funders]]
    name   = "Medical Research Council"
    url    = ""
    sameAs = "http://doi.org/10.13039/501100000265"
    [[params.funders.awards]]
        name = "MRC123"
        recipients = ["alice-exemplar", "bob-exemplar"]
    [[params.funders.awards]]
        name = "MRC456"
        recipients = ["alice-exemplar", "bob-exemplar"]

[[params.funders]]
    name   = "National Institutes of Health"
    url    = "http://www.nih.gov/"
    sameAs = "http://doi.org/10.13039/100000002"
    [[params.funders.awards]]
        name = "NIH123"
        recipients = ["alice-exemplar"]

[[params.contributions]]
    name = "Methodology"
    url  = "http://dictionary.casrai.org/Contributor_Roles/Methodology"
    contributors = [ "alice-exemplar", "bob-exemplar" ]

[[params.contributions]]
    name = "Investigation"
    url  = "http://dictionary.casrai.org/Contributor_Roles/Investigation"
    contributors = [ "alice-exemplar", "bob-exemplar" ]

[[params.contributions]]
    name = "Software"
    url  = "http://dictionary.casrai.org/Contributor_Roles/Software"
    contributors = [ "bob-exemplar" ]

[[params.contributions]]
    name = "Writing - original draft"
    url  = "http://dictionary.casrai.org/Contributor_Roles/Writing_%E2%80%93_original_draft"
    contributors = [ "alice-exemplar" ]

[[params.contributions]]
    name = "Writing - review & editing"
    url  = "http://dictionary.casrai.org/Contributor_Roles/Writing_%E2%80%93_review_%26_editing"
    contributors = [ "bob-exemplar" ]

```

Sample content structure is given in the `exampleSite` folder. Have fun!

## License

This theme is released under the MIT license. For more information read the [License](//github.com/eueung/hugo-paper-now/blob/master/LICENSE.md).


