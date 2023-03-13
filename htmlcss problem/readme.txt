Problem 1:
Using ReactJs, write a solution that does the following:
1. Render a button on dom

2. On button click change the color of the button randomly 
( available colors are red, green, blue, black and orange ), 
However if the previous color was blue the next color should always be green. 
Use state to store the color.

3. Using store, reducers and context 
( use react hooks, do not use react-redux or any other external library), 
keep track of the colors that were rendered and display it below the button 
in a comma seperated string. For eg red, blue, green . 
The text for each color should also display their color.

Problem 2:
1.Create a html page with an image background covering the full screen.

2. Add a block of width 500px by 300px, which is at center of page both horizontally 
and vertically. However On devices less than 600px, the box should be of full width 
and should center vertically only.

This needs to be done using css only and not javascript

Problem 3:
Using Javascript, 
Write a program that prints the number from 1 to 100. 
But for multiples of three print “Fizz” instead of the number & 
for the multiples of five print “Buzz”. However, for numbers which 
are multiples of both three and five print “ FizzBuzz” instead.




import React, { useState } from "react";

const colors = ["red", "green", "blue", "black", "orange"];

function App() {
  const [previousColor, setPreviousColor] = useState(null);
  const [currentColor, setCurrentColor] = useState(null);

  function handleChangeColor() {
    let newColor;

    if (previousColor === "blue") {
      newColor = "green";
    } else {
      newColor = colors[Math.floor(Math.random() * colors.length)];
    }

    setCurrentColor(newColor);
    setPreviousColor(newColor);
  }

  return (
    <div>
      <button
        style={{ fontSize: "1rem", backgroundColor: currentColor }}
        onClick={handleChangeColor}
      >
        {currentColor ? currentColor : "change colors on click"}
      </button>
    </div>
  );
}

export default App;

