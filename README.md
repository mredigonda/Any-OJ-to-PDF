# Get problem statements PDFs from AtCoder, Codeforces, SPOJ

## How to use

Go to the problem page, open the developer tools (F12 in Chrome), go to console, and paste the respective payload below, this will allow you to print the problem statement (you can then select to print it to PDF). All of these preserve images.

These codes delete the prefix letter of the problem since they might cause users to guess the difficulty of the problem, to make this completely effective, make sure to turn off priting "headers and footers".

### AtCoder

```js
var x = document.getElementById('main-container').children[0].children[1].children[0].innerHTML; // title
var y = document.getElementById('task-statement').children[0].children[1]; // content
y.removeChild(y.children[0]); // Hides problem score
document.body.innerHTML = '<h1>' + x.substr(x.indexOf('-') + 2) + '</h1>' + y.innerHTML; // deletes letter code for this problem
window.print();
```

### Codeforces

```js
var x = document.getElementById('pageContent'); // All of the problem statement
var y = x.children[2].children[0].children[0].children[0].children[0].innerHTML; // only the title of the problem like "A - eqweqwe"
x.children[2].children[0].children[0].children[0].children[0].innerHTML = y.substr(y.indexOf('.') + 2); // replace the title for only "eqweqwe"
document.body.innerHTML = x.innerHTML;
window.print();
```

### SPOJ

```javascript
var x = document.getElementById('problem-name').innerHTML;
var y = document.getElementById('problem-body').innerHTML;
document.body.innerHTML = '<h1>' + x + '</h1>' + y; 
window.print();
```

## Problems

* For SPOJ and AtCoder, it doesn't report the time and memory limits, since I'm planning on using vjudge, and that tells you those limits, I plan on getting people watch the limits from there, but you get the idea of how to extend this if you want to, I would, of course, welcome PRs.

* I need support for other OJs, feel free to add yours.
