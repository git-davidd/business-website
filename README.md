# HC Terra - Project 2-3
Hello everyone, I am participating to the [HC Terra](https://terra.hackclub.com) program to learn HTML, CSS and if neccesairy JS. I hope the prize at the end of the 12 weeks will keep me motivated :)

## About this project
This is my second project. I am learning HTML to build my dad a website for his business. As I practiced a bit with the coding before Terra, I now am kind of confident that I can make something that is sufficient, so after just one real finished small project before this one, I will now start on the real pages.

## Pages and features
**Please keep in mind that for this week i haven't done anything to make the website compatible with mobile devices and not all reactive sizing works perfect.** I will fix these issues later though.

### Navbar
- Holds all links
- "Activates" the link of the section youre currently on
- Moves to the left when scrolling the page
### Welcome
- Container with:
    - Logo
    - Page title
    - Button to "my work"
    - Theme image
### Services
- Holds info of the services my dad offers
- Currently put 3 there with stockphotos and fake text (lorem ipsum)
### About me
- Profile picture placeholder
- Header
- About me paragraph
- Contact button
### More to come in later updates!


## Devlogs
In this file I will log everything I do on which date. I will include calendar week numbers and HC Terra week numbers. I will include everything I do, not only the coding parts. So for example if I do some research before, I'll put it in here. or not if i forget:)
<details><summary><b>Open devlogs (prep week 2)</b></summary>

### Entry #1 - Week 42, 12/10, Prep week 3
Today I want to start making my dad's actual website. I won't put his real name, adress or anything like that on the page. And I'll keep this repo private untill I want to ship the project for the week.

> **[#3843cb3](https://github.com/git-davidd/business-website/commit/3843cb3493ea41e8007816fa7d697d5f851c6554)**
> - I made a project directory
> - I set up the git environment

> **[#bc0d211](https://github.com/git-davidd/business-website/commit/bc0d2113675b22f7201d8ecc8faab65df6d3dfd4)**
> - Wrote a first bit of the README
> - Watch some youtube videos about viewport and css to get in the mood
> - Started on the navbar
>   - Found out that I can't legally host the font that I wanted to use, so I'm going to pick another one from google fonts
>   - Settled on "Montserrat" for the font
>   - Added a placeholder for the logo
>   - Added 3 links
>       - Home (for the homepage, duh)
>       - Over mij ("About me", not a page yet, added for the future)
>       - Gallerij ("Gallery", not a page yet, added for the future)
>   - For now I did a lot with variables in CSS, and I think I'll stick with it, so I can easily make changes on the page.
>   - Made the active page have bold text and an underline
>   - Added a divider between the logo and the pages links


### Entry #2 - Week 42, 13/10, Prep week 3
Today's goal would be setting up the framework on which I can build all pages. With that I mean I want to make sure I have div objects for the background, the foreground. And I want to make CSS styles for the different types for text, so for titles, headers, paragraphs and maybe more.

> **[#c3fa417](https://github.com/git-davidd/business-website/commit/c3fa4175d41edf66e9f78347881e6fdb80f24f44)**
> - After first using a div for the background, I've decided to put the background on the body tag
> - Added a div that is always centered and is 80vw wide, for the homepage content.
> - I'm thinking about lining the navbar buttons out with where the homepage content starts (on the left)
> - I struggled quite a lot with centering the hp-cc (homepage content container) div.. so:

NOTE TO SELF: Please please please just use margin-left and margin-right: auto; to allign something horizontally centered !!

> **[#bea38f9](https://github.com/git-davidd/business-website/commit/bea38f91bf91b6965fe820bf37b2b5bb6241ca28)**
> - Added CSS styles for:
>   - Titles
>   - Headers
>   - Paragraphs

> **[#e05d475](https://github.com/git-davidd/business-website/commit/e05d4754569e52271c0ae10f01dcf895fd8e675c)**
> - Updated dev-logs.md, forgot to do that in last commit

> **[#f91f87d](https://github.com/git-davidd/business-website/commit/f91f87d2ff6149cb3e7b67bb602de7ca20ca48aa)**
> - Added padding to the navbar, so that everything on it is alligned with the homepage content (on the left side)

### Entry #3 - Week 42, 14/10, Prep week 3
Today I'm a little less motivated, but I'll try to just get started so I can still get some work done. What I want to do: Fix up text types with h1 and p for example; try to create a photo carousel at the top of the homepage; and add some (mock) content to the homepage

> **[#cc2b5e9](https://github.com/git-davidd/business-website/commit/cc2b5e92239de7adcb2bfe0906a6d078af3878a9)**
> - Changed `<div class="title">`to `<h1>`
> - Changed `<div class="header">`to `<h2>`
> - Changed `<div class="paragraph">`to `<p>`
> - Moved styling from named classes to named tags

> **[#cee6892](https://github.com/git-davidd/business-website/commit/cee689238c7a1fef7ca36df0aa0847dc1fb2bff1)**
> - Added some placeholder photos to ./assets/hp-carousel/ for the carousel
> - Took part of the html from w3school for the carousel and put it on the homepage
> - I let Claude change up the js script and css parts for the carousel, so that it slides instead of fades. After I put the changes in, I asked Claude to explain all the lines so I actually learn from it.
> - Added `box-sizing: border-box;` to the root of the css, so my page wouldn't have wierd empty space
> - Made it so that the hp-cc doesnt translate down a bit, but instead added `padding-top` to move all content to be below the navbar

> **[#08f3a83](https://github.com/git-davidd/business-website/commit/08f3a839559bc5efa838d1b09c01b20f5dbe1df2)**
> - Added `cursor: pointer` to the nav-buttons and small-logo
> - Added link to the homepage to the small-logo
> - Moved all devlogs to README.md
> - Added move notice to dev-logs.md

> **[#c1de1f5](https://github.com/git-davidd/business-website/commit/c1de1f534cd0736db6f6bdc5a426eb59e7f5ed80)**
> - I let Claude update the js script to not include the title in "active" slides (to make sure there no moment where no slides show up)
> - Struggled a lot with the title that floats over the carousel
>   - The background blur thingy would NOT adjust to the right width
> - In the end I went with a background that is the full with of the page (100vw) and made the text allign by using `padding-left: 15vw`
> - Added a 15% oppacity border to create a little bit of the glass effect with the blur
> - Changed up a view photos

### Entry #4 - Week 42, 16/10, prep week 3

> **[#23c4e0a](https://github.com/git-davidd/business-website/commit/23c4e0a169e1d33b04ceac31b605ac2afdbc48b5)**
> - A few minor changes, i dont even know anymore, just forgot to commit and sync these

Today I want to make the css more readable. I want to clean up unneccesairy lines and I want to rename the styles to make more sense. I also want to create styles for parts the the website, not generic ones.

> **[#cb61530](https://github.com/git-davidd/business-website/commit/cb61530dba5dbba40a400821114929a9e4d24eb1)**
> - shortened CSS style names
> - moved all CSS styles under their own category (their thing on the page)
> - and like very minimal minor teeny tiny changes that i already forgot about

> **[#fe1f064](https://github.com/git-davidd/business-website/commit/fe1f064ea28abe1b9925f9e92fbfb7f9b12abb21)**
> - added favicon
> - renamed some files and folders
> - started on the "Pages and features" bit on the readme

next thing ill work on is a footer

> **[#af12206](https://github.com/git-davidd/business-website/commit/af122064630f6a2bea3f3df82e22c679e1636b28)**
> - started on the footer
>   - added copyright thing
>   - added 2 links for phone and mail contact
>       - These links need some work to make them look right (not off center for example)

ISSUES: horizontal logo on carousel is absolute, so if the vh is small it overlaps with the title.

**AFTER BACKLOG WITH MY DAD**<br>
I had a chat with my dad about the website, and he does want to see things a lot differently. At the time you're reading this, I might have changed that up already. So unfortunately I have to redo a pretty big part, which hopefully won't take too long. Lesson learnt: maybe talk or think the final result a little more through. That said, he also didn't know exactly what he wants and he will research more about that this week. I'm not entirely sure what I'll do this week, A) start on the revamp or B) make this one more of a final product for HC. Right now I'm leaning towards aproach A. Commit #0035aa3 holds 2 non-noticable changes.

### Entry #5 - Week 42, 17/10, prep week 3

> **[#a345dac](https://github.com/git-davidd/business-website/commit/a345dac9b8bce44fdf2517aee0dd39c3050ba0f8)**
> - Removed basically the whole old page, only kept the footer
> - Added welkom (en: welcome) section with logo, title, button
> - Added a navbar
>   - Navbar moves to the left side upon scrolling
>   - Navbar links go to sections on the page using #section
> - Added diensten (en: services) section

### Entry #6 - Week 42, 18/10, prep week 3

> **[#cdbd409](https://github.com/git-davidd/business-website/commit/cdbd409709405dcf837a3549b9623bfeef293fe4)**
> - Added an over mij (en: about me) section with pfp, header and paragraph text (and a contact button)

</details>

<details><summary><b>Open devlogs (week 1)</b></summary>

### Entry #1 - Week 43, 24/10, terra week 1
> **[#77909d8](https://github.com/git-davidd/business-website/commit/77909d8e43410df69edf95380a632d5d35b3a74d)**
> - added some vibecoded gallery page that doesnt work yet. will look at it later, just wanted to test some things.
> - added content section
> - let claude edit the scripts to make the navbar also apply bold text on clicking on of the links, so that when the section is not at the correct heigt (for example when its not tall enough) it still makes the `<a>` bold because you clicked on it.
> - uploaded a bunch of images for the gallery page (that doesnt work yet)

> ### I now have a pretty good draft of what the page should be. Ill not down issues and todos under here:
> **Issues/todo:**
> - Make working gallery page
> - Make compatible with mobile screens
> - Contact button on about me section doesnt work
> - Several horizontal resizing issues
>   - pfp at about me
>   - the 3 bits at services
>   - theming image at welcome
>   - navbar should hide items instead when vw is small
>   - navbar should not go vertical on small vw
>   - footer doesnt resize well