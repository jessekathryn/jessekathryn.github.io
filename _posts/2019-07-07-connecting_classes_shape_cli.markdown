---
layout: post
title:      "Shape CLI Classes/Module"
date:       2019-07-07 19:56:46 -0400
permalink:  connecting_classes_shape_cli
---


After separating classes into three different working parts:

 - Scraper
 - CLI
 - Article

All of the groundwork is laid down.  The next step is making sure each class functions individually, each working it's own individual part, connecting to run the Shape_Cli project.

The Shape CLI scraper will function like below - and the key is to find the best way to connect each method and to keep it DRY or to a single purpose.  At first, my Article class was doing too much work.  Now, it will work through the scraper class and communicate through its shared connection, the CLI.

```
 def self.scrape_lifestyle_page()
    page = Nokogiri::HTML(open("https://www.shape.com/lifestyle"))
    articles = []
    page.css("div.taxonomy-seo-links").each do |a|
    article_hash = {}
      article_hash[:name] = a.css("div h5 a").text  
      article_hash[:url] = a.css("a").attribute("href").value
      articles << article_hash
      articles
    end 
    articles
  end
 
  def self.scrape_article_page(url)
    page = Nokogiri::HTML(open(url))
    article_page = {}
    article_page[:name] = page.css("h1.headline").text
    article_page[:url] = page.css("div.taxonomy-seo-links a").attr("href")
    article_page[:summary] = page.css("p.dek").text.strip
    article_page[:author] = page.css("span.bold.author-name").text.strip
    article_page[:date] = page.css("div.timestamp").text.strip
    aarticle_page[:text] = page.css("p").text.strip
    article_page
  end
end 
```


Next up: hashes and calling methods in CLI, connecting it all together


TO DO:
1. display article text in full, if interested
2. clean up and make sure all methods are working properly 
3. work on exit      

 
