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
        audio.currentTime = 0
        audio.play()
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
The whole script file looks like this:
```js
let userScore = 0
let compScore = 0

const choices = document.querySelectorAll(".choice")
const msg = document.getElementById("msg")
const audio = document.getElementById("winsound")

const userScorePara = document.getElementById("user-score")
const compScorePara = document.getElementById("comp-score")

const genCompChoice = () => {
    const option = ["rock", "paper", "scissors"]
    const randIdx = Math.floor(Math.random() * 3)
    return option[randIdx]
}

const drawGame = () => {
    msg.innerText = "Draw!"
    msg.style.background = "#081b31"
}

const showWinner = (userWin, userChoice, compChoice) => {
    if (userWin) {
        audio.currentTime = 0
        audio.play()
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

const playGame = (userChoice) => {
    const compChoice = genCompChoice()

    if (userChoice === compChoice) {
        drawGame()
    }

    else {
        let userWin = true

        if (userChoice === "rock") {
            userWin = compChoice === "paper" ? false : true
        }

        else if (userChoice === "paper") {
            userWin = compChoice === "scissors" ? false : true
        }

        else {
            userWin = compChoice === "rock" ? false : true
        }

        showWinner(userWin, userChoice, compChoice)
    }
}

choices.forEach((choice) => {
    choice.addEventListener("click", () =>{
        const userChoice = choice.getAttribute("id")
        playGame(userChoice)
    })
})
```
