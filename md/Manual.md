h---
Pr-id: Institute of Network Cultures
P-id: TOD Manual
A-id: 10
Type: article
Book-type: anthology
Anthology item: article
Item-id: unique no.
Article-title: title of the article
Article-status: accepted
Author: name(s) of author(s)
Author-email:   corresponding address
Author-bio:  about the author
Abstract:   short description of the article (100 words)
Keywords:   epub, pandoc, conversion, hybrid, workflow, publishing, arts publishing, styles, css, markdown, design, ebooks, epub3, GitHub
Rights: CC BY-NC 4.0
...


# Manual: How to produce a Theory on Demand

##Contents
 
Introduction 

1\. Prepare your desktop
	
2\. Prepare repository 

3\. Prepare Manuscript 

4\. Make Epub

5\. Make PDF

6\. Publish TOD


#Introduction

This manual shows you, step by step, how to create a theory on demand. 

For more information about the workflow and creating output for print files, visit the PublishingLab [site](http://www.publishinglab.nl/resources/hybrid-publishing-workflow-faq).

The Hybrid Publishing Toolkit method builds on chapter 6 of the Hybrid Publishing Toolkit book, it relies on a makefile and using the command line.

#1. Prepare your desktop 

### Step 1.1 install all requirements

Before you begin you will need to install:

- text processor (Microsoft Office or Openoffice);
- <a href="https://desktop.github.com/">GitHub Desktop</a> (for working collaboratively);
- markdown editor like <a href="http://macdown.uranusjr.com/">MacDown</a> and XCode for Mac or <a href="http://markdownpad.com/">MarkdownPad</a> for Windows (to edit your sourcefiles);
- plain-text editor (like <a href="http://www.sublimetext.com/">Sublime Text</a> or <a href="https://wiki.gnome.org/Apps/Gedit">Gedit</a>);
- <a href="http://www.adobe.com/nl/creativecloud.html">Adobe InDesign</a>; 
- <a href="http://calibre-ebook.com/download">Calibre</a> (to view/edit ebooks);
- <a href="http://pandoc.org/installing.html">Pandoc</a> (you can install Pandoc with <a href="https://brew.sh/">Homebrew</a>);
- git (for Mac git is included in Xcode, for Windows see <a href="https://git-scm.com/download/win">https://git-scm.com/download/win</a>;
- you will need to familiarise yourself with the command line (terminal
on Mac or go to the Start menu on Windows and type cmd into search/run - more <a
href="http://www.computerhope.com/issues/chusedos.htm">here</a>).

Make sure you login your Github desktop:

	User: 
	Pass: 
	
#2 Prepare manuscript 

###Step 2.1  Styling the manuscript inside Word: introducing structural meaning to the text

*For this step, please refer to the test.docx document in in the folder docx of your Manual folder.*

- Prepare your text document according to the INC style guide.
- Assign the title, headlines, the bodytext, and the blockquotes accordingly so that the structure will appear later on in your markdown-file. For this, refer to the template options of
- fered by Word.

*insert here screenshot for word template*

- Divide your document according to its parts. Avoid any special characters in the titles and number them properly: 01colophon, 02introduction, 03chapter1 etc.
- **IMPORTANT:** please make sure that you safe your Word file as .docx.


#3. Prepare repository 
### Step 3.1 Get your git on

Go to [https://github.com/](https://github.com/) and login 

	User: 
	Pass: 
	
- Create a new repository according to the title of your book. Please include number and title of the book, for instance TOD23kaos;
- Clone the repository to your Github desktop (click "Clone or download", then "Open in Desktop");

![](imgs/git.png)

![](imgs/git2.png)

### Step 3.2 Prepare folder // commit to master

Copy folders from this repository (TODManual) to your own theory on demand repository:

- Make sure you copy all folders and make files.
- Make sure your manuscript(s) are saved as .docx files and move them to the .docx folder, replacing the Test-chapter.docx file.
- Avoid any special characters in the title and number them properly: 01colophone, 02introduction, 03chapter1 etc. 
- Copy all your images in the imgs folder of your md folder. 

![](imgs/Folder3.png)
![](imgs/Folder4.png)

**Avoiding Errors**

- make sure there are no spaces or unusual characters (like %) in file names
- make sure you work with .docx files not .doc
- put any images (.jpg or .png) in the 'imgs' folder inside the markdown folder except the cover
- the cover.jpg image belongs in the epub folder

####MAKE SURE YOU UPLOAD ALL CHANGES TO THE REPOSITORY ON GITHUB.ORG BY CLICKING 'COMMIT TO MASTER' AND 'SYNC' IN THE GITHUB DESKTOP 
![](imgs/commit.png)

#4 Make Epub 

###Step 4.1 Convert the .docx to a Markdown plain-text file by: 
		
- Use the command line to navigate to your resources folder. You will need some knowledge of using the command line, you can find help with this <a
href="http://en.flossmanuals.net/command-line/getting-started/">here</a>. You can navigate to that specific folder by typing cd, and then dragging and dropping to the terminal the specific folder.

		cd pathofyourfolder
		
	![](imgs/terminal1.png)

-   After navigating to the right folder, create the source file(s) for your ebook by typing in "make markdowns", then press enter:
		
		make markdowns
	![](imgs/terminal2.png)

You will find the markdown files you created in the md-folder. From now on the Markdown will be the working document, therefore all the changes you would like to make concerning to the content, you should do in the markdown file. 

### Step 4.2 Edit you .md file(s)

Make sure you check the .md file(s) for any errors or glitches: 

- fill out the metadata at the beginning of your .md file(s). Check with the editor if you have the right metadata information, including the ISBN number.
Here's more information about <a href="http://www.publishinglab.nl/blog/2015/09/25/metadata-schmetadata-whats-it-good-for/">metadata</a>.
- make sure every H1, H2, footnote, blockquote etc. is converted correctly
- footnotes appear at the end of you .md file(s) and look like this: 

![](imgs/footnote.png)

- make sure you add your images manually to the .md file(s) by using the syntax:
		
		![](imgs/namefile)

- make sure you name you cover image cover.jpg, and add it to the epub folder

**Most used Syntaxes**

In the image you can see the most used syntaxes. For more examples see <a href="http://daringfireball.net/projects/markdown/syntax](http://daringfireball.net/projects/markdown/syntax">here</a>. 

![](imgs/syntax.jpg)

### Step 4.3 Convert to Epub

Now that you have your markdown file(s), you can create an epub: 

- open the terminal, navigate to your resources folder as you did in 4.1
		
		cd (with a space at end) pathofyourfolder

- then, type in "make book.epub" in your command line and press enter:

		make book.epub
	![](imgs/terminal3.png)

- Check the resources folder to see your book.epub file, which you can open with Calibre or iBooks.

- If you get an error message, there is a useful resource section <a href="http://www.publishinglab.nl/resources/hybrid-publishing-workflow-faq/">here</a> to help you.


### Step 4.4 Design your epub 

A successful epub has been visually styled (with css and a cover), correctly classified (with metadata), and validated. The epub folder typically has 3 important components:

* the cover image (jpg)
* the metadata file
* the stylesheet

![](imgs/epub.png)

The look of your book is controlled by the styles that you can find in the stylesheet. You can get color values and typeface suggestions from the print designer. Make sure you embed the fonts you use by including them in the make file and in the lib folder.
Here's more information about <a href="http://www.publishinglab.nl/blog/2015/07/01/epub-typography/">type in epubs</a>.

If you want to change fonts and colors etc. within the epub you need to do this in the styles.epub.css.

### Step 4.5 Validating your ePub file

Last, but not least, the developer needs to validate epub to make sure there are no errors that will cause it to be rejected from a retailer or not open correctly for readers:

- You can use the <a href="http://validator.idpf.org/">online
validator</a> for smaller ePubs (under 10MB). The validator will show you where the errors are in your book. See the example below:

![](imgs/idpf-validator.png)

- The error occurs in chapter ch002.xhtml, line 47, there's an explanation that a 'referenced resource is missing', but it helps a lot to edit the book in <a href="http://calibre-ebook.com/download">Calibre</a> and further diagnose that in this case an image is missing.

####MAKE SURE YOU UPLOAD ALL CHANGES TO THE REPOSITORY ON GITHUB.ORG BY CLICKING 'COMMIT TO MASTER' AND 'SYNC' IN THE GITHUB DESKTOP 

#5 Make PDF 

### Step 5.1 Create icmls
- open the terminal and navigate to your resources folder as you did in 4.1 

		cd (with a space at end) pathofyourfolder

- Use the command line to convert your md files to icml files by typing:

		make icmls 

Press enter. You can then find the icmls in the icml folder.

### Step 5.2 load icmls in InDesign 
- Copy the TemplateTOD.indd files in the InDD folder and rename all files and make sure you do not use any special characters:
		
		01colophone
		02acknowledgments 
		03introduction 
		04chapter1 

- Drop and drag your icml files in the InDesign document(s).
- Before you are able to edit/design the text in indesign make sure you check out: 
		
		Edit > Incopy > Check Out 

Now you are able to edit your text. 

### Step 5.3 Design your book

- Assign the different text components (headings, bodytext, footnotes) to the different paragraph styles that you can find in the template.
	- H1, H2, H3, titles use Lato font
	- Body text use Trade Gothic Light

### Step 5.4 Export your book
- To export the entire book make use of the book function. Go to:

		File > New > Book
		Define a name and the location: the InDD folder.
		
- Click on '+' to add all chapters of the book. All page numbers should update automatically.
- Click on the right upper button and Export Book to PDF in pages: 
![](imgs/book1.png)

### Step 5.5 Design cover 

- Add title 
- Add blurb on backcover
- Add ISBN
- Add spine (upload pdf on LULU. Lulu will tell you the exact size of the spine). 

####MAKE SURE YOU UPLOAD ALL CHANGES TO THE REPOSITORY ON GITHUB.ORG BY CLICKING 'COMMIT TO MASTER' AND 'SYNC' IN THE GITHUB DESKTOP 

#6. Publish the book 
How to publish the theory on demand online

###Step 6.1 Issuu 
- On Issuu the publication should be set with the cover and single pages in one single PDF
- After the cover follows a white page
- In the case the cover is in a different file use Adobe Acrobat to merge the PDF: [http://www.dummies.com/howto/content/insertinganddeletingpagesinpdfdocumentswith.html](http://www.dummies.com/howto/content/insertinganddeletingpagesinpdfdocumentswith.html)

Go to [http://issuu.com/login?](http://issuu.com/login?) and login as INC: <br />

	user:
	pass: Click on upload: Upload your PDF and fill out the form:  <br />

 - replace the automatically added title;
 - add description (take this from the back cover text); 
 - add date; 
 - click Allow download and leave the visibility on Public;
 - and then Publish!Now you should be able to see your publication in [http://issuu.com/home/publications](http://issuu.com/home/publications)

###Step 6.2 LULU 

In this case we will need two PDFs: 

- For the inside, we need a single PDF with single pages, without cover 
- Spreadsheet for the cover (with spine)

Go to [http://www.lulu.com/](http://www.lulu.com/)
		user:		pass: - Click on Creëren / Create and choose Print book Onthe next page choose **Premium pocketboek**, then scroll down and choose **Royal** as the format and endby clicking **‘Dit boek maken’** in the orange arrow:
- Fill in your Title and Author(s) and leave the first options (Lulu, Amazon, Barnes and Nobles) selected 
- Add the ISBN to the publication, **don’t add the barcode**
- Click on Choose File and select your inside PDF, then click on **Upload**
- Click on **“Make PrintReady File”**
- Click on **“advanced onepiece cover designer”**. You will be prompted with all the necessary specs to create the PDF cover, including the measurements for the cover in total as well as the measurements of the spine. You can design it using Adobe InDesign by creating three pages: the back cover on the left, the spine as page two and the front cover as page three. All pages should be right next to each other. You can adjust the spine by changing the size of the page. Refer to older covers if you are unsure.
- Choose your file and upload it, click **“Save and Continue”**
- Fill the form with the requested info Click **“Save and Continue”**
- Set the price as the minimum suggested by the platform and click on review project
- Finally review your project and then click on **“Save and Finish”**. If you click on the blue title you should see your book for sale on Lulu

###Step 6.3 Upload in INC pageEmbed the book on [http://networkcultures.org/](http://networkcultures.org/). In this last part we will create the page for the publication on the INC blog.
Login to [http://networkcultures.org/](http://networkcultures.org/)- Go over Publications and click on **Add New**; fill the form with title of the book
- Go to the Issuu page relative to the publication and copy the URL
- Paste the url at the top of the content box according to the series, check the correct category. It should look like this: 
			
		[embed]http://issuu.com/instituteofnetworkcultures/docs/issuethelistserveskwerbin?e=3130431/44189048[/embed]

		<a class="pwk-link" style="float: left;margin-right: 15px" href="http://networkcultures.org/wp-content/uploads/2017/02/KennethWerbinTheListServes22.pdf"><img class="alignnone wp-image-4032 size-full" src="http://networkcultures.org/wp-content/uploads/2014/04/inc_icon_pdf_@2x.png" alt="inc_icon_pdf_@2x" width="42" height="42" /></a><a class="pwk-link" style="float: left;margin-right: 15px" href="http://issuu.com/instituteofnetworkcultures/docs/playfulmappinginthedigitalageissue?e=3130431/41821881"><img class="alignnone size-full wp-image-4031" src="http://networkcultures.org/wp-content/uploads/2014/04/inc_icon_issuu_@2x.png" alt="inc_icon_issuu_@2x" width="42" height="42" /></a> <a class="pwk-link" href="http://www.lulu.com/shop/kenneth-c-werbin/the-list-serves/paperback/product-23062384.html" target="_blank"><img class="alignnone wp-image-4057" src="http://networkcultures.org/wp-content/uploads/2014/04/inc_icon_lulu_@2x.png" alt="inc_icon_lulu_@2x" width="42" height="42" /></a><a class="pwk-link" style="clear: both;margin-right: 15px" href="http://networkcultures.org/_uploads/TheListServes.epub" target="_blank"><img class="alignnone wp-image-4033 size-full" src="http://networkcultures.org/wp-content/uploads/2014/04/inc_icon_epub_@2x.png" alt="inc_icon_scribd_@2x" width="42" height="42" /></a>

- Add a (small) cover image- Add colophon info to the Info box
- Don’t add a link in the download area 
- Click on Publish, you should finally see you publication: [http://networkcultures.org/publications/](http://networkcultures.org/publications/)



