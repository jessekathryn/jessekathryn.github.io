---
layout: post
title:      "Refactoring CLI/Send"
date:       2019-07-07 20:08:28 -0400
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

The send method is described in our curriculum as a hack to make our initialize method more flexible.  The best way to describe this method is to pull the key value pairs together without hardcoding them in our initialize.

>  We define our initialize method to take in some unspecified attributes object. Then, we iterate over each key/value pair in the attributes hash. The name of the key becomes the name of a setter method and the value associated with the key is the name of the value you want to pass to that method. The ruby .send method then calls the method name that is the key’s name, with an argument of the value. In other words:
>  
> self.send(key=, value)
> Is the same as:
>  
> instance_of_user.key = value
> 

This helps us add and use keys when we want to call them and not every time we run our program.  The hash is sent into the initialize and in this case, we are storing our hash items into our all array:

```
@@all = []

  def initialize(shape_hash)
    shape_hash.each {|key, value| self.send(("#{key}="), value)}
        @@all << self
  end
```

The second level was harder to put together.  As we can still send the key/value pair through the send method and the attributes hash, where article page is our url from the key/value pair the user has selected:

```
  def add_article_attributes(article_page)
    article_page.each {|key, value| self.send(("#{key}="), value)}
  end
```

We need to make sure we are calling this specific url/passing this through as the argument in our CLI method of display_details:

```
def display_details  
    ShapeCli::Article.all.each do |a|
    attributes = ShapeCli::Scraper.scrape_article_page(a.url)
    a.add_article_attributes(attributes)
  end
    input = nil
      while input != "exit"
      input = gets.strip  
    
      if input.to_i > 0 
      the_article = @all[input.to_i - 1]
      puts "
                                SHAPE CLI 
_________________________________________________________________________
   
       #{the_article.name} 
    
       #{the_article.summary}
    
       #{the_article.url}                            
       #{the_article.author}                         
       #{the_article.date}   
_________________________________________________________________________
                                                                        
  Please, enter Y/N or back to return home~        
_________________________________________________________________________" 
     
```

At first, it felt overwhelming in how to connect these classes AND it can be daunting even going over it again, because making things work vs. explaining them to others are pretty different things.

Since we had the data and did not need to create a new Article---> we simply needed to iterate through our scraped data for the article page. We set our scraper to a variable that when passed, will scrape the article page; yet, this time we are asking to find a specifical set of attributes, which is going to be the key:value's url.  

Once we have our url, we are going to return the block |a| and call our send method defined in our #add_student_attributes method from the article class on this block.  It takes an arguments and in this case, we need our argument to be defined as the article's url; which, we have done in the set variable of Attributes.

```
ShapeCli::Article.all.each do |a|
    attributes = ShapeCli::Scraper.scrape_article_page(a.url)
    a.add_article_attributes(attributes)
```

Finally we acces this data through our @all array which is initialized in Article class to store our values.  The Learn curriculum writes it very nicely here:

> Let's look at the same behavior using .send

> sophie = User.new
> sophie.send("name=", "Sophie")
> That is generally considered to be clunky and ugly. It's whats known as "syntactic vinegar". We prefer the "syntactic sugar" of the first approach.
> 
> The .send method, however, is a very useful tool for our metaprogramming purposes. It allows us to abstract away the specific method call:
> 
> sophie = User.new
> sophie.send("#{method_name}=", value)

This connects to our data in this method Here:

```
  def add_student_attributes(article_page)
    article_page.each {|key, value| self.send(("#{key}="), value)}
  end
```

As we pass in our article page argument, we ask our send method to assign and add the hash here in our Scraper class method while we iterate through each page url; thus grabbing the attributes:

```
  def self.scrape_article_page(url)
    page = Nokogiri::HTML(open(url))
    article_page = {}
    #article_page[:name] = page.css("h1.headline").text
    #article_page[:url] = page.css("div.taxonomy-seo-links a").attr("href")
    article_page[:summary] = page.css("p.dek").text.strip
    article_page[:author] = page.css("span.bold.author-name").text.strip
    article_page[:date] = page.css("div.timestamp").text.strip
    article_page[:text] = page.css("p").text.strip
    article_page
  end
end 
```

and Done.  It's a lot to take in, but the easiest way to build this was to start initially with fake data and as long as you understand what each object does, research code or methods that can help you facilitate a quicker, more simple code.

It helped to read and understand the functionality of the scraper class and the methods used in the Student Scraper.  Understanding this as well as previously labs, piece by piece, allow for you to reference other code as a reminder to best practices.

Avi's video helped a lot in the start, in order to set up the project.  Then listen to him grab objects and manipulate them here as a great way to see live what OO is doing.

Practicing along with him as he shows you, not only just watching, helps you learn and understand why things are happening and then it gives good practice in exactly how to code from someone who has coded for 15 years. It becomes easier and your concerns over little qualms begin to disappear through the repitition. We aren't trying to reinvent the wheel.  Trust your teachers and watch Avi's videos.  They are very helpful.


