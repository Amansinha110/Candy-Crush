<h1>Developing a Candy Crush Game Using JavaScript</h1>

<p>My name is Aman Kumar, and I have embarked on an exciting journey to develop a Candy Crush game using JavaScript, HTML, and CSS. Inspired by Kenny Yip Coding's YouTube tutorial, I decided to create my own version of this popular puzzle game.</p>

<h2>Game Concept</h2>

<p>Candy Crush is a match-three puzzle game where players swap candies to form rows or columns of three or more matching candies. When matched, the candies disappear, and new ones fall into place, creating a cascading effect.</p>

<h3>Technologies Used</h3>
<P>To build this game, I used:

HTML for the game structure.

CSS for styling the candies and board.

JavaScript for game logic, including swapping candies, checking matches, and updating the board.</P>

<a href ="https://amansinha110.github.io/Candy-Crush/"><img src = "https://github.com/Amansinha110/Candy-Crush/blob/master/Screenshot%202025-06-01%20053624.png"><img src ="https://github.com/Amansinha110/Candy-Crush/blob/master/OIP.jpeg"></a>
<h1>Click Blue Button For Play</h1>

<h2>Here’s a basic JavaScript implementation:</h2>

```javscript
document.addEventListener("DOMContentLoaded", () => {
    const board = document.querySelector(".board");
    const width = 8;
    const candies = ["🍬", "🍭", "🍫", "🍩", "🍪"];
    let candyGrid = [];

    // Initialize the board
    function createBoard() {
        for (let i = 0; i < width * width; i++) {
            let candy = document.createElement("div");
            candy.classList.add("candy");
            candy.textContent = candies[Math.floor(Math.random() * candies.length)];
            board.appendChild(candy);
            candyGrid.push(candy);
        }
    }

    // Swap candies
    function swapCandies(index1, index2) {
        let temp = candyGrid[index1].textContent;
        candyGrid[index1].textContent = candyGrid[index2].textContent;
        candyGrid[index2].textContent = temp;
    }

    // Check for matches
    function checkMatches() {
        for (let i = 0; i < candyGrid.length; i++) {
            if (i % width < width - 2 &&
                candyGrid[i].textContent === candyGrid[i + 1].textContent &&
                candyGrid[i].textContent === candyGrid[i + 2].textContent) {
                candyGrid[i].textContent = "";
                candyGrid[i + 1].textContent = "";
                candyGrid[i + 2].textContent = "";
            }
        }
    }

    createBoard();
});
```

<h1>Future Enhancements</h1>

<p>To make the game more engaging, I plan to:

Add animations for candy swaps and matches.

Implement a scoring system.

Introduce special candies with unique effects.

Developing this game has been a fun and educational experience, and I look forward to refining it further!
</p>
