---
layout: post
title:      "Shape CLI Scraper "
date:       2019-07-03 05:33:10 +0000
permalink:  shape_cli_scraper
---


Scraping seems scary and intimidating, but in reality, it really isn't so bad.

A lot of this depends on the tags you are wanting to scrape.

```
class ShapeCli::Article
  
attr_accessor :article, :name, :url, :summary, :date, :author, :article_text

  def self.popular
    self.scrape_article
  end

  def self.scrape_article
    article = []
    article << self.scrape_lifestyle
    article << self.scrape_article_attr
    article
  end  
  
  def self.scrape_lifestyle
    site = "https://www.shape.com/lifestyle"
    page = Nokogiri::HTML(open(site)) 
    article = self.new 
    article.name = page.css("div h5 a").text
    article
    end
 
  def self.scrape_article_attr
    site = "https://www.shape.com/lifestyle/mind-and-body/5-ways-change-your-life-good"
    page = Nokogiri::HTML(open(site))
    article = self.new
    article.name = page.css("h1.headline").text
    article.url = page.css("div.taxonomy-seo-links a").attr("href")
    article.summary = page.css("p.dek").text
    article.author = page.css("span.bold.author-name").text
    article.date = page.css("div.timestamp").text
    article.article_text = page.css("p").text
    article
  end
end
```

As this is working for now there are issues with 

1. iteration through the container holding each popular title
2. the url tag

TO DO:
1. display article text in full, if interested
2. clean up and make sure all methods are working properly 
3. work on exit
