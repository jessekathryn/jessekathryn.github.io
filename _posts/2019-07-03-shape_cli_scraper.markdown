---
layout: post
title:      "Shape CLI Scraper "
date:       2019-07-03 01:33:11 -0400
permalink:  shape_cli_scraper
---


Scraping seems scary and intimidating, but in reality, it really isn't so bad.

A lot of this depends on the tags you are wanting to scrape.

Right now I have everything in my Article class, which is incomplete.  The methods in Article that call on the scraper can stay in this class.

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

The next step is to put the scraper methods inside a Scraper class and then call on them in the Article class.

class ShapeCli::Scraper
  
attr_accessor :article, :name, :url, :summary, :date, :author, :article_text
  
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
    article.summary = page.css("p.dek").text.strip
    article.author = page.css("span.bold.author-name").text.strip
    article.date = page.css("div.timestamp").text.strip
    article.article_text = page.css("p").text.strip
    article
  end
end



