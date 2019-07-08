---
layout: post
title:      "Refactoring CLI"
date:       2019-07-08 00:08:27 +0000
permalink:  refactoring_cli
---


After refactoring my Article class into two classes (below is the new code for this class for specific examples), Article.rb and Scraper.rb, it is time to refactor my CLI.

Don't forget, this was initially written to create a backbone and use fake data, or it's groundwork was laid down as a draft so to speak.

Now, the CLI can change and instead of calling on the Article class or the items inside it, we can ask call on our Scraper class to scrape the data.  Originally, the methods for each scraping and data display methods were in the same file.  Now we can separate the two and have each use the common information of the data (think back Music CLI and the data which is shared between two classes (Artist::Songs, Genre::Songs) in this case, is the song.  

See below our new refactored and more efficient Article class below:

```
class ShapeCli::Article
  
attr_accessor :article, :name, :url, :summary, :date, :author, :article_text

  @@all = []

  def initialize(shape_hash)
    shape_hash.each {|key, value| self.send(("#{key}="), value)}
        @@all << self
  end

  def self.create_from_collection(articles_array)
    articles_array.each do |article|
      Article.new(article)
    end
  end

  def add_student_attributes(article_page)
    article_page.each {|key, value| self.send(("#{key}="), value)}
  end

  def self.all
    @@all
  end 
  
```
