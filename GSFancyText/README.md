Summary {#mainpage}
==========

GSFancyText is a rich text drawing library for iOS.


Example
==========

First define the styles using a CSS-like string:

    NSString* styleSheet = @".green {color:#00ff00; font-weight:bold} .gray {color:gray; font-weight:bold}";
    [GSFancyText parseStyleAndSetGlobal:styleSheet];

Then create a GSFancyText object with a markup string:

    GSFancyText* fancyText = [[GSFancyText alloc] initWithMarkupText: @"<span class=green>Hulu</span> <span class=gray>Plus</span>"];

Then you can directly draw this in a customized view:

    [fancyText drawInRect: rect];

Or create a GSFancyTextView object to display it

    GSFancyTextView* fancyView = [[GSFancyTextView alloc] initWithFrame:frame fancyText:fancyText];


Notes on ARC
==========

ARC stands for Automatic Reference Counting.

GSFancyText supports both ARC-enabled and ARC-disabled projects. Depending on your project setting, you need to either enable or delete the following line:

    #define GS_ARC_ENABLED 1

in the GSConfig.h file.

When ARC is enabled, you can further configure the support of weak reference by enabling or disabling the GS_ARC_WEAK_REF_ENABLED flag.

Make sure that modifications of configurations in GSConfig.h is not committed in git.


Use the Demo
==========

The open the GSFancyTextDemo.xcodeproj file with Xcode (4.2 or higher version).

First you need to go to GSConfig.h, and uncomment the following line:

    #define GS_ARC_ENABLED 1

because the demo project has ARC enabled.

Then you should be able to compile and run the app. For better viewing experience, it's recommended to compile it to an iPhone, iPod touch, or iPhone simulator.

You can check the GSFancyTextDemoViewController.m file under demo folder to see how the fancy text is defined. You can also change the parameters and see how it affects the output.




Full Documentation
==========

For markup text and style sheet rules, please check the wiki page:
https://github.com/hulu/GrannySmith/wiki/GSFancyText

To install Xcode docset:
1. Install Doxygen, run ruby docs/create.rb to generate a docset file.
2. Copy the com.hulu.gsfancytext.docset file in GSFancyText/docs folder to ~/Library/Developer/Shared/Documentation/DocSets
3. Restart Xcode

After installing docset, you can hold option key and click a GSFancyText class or method name in Xcode, to preview or link to the documentation page.

To create documentation and docset based on the latest code, install Doxygen and run the script GSFancyText/docs/create.rb
A new docset will be created and installed, and HTML based documentations are available at:
GSFancyText/docs/Doxygen/output/html



Unit Test Coverage
==========

A major portion of GSMarkupNode, GSFancyText, GSHTML, GSParsingHelper, GSHierarchicalScan are covered by unit tests.

Methods involving drawing, view displaying, and view frame updating are not covered.

Covered topics:
* Markup text parsing
* Style sheet parsing
* Markup tree construction
* Node replacing/appending/removing
* Style updating
* Line breaking
* HTML unescaping
* Object deep copying


Demo App Screenshot
==========

![GSFancyText Demo App](https://github.com/hulu/GrannySmith/wiki/GSFancyTextDemo.png)


License
==========
Copyright (C) 2012 by Hulu, LLC

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.



Contact
==========

For support or for further questions, please use the issue tracker of github, or contact:

      grannysmith-dev@googlegroups.com



