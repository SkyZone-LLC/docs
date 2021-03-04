# Landing Page Image Slider
> DOM Events, Arrays, Loops, Styling

## 1. Introduction 

### Goal

The goal is to create an image slider with vanilla javascript. Again here you have to interact with DOM event handlers. And learn how to style your elements inside javascript.

When `right/left` clicked your **background image** and **name of a car** should change accordingly.

Addintioanlly we added `start/stop` buttons to trigger slider automatically.


**WORKSHOP GOAL**

![goal](../_media/workshops/image-slider/image-slider-result.gif)


### Setup

Here are the instructions for our Git workflow one more time.

Both partners should fork this [repo](https://github.com/urakymzhan/image-slider) and clone their fork to their respective machines.

**PartnerA:** Copy the url for your fork's github page from your browser's url bar (it will be something like https://github.com/<PartnerA>/PairExercise.image-slider) and send that url to PartnerB via Slack

**PartnerB:** Copy the url that PartnerA sent you, cd into your local clone on your machine and execute this command using that url:

`git remote add partnerA <partnerA_github_url>`

- Repeat the two steps above, swapping PartnerA and PartnerB
- Both partners should read the README.md of the project (separately)
- Once both partners have read the README.md, start the pairing timer and complete the test specs in order

**When it's time to switch roles**

PartnerA should commit all of their work and push it to their main branch:
```
git add -A
git commit -m "Easy to understand commit message"
git push origin main
```

PartnerB should then pull from their partner's remote (NOT from their own origin):
```
git pull partnerA main
```

Once PartnerB completes the pull, they will have all of PartnerA's work, and you will both be ready to continue with roles reversed. When the time comes to switch again, you simply perform the same process (with roles reversed).




## 2. Getting Started


### Observation
Open up the `index.html` file. For your convenience we provided all the html, css code ready for you. 

`div` with class `img-container` will update its background value.


### Remove boilerplate

Everything you see about `start/stop` buttons can be done at the end. First implement manual `left/right` sliders.

One the ways of tackling this challenge is to store image names and car names inside an array:

**Hint:**
```javascript
  const pictures = [ "contBcg-0", "contBcg-1", "contBcg-2", "contBcg-3", "contBcg-4"];
  const carNames = [ "Mercedes AMG", "Mercedes E Class", "BMW", "AUDI", "Dodge Challenger"];
```

### Get Hands Dirty

Now for **each** button left or right add an event listener. When clicked update the background image and car names.

Don't forget to handle `limits` when changing background or names. So that you don't hang with bigger number than your array lenghts.

**Hint:** `counter and pictures.length corellation`


### Automate it

After you implenented manual sliders, you can move on to work on `start/stop` buttons similarly.

**Hint:** You might want to use `setInterval`. Read more [here](https://www.w3schools.com/jsref/met_win_setinterval.asp) 



> Want to give feedback? Did more than asked? Please slack your instructor.

