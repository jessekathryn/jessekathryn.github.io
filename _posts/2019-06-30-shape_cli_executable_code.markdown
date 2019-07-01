---
layout: post
title:      "Shape CLI Executable Code "
date:       2019-06-30 20:37:44 -0400
permalink:  shape_cli_executable_code
---


The example CLI code can be found [here](https://jessekathryn.github.io/cli_-_my_first_ruby_gem).

Follow the below steps to writing your CLI Class 

1. Make sure your have the right permissions for each file

```
// ♥ ls -lah

total 16K
drwxr-xr-x 4 jessekathryn jessekathryn 4.0K Jun 30 23:26 .
drwxrwxr-x 5 jessekathryn jessekathryn 4.0K Jun 30 23:22 ..
drwxr-xr-x 8 jessekathryn jessekathryn 4.0K Jun 30 23:30 .git
drwxr-xr-x 5 jessekathryn jessekathryn 4.0K Jun 
```

2. These files are executable, but if yours are not type command

```
chmod +x CLI_Name
```

3. Add your #shebang in CLI bin file

4. Name your .call method on the new module/class in bin

5. Create a Class for your CLI in your Lib

6. Write your call method in your new class and fill out your controller

```
class ShapeCli::CLI 
  
  def call
    puts "SHAPE CLI Shape CLI is a quick source for the latest popular topics in Lifestyle!    
    
    Want tips and info on beauty, fashion, travel, health, sex, love and everything else you need to live a fuller and happier life?

    Yes or  No " 
  end
end
```

7. Test it out and watch [this video](https://www.youtube.com/watch?v=_lDExWIhYKI) to set it up step by step with Avi

8. Type out your CLI for now (even though it does not actually scrape data)


