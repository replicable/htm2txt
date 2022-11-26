# htm2text

<img src="./img/htm2txt.png" height="200" align="right"/>

R package converting a html document to plain texts by stripping off all html tags.

## Install htm2txt

    install.packages('htm2txt')

## Get plain text of a webpage

    site = "https://www.wikipedia.org/"

    htm2txt::browse(URL = site)

## Extract a website text

    globe_world_news = "https://www.theglobeandmail.com/world/"
    news = htm2txt::gettxt(URL = globe_world_news, encoding = "UTF-8")

    # save news object into a text file where it is formatted
    readr::write_lines(news, file="scraped_news.txt")

## Convert html tags into text

A character vector is created from this function. A vector of html tags can be passed into the function.

    h = c("<p> this is a paragraph</p><div> div tag here</div>")
    t = htm2txt::htm2txt(h)
    t

    [1] "this is a paragraph\n\ndiv tag here"
