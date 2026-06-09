# rock-paper-scissor
This is a web based rock paper scissors game. Choose the options: rock, paper or scissors to play against the computer.
The script automatically chooses one of the options and compares it with the option user chose.
```javascript
const genCompChoice = () => {
    const option = ["rock", "paper", "scissors"]
    const randIdx = Math.floor(Math.random() * 3)
    return option[randIdx]
}
```
This script checks if the game is draw or not.
```javascript
const drawGame = () => {
    msg.innerText = "Draw!"
    msg.style.background = "#081b31"
}
```
