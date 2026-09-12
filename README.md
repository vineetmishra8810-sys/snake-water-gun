<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Snake Water Gun</title>
</head>
<body>

<script>
    // Function to generate computer's choice
    function getComputerChoice() {
        let choices = ["S", "W", "G"];
        let randomIndex = Math.floor(Math.random() * choices.length);
        return choices[randomIndex];
    }

    // Function to decide the winner
    function checkWinner(player, computer) {

        if (player === computer) {
            return "It's a Draw!";
        }

        if (
            (player === "S" && computer === "W") ||
            (player === "W" && computer === "G") ||
            (player === "G" && computer === "S")
        ) {
            return "You Win!";
        }

        return "Computer Wins!";
    }

    // Start the game
    let playAgain = true;

    while (playAgain) {

        let playerChoice = prompt(
            "Enter your choice:\nS = Snake\nW = Water\nG = Gun"
        );

        // Convert input to uppercase
        if (playerChoice !== null) {
            playerChoice = playerChoice.toUpperCase();
        }

        // Check for valid input
        if (
            playerChoice !== "S" &&
            playerChoice !== "W" &&
            playerChoice !== "G"
        ) {
            alert("Invalid choice! Please enter only S, W, or G.");
        } else {

            // Computer makes a random choice
            let computerChoice = getComputerChoice();

            // Display computer's choice
            alert("Computer chose: " + computerChoice);

            // Decide winner
            let result = checkWinner(playerChoice, computerChoice);

            // Show result
            alert(result);
        }

        // Ask if the player wants to play again
        playAgain = confirm("Do you want to play again?");
    }

    alert("Thanks for playing Snake, Water, Gun!");
</script>

</body>
</html>
