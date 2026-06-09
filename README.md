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
This script shows draw.
```javascript
const drawGame = () => {
    msg.innerText = "Draw!"
    msg.style.background = "#081b31"
}
```
The following script shows winner.
```javascript
const showWinner = (userWin, userChoice, compChoice) => {
    if (userWin) {
        userScore++
        userScorePara.innerText = userScore
        msg.innerText = `You win! ${userChoice} beats ${compChoice}`
        msg.style.backgroundColor = "green"
    }

    else {
        compScore++
        compScorePara.innerText = compScore
        msg.innerText = `You lost! ${compChoice} beats ${userChoice}`
        msg.style.backgroundColor = "red"
    }
}
```
