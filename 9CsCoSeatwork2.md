# Seatwork #2 - Getting to know CSS Position and z-index.
### This seatwork will ask you to implement the different CSS position on a given code.
### short link to this .md file is: https://bit.ly/4c61P9K
#### Resources (also found in Khub week 5)
- [4 Minute Youtube Video on CSS Position](https://www.youtube.com/watch?v=YEmdHbQBCSQ)
- [CSS Position Tutorial](https://roycan.github.io/CssPositioningZIndexLab/)

### Instructions: 
1. This is individual submission in khub, but you can work with a partner.  When you submit in khub please place both your names in the submission bin.
2. Guided Activity (30 minutes), please follow what is being required.  

    - Make a copy of this .md file to your Q4 repository and name it as **SectionLNseatwork2.md** example **9LiCruzSeatwork2.md**. Place it in your q4 repository vscode local computer. Committing frequently to your Github repository.  
    - Copy the code below and paste it inside a new file (name it as SectionLNseatwork2.html). Place this file in the same location where the .md file is saved. 
    - Change the content values of the meta tags to your names for author/s and the date today for revised.
    - Please do the following tasks that will ask you to reposition HTML elements then answer the guided question for each task on the .md file. Commit changes to the .md file and to the .html file as well.
    **- This seatwork is worth 20pts and should be submitted by the end of the period** The link to [KHub submission bin](https://khub.mc.pshs.edu.ph/mod/assign/view.php?id=15481).
      - Submit the links to your .md file and .html file.

```html
<!DOCTYPE html>
<html>
<head>
  <meta name="author" content="Varick Co" />
  <meta name="revised" content="March 27 2026" />
  <style>
    body { font-family: Arial, sans-serif; }
    .header, .footer {
        background: lightblue;
        padding: 10px;
    }
    .footer {
        opacity: 0.5;
        position: fixed; 
        bottom: 0;
        width: 100%;
    }
    .sidebar {
        background: lightgreen;
        width: 150px;
        height: 200px;
        position: relative; 
        top: 20px; 
        left: 20px;
    }
    .content {
        background: lightyellow;
        width: 300px;
        height: 200px;
        position: absolute; 
        top: 66px; 
        left: 200px;   
        z-index: 1;   
    }    

    .notice {
        position: absolute;
        top: 60px;
        left: 400px;
        background: orange;
        padding: 10px;
        z-index: 2;
    }
  </style>
</head>
<body>
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="content">Main Content</div>
  <div class="footer">Footer</div>
  <div class="notice">Notice!</div>
</body>
</html>
```
### Step 1 (Static vs Relative):

- Add in css ```position: relative; top: 20px; left: 20px;``` to .sidebar.

- Guided Question: What changed compared to the default static positioning? Try to give different values to top and left or you can change it to bottom, right.

    It adds a padding that can move the sidebar relative to the top and left parts of the page. It just goes from its normal position, to 20 px below the top and 20 px to the right of the leftmost side.



### Step 2 (Fixed):

- Add in css ```position: fixed; bottom: 0; width: 100%;``` to .footer.

- Guided Question: What happens when you scroll the page? Why does the footer behave differently from position relative?

    Even when you scroll down the page, since it is fixed positioning, it will not move and it will remain at the bottom of the page. It is not relative to any objects and parts of the webpage and stays glued to the bottom.

### Step 3 (Absolute):

- Add in css ```position: absolute; top: 66px; left: 200px;``` to .content.

- Guided Question: What is the effect of position: absolute on an element? How is it different from fixed?

    Adding absolute to an element makes it compare to its nearest common ancestor, and it is different from fixed because if you scroll the page absolute elements will move, but fixed elements will not.

### Step 4 : (Absolute)

- Add in html ```<div class="notice">Notice!</div>``` and include the css below:

```css
.notice {
    position: absolute;
    top: 60px;
    left: 400px;
    background: orange;
    padding: 10px;
    z-index: 2;
}
```

- Give .content a z-index: 1.

- Guided Question: Why does the notice appear on top of the content? What happens if you swap the z‑index values?

    If you swap the z-index values, the Main Content will appear over the Notice. The notice has a higher z-index, so it is layered in front of Main Content.

- Challenge: 
    * What changes that you have to do on the code that will position .notice box on the top right corner of the .content box? Please write the code on paper as well (both html and css on the part of .notice and .content).

```css
.notice {
    position: absolute;
    top: 70px;
    left: 430px;
    background: orange;
    padding: 10px;
    z-index: 2;
}
```


    * Try to change the position of .content to relative then to fixed. What do you observed each time?

        If you change the position to relative, then it will move from its original position, and it goes way below its usual spot on absolute. If you change it to fixed, nothing seems to change until you scroll, and you will find that main content is not moving. 

    * What do you observe on about the effect of z-index on .notice and .content boxes?

        If the z-index is higher on .notice, then it will appear in front of Main Content. Otherwise, if z-index is higher on .content, then it will appear in front of notice.

3. Please answer the following reflection questions (15 minutes)

    a. Could you summarize the differences between the CSS position values (static, relative, absolute, fixed)? 

        Static is basically the normal positioning, where elements are in a default document flow. Relative is changing the position relative to its normal position, and you can control this with the top, bottom, left, and right. Absolute positions your element to its nearest ancestor. Fixed is positioned relative to the viewport, and no matter how much you scroll, it will remain in place.

    b. How does absolute positioning depend on its parent element?

        Absolute positioning depends on its parent element because it positions itself relative to that parent element. 

    c. How do you differentiate sticky from fixed (you can research on sticky)?

        Sticky is like scrolling normally at the beginning, but instead of dissapearing from the page, it sticks on to your page. In fixed, even at the beginning of scrolling, it will never move.

    d. If you were designing a webpage for a school event, how might you use positioning to highlight important information? Please give concrete examples.

        I would use fixed positioning for a footer, and put contact details and dates and event times there. I would also use sticky positioning at the side of the page for example, people who made the website or event.