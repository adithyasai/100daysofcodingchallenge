# Day 28: Final Project - Build a JavaScript Web Application or Game

Congratulations on reaching the final day of our JavaScript series! Today, you have the opportunity to apply your knowledge and skills by building a small web application or game using JavaScript. This assignment is designed to integrate various concepts we've covered throughout the series.

## Assignment: Build Your Own JavaScript Project

### Requirements:

1. **Choose Your Project:** Select a project idea that aligns with your interests. It could be a to-do list app, a weather application, a quiz game, or any other creative concept you have in mind.

2. **HTML/CSS:** Create a clean and user-friendly interface using HTML for the structure and CSS for styling. Ensure responsiveness for a seamless user experience.

3. **JavaScript Functionality:** Implement JavaScript to add dynamic behavior to your project. Utilize concepts like DOM manipulation, events, functions, and any other relevant features.

4. **Apply Asynchronous Programming:** If applicable, integrate asynchronous operations using concepts like callbacks, promises, or async/await.

5. **Use External APIs (Optional):** If your project allows, fetch data from external APIs to enhance functionality. This could include displaying real-time weather information, fetching trivia questions, or any other relevant data.

6. **Enhance User Interaction:** Implement features that engage users, such as animations, transitions, or any interactive elements that add value to the user experience.

7. **Ensure Code Quality:** Write clean, well-documented code. Use meaningful variable and function names, and follow best practices.

### Example Project Structure:

```plaintext
my-javascript-project/
|-- index.html
|-- styles/
|   |-- main.css
|-- scripts/
|   |-- main.js
|-- assets/
    |-- images/
    |-- other_assets/
```

### Game Hint:

**Hint:** Create an interactive memory card game. The player flips two cards at a time, trying to find matching pairs. The game could include a timer and a score based on the number of moves.

**Example Code Snippet (Memory Card Game):**

```html
<!-- HTML structure for the memory card game -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles/main.css" />
    <title>Memory Card Game</title>
  </head>
  <body>
    <div class="game-container" id="game-container">
      <!-- Memory cards will be dynamically generated here -->
    </div>
    <script src="scripts/main.js"></script>
  </body>
</html>
```

```css
/* CSS styling for the memory card game */
/* Add your own styles for the game cards and container */
.game-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
}
```

```javascript
// JavaScript logic for the memory card game
document.addEventListener("DOMContentLoaded", initGame);

function initGame() {
  const cardSymbols = ["🌟", "🎉", "🌈", "🚀", "🎨", "🍕", "🎸", "📚"];
  const allCards = [...cardSymbols, ...cardSymbols]; // Duplicate to create pairs
  const shuffledCards = shuffle(allCards);
  const gameContainer = document.getElementById("game-container");
  let flippedCards = [];
  let moves = 0;

  // Create and display cards on the game board
  shuffledCards.forEach((symbol, index) => {
    const card = document.createElement("div");
    card.classList.add("card");
    card.dataset.index = index;
    card.innerHTML = '<div class="card-inner"></div>';
    card.addEventListener("click", flipCard);
    gameContainer.appendChild(card);
  });

  // Function to shuffle the cards
  function shuffle(cards) {
    for (let i = cards.length - 1; i > 0; i--) {
      const j = Math.floor(Math.random() * (i + 1));
      [cards[i], cards[j]] = [cards[j], cards[i]];
    }
    return cards;
  }

  // Function to handle card flipping
  function flipCard(event) {
    const selectedCard = event.currentTarget;
    selectedCard.classList.add("flipped");
    flippedCards.push(selectedCard);

    if (flippedCards.length === 2) {
      // Two cards flipped, check for a match
      setTimeout(checkMatch, 800);
      moves++;
      // Update the UI with the number of moves
      // (You can create a UI element for displaying moves)
    }
  }

  // Function to check if the flipped cards match
  function checkMatch() {
    const [card1, card2] = flippedCards;
    const symbol1 = card1.textContent;
    const symbol2 = card2.textContent;

    if (symbol1 === symbol2) {
      // Matching pair, keep cards flipped
      card1.removeEventListener("click", flipCard);
      card2.removeEventListener("click", flipCard);
    } else {
      // Not a match, flip cards back
      card1.classList.remove("flipped");
      card2.classList.remove("flipped");
    }

    flippedCards = []; // Reset flipped cards

    // Check if all pairs are matched
    if (document.querySelectorAll(".flipped").length === shuffledCards.length) {
      // Game completed
      alert(`Congratulations! You completed the game in ${moves} moves.`);
    }
  }
}
```

Remember, this is just one example, and you're encouraged to come up with your unique game idea. Please avoid duplicating the exact game provided in the example. Have fun building your JavaScript project! 🎉
