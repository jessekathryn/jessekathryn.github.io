---
layout: post
title:      "Shape CLI Classes/Modules"
date:       2019-07-01 22:20:24 -0400
permalink:  shape_cli_classes_modules
---


I have a CLI class and a Shape_CLI class in my library folder inside my project, but now I need to create a class for my articles (in order to scrape the data and have it interact with my other classes).

1.  Start building your CLI class and flesh out a "pretend" interface (this means no data)

```

class ShapeCli::CLI 
  
  def home
    puts "
                                                                  SHAPE CLI 
 ________________________________________________________________________
                                                                       
Shape CLI is a quick source for the latest popular topics in Lifestyle.
                                                                      
Want tips and info on beauty, fashion, travel, health, sex, love and  
everything else you need to live a fuller and happier life?            
________________________________________________________________________" 
    menu
  end


  def menu 
    puts " ________________________________________________________________________
                                                                  
   Y = Yes, display articles / N = No, thank you                     ________________________________________________________________________"
     input = nil
      input = gets.strip
        case input
        when "Y" 
          puts display_articles
        when "N"  
          puts exit
        when "back"
          puts home
        when "exit"
          puts exit
        else
          puts "
                                SHAPE CLI 
 _________________________________________________________________________
 
   Y = Yes, display articles / N = No, thank you, let's exit  :        
_________________________________________________________________________"
      end        
    end
    
      
  def display_articles
   puts "
                                SHAPE CLI  
 _________________________________________________________________________   
 Enter a number from the list of latest popular topics in Lifestyle    
 below to view more details                                            
                                                                         "   
    @article = ShapeCli::Article.popular
    @article.each.with_index(1) do |a, i|
     puts "| |#{i}|  #{a.name}"
    end
    puts"_________________________________________________________________________"
    display_details
   end
 
 def display_details   
    input = nil
      while input != "exit"
      input = gets.strip  
    
      if input.to_i > 0 
      the_article = @article[input.to_i - 1]
      puts "
                                SHAPE CLI 
									_________________________________________________________________________
                                                                         
#{the_article.name}                           
#{the_article.summary}                        
#{the_article.url}                            
#{the_article.author}                         
#{the_article.author}                         
#{the_article.date}                           
_________________________________________________________________________"
      elsif input == ""
        puts "
 _________________________________________________________________________
                                                                   
 Please, enter a number between 1-5 / Type back to return to home~                
________________________________________________________________________"
      elsif input == "exit"
        exit
      else
        home
      end 
     end
    end
    
  def exit
    puts "
 _________________________________________________________________________
                
  Exiting.. Thank you for using Shape CLI! Have a nice day~           
_________________________________________________________________________"

 end 
end


```

2. Start one by one and build on to your data with objects created in your object class.  In this case it is "article"..

```

class ShapeCli::Article
  
attr_accessor :article, :name, :url, :summary, :date, :author

  def self.popular
  
  article_1 = self.new
  article_1.name = "5 Ways to Change Your Life -- For Good"
  article_1.url = "https://www.shape.com/lifestyle"
  article_1.summary = "Five no-fail strategies to finally stick to your goals"
  article_1.date = "Updated: March 01, 2019"
  article_1.author = "By Barbara Brody"
  
  article_2 = self.new
  article_2.name = "What Really Helps Get Rid of Cellulite?"
  article_2.url = "https://www.shape.com/lifestyle"
  article_2.summary = "Let's clear this up: Cellulite is natural and normal. But what is happening inside the skin and why? Here, everything you need to know."
  article_2.date = "Updated: March 13, 2019"
  article_2.author = "By Stephanie Dolgoff and Jessica Matthews "
  
  article_3 = self.new
  article_3.name = "10 Simple Rules for a Healthy Life"
  article_3.url = "https://www.shape.com/lifestyle"
  article_3.summary = "Your guide to staying healthy, happy, and fit…for life!"
  article_3.date = "Updated: December 16, 2015"
  article_3.author = "By Jené Luciani"
  
  article_4 = self.new
  article_4.name = "3 Cool Winter Hairstyles"
  article_4.url = "https://www.shape.com/lifestyle"
  article_4.summary = "The wintry skies may be drab and dull, but that doesn't mean your hair needs to be lackluster, too. Just in time for the holiday season, we've got three stylish 'dos anyone can pull off created by Marc Harris, founder and lead stylist of Boston's Salon Marc Harris."
  article_4.date = "Updated: January 07, 2016"
  article_4.author = "Shape.com"
  
  article_5 = self.new
  article_5.name = "7 Mind Tricks for Self-Motivation"
  article_5.url = "https://www.shape.com/lifestyle"
  article_5.summary = "Experts reveal their time management skills to show you how to be more productive with your daily to-do's"
  article_5.date = "Updated: December 16, 2015"
  article_5.author = "By Sara Angle"
  
  [article_1, article_2, article_3, article_4, article_5]
	end
	```
	
	3. When you're able to call on your objects and get your CLI running as you prompt for input, and input is accurately returned as given, then it's time to begin Scraping.

:)
	

