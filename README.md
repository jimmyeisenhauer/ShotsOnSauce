Shots on Sauce
===========
Open source, cloud based, web browser screen shot comparison tool.  Utilizes github & saucelabs cloud based services.  

Developed and tested on a Mac.  Pull-requests and feature-requests are welcomed.  Follow the Fork, Config, Shoot instructions below to get up and running!


#FORK
Hit the little fork button in the top right.  Then clone the fork to your computer

#CONFIG

Install the components

``` bundle install ```

Go to www.saucelabs.com and sign up for a account and find your grid url

A easy way to find your saucelabs url is to go here: https://saucelabs.com/docs/ondemand/getting-started/env/ruby/se2/mac


Create a ``` config.yaml ``` file in the root directory
add the below two lines to it

```
grid: "http://ursaucelabsurl@ondemand.saucelabs.com:80/wd/hub"
maxthreads: 3
```

-don't worry the ``` config.yaml ``` file is in the .gitignore and won't be checked in.

-make the maxthreads 1 more than you have in your saucelabs account.  This makes sure one is on standby and the others do not time out.  The free saucelabs account comes with 2 threads so start with 3!

Edit the ``` browsers.yaml``` file

Any browser/os combo saucelabs can handle is fair game!

Example:
```
- !ruby/object:Browser 
  name: 'firefox'
  version: '25'
  platform: 'Windows 8'
  resolution: '1280x1024'
```

#SHOOT

Pick a url run the below command and yell SHOTS!!
```
./sos -u http://www.cnn.com
```

Browse in github to your forked repository and view the ``` /commits/  ``` section and checkout your latest commit and screen shots!

Future Features
-------------------------
* base browser - enabling browser vs browser comparison

* complex branching - enabling sophisticated date comparisons 




#License

The MIT License (MIT)

Copyright (c) 2014 James Eisenhauer

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
