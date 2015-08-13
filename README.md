# scrape

## a command-line web scraping and crawling tool
scrape is a command-line tool used to extract webpage content in the form of text, pdf, or simply html. A crawling mechanism allows scrape to follow subsequent webpages either freely or according to a set of keywords, making scraping entire websites a quick and easy task. scrape can extract text content for any tag attributes, such as href for links or text for plain text. Text can be filtered in a grep-like manner, saving you another extra step!

## Installation
* `pip install scrape`
* [Installing wkhtmltopdf](https://github.com/pdfkit/pdfkit/wiki/Installing-WKHTMLTOPDF)

## Usage
    usage: scrape.py [-h] [-a [ATTRIBUTES [ATTRIBUTES ...]]]
                     [-c [CRAWL [CRAWL ...]]] [-ca] [-f [FILTER [FILTER ...]]]
                     [-ht] [-l LIMIT] [-n] [-p] [-q] [-t] [-v]
                     [urls [urls ...]]
    
    a command-line web scraping and crawling tool
    
    positional arguments:
      urls                  url(s) to scrape
    
    optional arguments:
      -h, --help            show this help message and exit
      -a [ATTRIBUTES [ATTRIBUTES ...]], --attributes [ATTRIBUTES [ATTRIBUTES ...]]
                            tag attribute(s) for extracting lines of text, default
                            is text
      -c [CRAWL [CRAWL ...]], --crawl [CRAWL [CRAWL ...]]
                            regexp(s) to match links to crawl
      -ca, --crawl-all      crawl all links
      -f [FILTER [FILTER ...]], --filter [FILTER [FILTER ...]]
                            regexp(s) to filter lines of text
      -ht, --html           save output as html
      -l LIMIT, --limit LIMIT
                            set page crawling limit
      -n, --nonstrict       set crawler to visit other websites
      -p, --pdf             save output as pdf
      -q, --quiet           suppress output
      -t, --text            save output as text, default
      -v, --version         display current version

## Author
* Hunter Hammond (huntrar@gmail.com)

## Notes
* Pages are converted to text by default, you can specify --html or --pdf to save to a different format.

* If saving to text, lines may be filtered for keywords by passing one or more regexps to --filter.

* Also if saving to text, you may specify specific tag attributes to extract from the page using --attributes. The default choice is to extract only text attributes, but you can specify one or many different attributes (such as href, src, title, or any attribute available..).

* Pages are saved temporarily as PART%d.html files during processing. These files are removed automatically if saving to text or pdf.

* Entire websites can be downloaded by using the --crawl-all flag or by passing one or more regexps to --crawl, which filters through a list of URL's.

* If you want the crawler to follow links outside of the given URL's domain, use --nonstrict.

* Crawling can be stopped by Ctrl-C or by setting the number of pages to be crawled using --limit.

