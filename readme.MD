## Grade 5 Cambridge 

U1 
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-input {
            padding: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            font-size: 1rem;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 15px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
        }
        .choices-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .choice-button {
            padding: 10px 20px;
            border-radius: 15px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin: 10px 0;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <div id="answer-options-container"></div>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                question: "In 123.456, what does the 4 represent?",
                answer: "Four hundreds",
                choices: ["Four tenths", "Four hundreds", "Four thousandths", "Four hundredths"]
            },
            {
                question: "Multiply 10 by 100. How many zeros in total?",
                answer: "3",
                choices: ["2", "3", "4", "5"]
            },
            {
                question: "Which is bigger, 0.501 or 0.510?",
                answer: "0.510",
                choices: ["0.501", "0.510", "They're the same", "Can't tell"]
            },
            {
                question: "What's 0.6 rounded to the nearest whole number?",
                answer: "1",
                choices: ["0", "1", "0.5", "0.6"]
            },
            {
                question: "Multiply 5 by 100. What do you get?",
                answer: "500",
                choices: ["50", "500", "5,000", "505"]
            },
            {
                question: "Round 4.86 to the nearest whole number.",
                answer: "5",
                choices: ["4", "5", "4.8", "4.9"]
            },
            {
                question: "If 5 x 3 = 15, what's 5 x 30?",
                answer: "150",
                choices: ["50", "150", "30", "15"]
            },
            {
                question: "Start with 3. Multiply by 10 three times. What number do you get?",
                answer: "3000",
                choices: ["30", "300", "3,000", "300,000"]
            },
            {
                question: "How do you express 4 added to 6 and then multiplied by 2?",
                answer: "(4 + 6) x 2",
                choices: ["4 + 6 x 2", "(4 + 6) x 2", "4 + (6 x 2)", "2 x 4 + 6"]
            },
            {
                question: "What's 0.5 multiplied by 100?",
                answer: "50",
                choices: ["5", "50", "0.05", "500"]
            },
            {
                question: "What's 23 times 45?",
                answer: "1035",
                choices: ["1035", "935", "1025", "950"]
            },
            {
                question: "What's 8928 divided by 12?",
                answer: "744",
                choices: ["744", "764", "752", "734"]
            },
            {
                question: "Round 3.75 to the nearest whole number.",
                answer: "4",
                choices: ["3", "4", "3.8", "3.7"]
            },
            {
                question: "In the number 5,800, what does the 8 represent?",
                answer: "8 thousands",
                choices: ["8 ones", "8 tens", "8 hundreds", "8 thousands"]
            },
            {
                question: "Round 2.49 to the nearest whole number.",
                answer: "2",
                choices: ["2", "3", "2.4", "2.5"]
            },
            {
                question: "Starting with 0 and adding 3 each time, what's the fourth number?",
                answer: "9",
                choices: ["3", "6", "9", "12"]
            },
            {
                question: "Starting with 0 and adding 5 each time, what's the fifth number?",
                answer: "20",
                choices: ["5", "10", "15", "20"]
            },
            {
                question: "What's the third number in the sequence: start with 2 and multiply by 3 each time?",
                answer: "18",
                choices: ["18", "6", "12", "24"]
            },
            {
                question: "If you add 5 to 3 and then triple the result, what do you get?",
                answer: "24",
                choices: ["24", "27", "21", "15"]
            },
            {
                question: "How do you express the idea 'Multiply 5 and 6, then subtract 4'?",
                answer: "(5 x 6) - 4",
                choices: ["(5 x 6) - 4", "5 x (6 - 4)", "(5 - 4) x 6", "5 + 6 x 4"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            const answerOptionsContainer = document.getElementById('answer-options-container');
            answerOptionsContainer.innerHTML = '';
            for (let choice of questionObject.choices) {
                const choiceButton = document.createElement('button');
                choiceButton.classList.add('choice-button');
                choiceButton.innerText = choice;
                choiceButton.onclick = () => {
                    checkAnswer(choice, questionObject.answer);
                }
                answerOptionsContainer.appendChild(choiceButton);
            }
        }

        function checkAnswer(userAnswer, correctAnswer) {
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>

</html>


## U2 


<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Unit 2 - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-input {
            padding: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            font-size: 1rem;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 15px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
        }
        .choices-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .choice-button {
            padding: 10px 20px;
            border-radius: 15px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin: 10px 0;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <div id="answer-options-container"></div>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                question: "In 234.567, which digit represents the tenths place?",
                answer: "6",
                choices: ["2", "5", "6", "7"]
            },
            {
                question: "What is the result of multiplying 10 by 100?",
                answer: "1000",
                choices: ["1000", "100", "10000", "10"]
            },
            {
                question: "Which is greater, 0.601 or 0.610?",
                answer: "0.610",
                choices: ["0.601", "0.610", "Both are equal", "It's not clear"]
            },
            {
                question: "What's 0.7 rounded to the nearest whole number?",
                answer: "1",
                choices: ["0", "1", "0.5", "0.7"]
            },
            {
                question: "Multiply 6 by 1000. What do you get?",
                answer: "6000",
                choices: ["60", "600", "6000", "6"]
            },
            {
                question: "Round 3.89 to the nearest whole number.",
                answer: "4",
                choices: ["3", "4", "3.8", "3.9"]
            },
            {
                question: "What's 5 times 30?",
                answer: "150",
                choices: ["150", "35", "50", "15"]
            },
            {
                question: "Start with 2. Multiply by 10 twice. What number do you get?",
                answer: "200",
                choices: ["20", "200", "2000", "200000"]
            },
            {
                question: "What is 4 added to 6, then multiplied by 3?",
                answer: "30",
                choices: ["18", "30", "12", "24"]
            },
            {
                question: "What's 0.5 multiplied by 1000?",
                answer: "500",
                choices: ["5", "500", "50", "5000"]
            },
            {
                question: "What's the result of 23 times 46?",
                answer: "1058",
                choices: ["1058", "1006", "1060", "1038"]
            },
            {
                question: "Divide 8,888 by 4. What do you get?",
                answer: "2222",
                choices: ["2222", "2224", "2220", "2218"]
            },
            {
                question: "Round 5.45 to the nearest whole number.",
                answer: "5",
                choices: ["5", "6", "5.4", "5.5"]
            },
            {
                question: "In the number 7,900, which digit represents the hundreds place?",
                answer: "9",
                choices: ["7", "9", "0", "There's no hundreds place"]
            },
            {
                question: "If you divide 1234 by 10, which digit moves to the tenths place?",
                answer: "3",
                choices: ["1", "2", "3", "4"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            const answerOptionsContainer = document.getElementById('answer-options-container');
            answerOptionsContainer.innerHTML = '';
            for (let choice of questionObject.choices) {
                const choiceButton = document.createElement('button');
                choiceButton.classList.add('choice-button');
                choiceButton.innerText = choice;
                choiceButton.onclick = () => {
                    checkAnswer(choice, questionObject.answer);
                }
                answerOptionsContainer.appendChild(choiceButton);
            }
        }

        function checkAnswer(userAnswer, correctAnswer) {
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>

</html>




U3 



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-input {
            padding: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            font-size: 1rem;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 15px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
        }
        .choices-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .choice-button {
            padding: 10px 20px;
            border-radius: 15px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <div id="answer-options-container"></div>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                question: "Add: 3/5 + 4/7 + 5/3",
                answer: "7/12",
                choices: ["7/12", "41/35", "29/35", "12/14"]
            },
            {
                question: "John ate 3/8 of a pizza and Mary ate 5/12. How much of the pizza was eaten in total?",
                answer: "7/12",
                choices: ["3/4", "7/12", "13/24", "1/3"]
            },
            {
                question: "Subtract: 9/11 - 4/7",
                answer: "5/18",
                choices: ["5/18", "3/77", "15/77", "7/14"]
            },
            {
                question: "A chocolate bar is divided into 12 pieces. If Sarah eats 1/4 and Joe eats 5/12, how many pieces are left?",
                answer: "6",
                choices: ["5", "7", "6", "3"]
            },
            {
                question: "What is 2/3 divided by 4?",
                answer: "1/6",
                choices: ["1/6", "2/12", "8/12", "1/3"]
            },
            {
                question: "Multiply: 4/5 x 3/2",
                answer: "6/10",
                choices: ["6/10", "8/15", "8/24", "2/3"]
            },
            {
                question: "If a rectangle has a length of 3/4 and a width of 2/3, what is the area?",
                answer: "1/2",
                choices: ["1/2", "6/12", "1/4", "1/7"]
            },
            {
                question: "What is 2/5 of 10?",
                answer: "4",
                choices: ["2", "4", "6", "8"]
            },
            {
                question: "Divide: 5 by 1/3",
                answer: "15",
                choices: ["3", "15", "10", "1.5"]
            },
            {
                question: "If 3/4 of a number is 12, what is the number?",
                answer: "16",
                choices: ["9", "16", "48/3", "3/48"]
            },
            {
                question: "Interpret 5/8 as:",
                answer: "5 divided by 8",
                choices: ["5 divided by 8", "8 divided by 5", "5 times 8", "8 times 5"]
            },
            {
                question: "Divide: 6 by 2/3",
                answer: "9",
                choices: ["4", "9", "3", "12"]
            },
            {
                question: "Sam has 2/3 of a chocolate bar. He wants to share it equally among 3 friends. How much will each friend get?",
                answer: "2/9",
                choices: ["2/9", "1/9", "1/3", "2/6"]
            },
            {
                question: "If 8 kids want to share 4 pizzas equally, how much pizza does each child get?",
                answer: "1/2 pizza",
                choices: ["1/2 pizza", "1/4 pizza", "2/3 pizza", "1 pizza"]
            },
            {
                question: "If you need 3/4 cup of sugar for a recipe and you want to make half of that recipe, how much sugar do you need?",
                answer: "3/8 cup",
                choices: ["1/8 cup", "1/4 cup", "3/8 cup", "1/2 cup"]
            },
            {
                question: "If a container has 5/6 gallons of water and you use half for cooking, how much is left?",
                answer: "5/12 gallons",
                choices: ["5/12 gallons", "1/3 gallons", "1/2 gallons", "1/6 gallons"]
            },
            {
                question: "In a race, Mark finished in 3/5 of an hour. If Jamie took twice as long, how long did Jamie take?",
                answer: "6/5 hours",
                choices: ["3/10 hour", "6/5 hours", "1 hour", "2 hours"]
            },
            {
                question: "A bag has 10 apples. If Lily ate 2/5 of them, how many are left?",
                answer: "6",
                choices: ["2", "4", "6", "8"]
            },
            {
                question: "If a cloth measures 4/5 yards and is cut into 4 equal pieces, how long is each piece?",
                answer: "1/5 yard",
                choices: ["1/5 yard", "1/10 yard", "1/20 yard", "2/5 yard"]
            },
            {
                question: "Alex wants to divide his 3/4 pound of candy into 6 equal parts for his friends. How much candy will each friend get?",
                answer: "1/8 pound",
                choices: ["1/8 pound", "1/12 pound", "3/24 pound", "3/8 pound"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            const answerOptionsContainer = document.getElementById('answer-options-container');
            answerOptionsContainer.innerHTML = '';
            for (let choice of questionObject.choices) {
                const choiceButton = document.createElement('button');
                choiceButton.classList.add('choice-button');
                choiceButton.innerText = choice;
                choiceButton.onclick = () => {
                    checkAnswer(choice, questionObject.answer);
                }
                answerOptionsContainer.appendChild(choiceButton);
            }
        }

        function checkAnswer(userAnswer, correctAnswer) {
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>




U4 



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-input {
            padding: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            font-size: 1rem;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 15px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
        }
        .choices-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .choice-button {
            padding: 10px 20px;
            border-radius: 15px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin: 10px 0;
        }
    </style>
</head>
<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <div id="answer-options-container"></div>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                question: "What is the point where the x-axis and y-axis meet called?",
                answer: "Origin",
                choices: ["Origin", "Intersection", "Middle Point", "Central Axis"]
            },
            {
                question: "John walked 3 units right and 4 units up on a coordinate plane. Which coordinate did he land on?",
                answer: "(3,4)",
                choices: ["(3,4)", "(4,3)", "(-3,-4)", "(-4,-3)"]
            },
            {
                question: "If a point is at (5,0), where is it located?",
                answer: "5 units to the right of the origin",
                choices: [
                    "5 units up from the origin",
                    "5 units down from the origin",
                    "5 units to the right of the origin",
                    "5 units to the left of the origin"
                ]
            },
            {
                question: "Which axis is the horizontal line on the coordinate plane?",
                answer: "x-axis",
                choices: ["y-axis", "z-axis", "x-axis", "w-axis"]
            },
            {
                question: "Which coordinate represents a point that's 2 units to the left and 3 units down from the origin?",
                answer: "(-2,-3)",
                choices: ["(2,3)", "(-2,-3)", "(-2,3)", "(3,-2)"]
            },
            {
                question: "Which shape has four right angles?",
                answer: "Rectangle",
                choices: ["Circle", "Triangle", "Rectangle", "Rhombus"]
            },
            {
                question: "If all squares are rectangles because they both have four sides, what makes a square special?",
                answer: "All sides are equal in length.",
                choices: [
                    "It has no right angles.",
                    "All sides are equal in length.",
                    "It has two right angles.",
                    "It's always big."
                ]
            },
            {
                question: "Which shape is a quadrilateral with opposite sides that are parallel?",
                answer: "Parallelogram",
                choices: ["Triangle", "Circle", "Parallelogram", "Pentagon"]
            },
            {
                question: "All rectangles have:",
                answer: "Four right angles",
                choices: ["3 sides", "No right angles", "Four right angles", "Curved sides"]
            },
            {
                question: "Which of these is NOT a property of all parallelograms?",
                answer: "All sides are of equal length",
                choices: [
                    "Opposite sides are parallel",
                    "All sides are of equal length",
                    "Opposite angles are equal",
                    "They are quadrilaterals"
                ]
            },
            {
                question: "Which shape is known for having all its sides of equal length and all right angles?",
                answer: "Square",
                choices: ["Triangle", "Square", "Circle", "Trapezoid"]
            },
            {
                question: "Every square is also a:",
                answer: "Rectangle",
                choices: ["Circle", "Triangle", "Rectangle", "Hexagon"]
            },
            {
                question: "What shape has two pairs of equal-length sides, but not all sides are the same length?",
                answer: "Rhombus",
                choices: ["Square", "Rhombus", "Rectangle", "Circle"]
            },
            {
                question: "All quadrilaterals with two pairs of opposite sides parallel are:",
                answer: "Parallelograms",
                choices: ["Triangles", "Circles", "Parallelograms", "Pentagons"]
            },
            {
                question: "If a shape has 4 right angles and all sides are the same length, it's a:",
                answer: "Square",
                choices: ["Rhombus", "Square", "Trapezoid", "Triangle"]
            },
            {
                question: "Sarah plotted a point 4 units to the left of the origin on the coordinate plane. What is the x-coordinate of her point?",
                answer: "-4",
                choices: ["4", "-4", "0", "1"]
            },
            {
                question: "On which axis do we move up or down?",
                answer: "y-axis",
                choices: ["x-axis", "y-axis", "z-axis", "w-axis"]
            },
            {
                question: "Which shape can be classified as a rectangle but has all its sides of the same length?",
                answer: "Square",
                choices: ["Rhombus", "Square", "Triangle", "Pentagon"]
            },
            {
                question: "How many sides does a parallelogram have?",
                answer: "4",
                choices: ["3", "4", "5", "6"]
            },
            {
                question: "Which of the following is a property that both squares and rectangles share?",
                answer: "All sides are of equal length.",
                choices: [
                    "All sides are of equal length.",
                    "Contains four right angles.",
                    "Contains no right angles.",
                    "Has only two sides of equal length."
                ]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            const answerOptionsContainer = document.getElementById('answer-options-container');
            answerOptionsContainer.innerHTML = '';
            for (let choice of questionObject.choices) {
                const choiceButton = document.createElement('button');
                choiceButton.classList.add('choice-button');
                choiceButton.innerText = choice;
                choiceButton.onclick = () => {
                    checkAnswer(choice, questionObject.answer);
                }
                answerOptionsContainer.appendChild(choiceButton);
            }
        }

        function checkAnswer(userAnswer, correctAnswer) {
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>




##Grade 6 Cambridge 

U1 

<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Numera - Challenge Yourself</title>
  <style>
    body {
      font-family: 'Georgia', serif;
      margin: 0;
      padding: 0;
      color: #000033;
      background-color: white;
    }

    .question-container {
      padding: 40px;
      text-align: center;
    }

    .question-box {
      border: 2px solid #000033;
      padding: 20px;
      border-radius: 15px;
      margin: 20px 0;
    }

    .answer-input {
      padding: 10px;
      width: 50%;
      border-radius: 15px;
      border: 2px solid #000033;
      font-size: 1rem;
    }

    .submit-button {
      padding: 10px 20px;
      border-radius: 15px;
      background-color: white;
      color: #000033;
      border: 2px solid #000033;
      cursor: pointer;
    }

    .choices-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    .choice-button {
      padding: 10px 20px;
      border-radius: 15px;
      background-color: white;
      color: #000033;
      border: 2px solid #000033;
      cursor: pointer;
      margin: 10px 0;
    }
  </style>
</head>

<body>
  <div class="question-container">
    <div class="question-box">
      <h3>Question:</h3>
      <p id="question-text">Loading question...</p>
      <div id="answer-options-container"></div>
      <button class="submit-button" onclick="checkAnswer()">Submit</button>
    </div>
  </div>

  <script>
    const questionsDatabase = [
      {
        question: "A bakery uses the ratio of 2 cups of flour to 1 cup of sugar for its cookies. This means:",
        answer: "a) For every 1 cup of sugar, there are 2 cups of flour.",
        choices: ["a) For every 1 cup of sugar, there are 2 cups of flour.", "b) For every 2 cups of sugar, there is 1 cup of flour.", "c) There are more cups of sugar than flour.", "d) They use equal amounts of flour and sugar."]
      },
      {
        question: "John read 4 books in 8 days. How many books does he read in 1 day?",
        answer: "d) 2 books",
        choices: ["a) 0.5 books", "b) 0.8 books", "c) 1 book", "d) 2 books"]
      },
      {
        question: "If a car consumes gas at the rate of 3 gallons per 60 miles, how much gas will it consume for 20 miles?",
        answer: "a) 1 gallon",
        choices: ["a) 1 gallon", "b) 2 gallons", "c) 3 gallons", "d) 4 gallons"]
      },
      {
        question: "If the table shows that 3 shirts cost $45, how much do 6 shirts cost?",
        answer: "c) $90",
        choices: ["a) $60", "b) $75", "c) $90", "d) $120"]
      },
      {
        question: "Maria buys 5 candy bars for $25. How much does each candy bar cost?",
        answer: "b) $5",
        choices: ["a) $2", "b) $5", "c) $10", "d) $12.50"]
      },
      {
        question: "A car travels 150 miles in 3 hours. What's the speed of the car per hour?",
        answer: "b) 50 mph",
        choices: ["a) 45 mph", "b) 50 mph", "c) 55 mph", "d) 60 mph"]
      },
      {
        question: "If 40% of a class of 30 students like chocolate ice cream, how many students like chocolate ice cream?",
        answer: "b) 12 students",
        choices: ["a) 8 students", "b) 12 students", "c) 18 students", "d) 20 students"]
      },
      {
        question: "If 1 mile equals 1.6 kilometers, how many kilometers are there in 5 miles?",
        answer: "b) 8 km",
        choices: ["a) 3 km", "b) 8 km", "c) 10 km", "d) 12.5 km"]
      },
      {
        question: "If 1 liter of water weighs 1 kilogram, how much does 4 liters of water weigh?",
        answer: "c) 4 kg",
        choices: ["a) 2 kg", "b) 3 kg", "c) 4 kg", "d) 5 kg"]
      },
      {
        question: "If a dozen eggs cost $3, how much does each egg cost?",
        answer: "a) $0.25",
        choices: ["a) $0.25", "b) $0.30", "c) $0.75", "d) $1"]
      },
      {
        question: "On a number line, if 2 units represent $10, how much do 5 units represent?",
        answer: "d) $50",
        choices: ["a) $15", "b) $20", "c) $25", "d) $50"]
      },
      {
        question: "If a shirt is sold at 20% off its original price of $50, how much is the discount?",
        answer: "d) $20",
        choices: ["a) $5", "b) $10", "c) $15", "d) $20"]
      },
      {
        question: "If 1 hour equals 60 minutes, how many minutes are in 2.5 hours?",
        answer: "b) 150 minutes",
        choices: ["a) 120 minutes", "b) 150 minutes", "c) 175 minutes", "d) 200 minutes"]
      },
      {
        question: "For every 4 pencils James has, Karen has 3. If James has 16 pencils, how many does Karen have?",
        answer: "a) 12 pencils",
        choices: ["a) 12 pencils", "b) 15 pencils", "c) 18 pencils", "d) 20 pencils"]
      },
      {
        question: "If 1 tablespoon equals 3 teaspoons, how many teaspoons are in 4 tablespoons?",
        answer: "b) 12 teaspoons",
        choices: ["a) 8 teaspoons", "b) 12 teaspoons", "c) 16 teaspoons", "d) 20 teaspoons"]
      }
    ];

    let currentQuestionIndex = 0;

    function displayNextQuestion() {
      const questionObject = questionsDatabase[currentQuestionIndex];
      document.getElementById('question-text').innerText = questionObject.question;

      const answerOptionsContainer = document.getElementById('answer-options-container');
      answerOptionsContainer.innerHTML = '';
      for (let choice of questionObject.choices) {
        const choiceButton = document.createElement('button');
        choiceButton.classList.add('choice-button');
        choiceButton.innerText = choice;
        choiceButton.onclick = () => {
          checkAnswer(choice, questionObject.answer);
        }
        answerOptionsContainer.appendChild(choiceButton);
      }
    }

    function checkAnswer(userAnswer, correctAnswer) {
      if (userAnswer === correctAnswer) {
        currentQuestionIndex++;
        if (currentQuestionIndex < questionsDatabase.length) {
          displayNextQuestion();
        } else {
          alert('Congratulations! You have completed all the questions.');
        }
      } else {
        alert('Incorrect Answer. Try Again!');
      }
    }

    displayNextQuestion();
  </script>
</body>

</html>


U2 


<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Numera - Challenge Yourself</title>
  <style>
    body {
      font-family: 'Georgia', serif;
      margin: 0;
      padding: 0;
      color: #000033;
      background-color: white;
    }

    .question-container {
      padding: 40px;
      text-align: center;
    }

    .question-box {
      border: 2px solid #000033;
      padding: 20px;
      border-radius: 15px;
      margin: 20px 0;
    }

    .answer-input {
      padding: 10px;
      width: 50%;
      border-radius: 15px;
      border: 2px solid #000033;
      font-size: 1rem;
    }

    .submit-button {
      padding: 10px 20px;
      border-radius: 15px;
      background-color: white;
      color: #000033;
      border: 2px solid #000033;
      cursor: pointer;
    }

    .choices-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    .choice-button {
      padding: 10px 20px;
      border-radius: 15px;
      background-color: white;
      color: #000033;
      border: 2px solid #000033;
      cursor: pointer;
      margin: 10px 0;
    }
  </style>
</head>

<body>
  <div class="question-container">
    <div class="question-box">
      <h3>Question:</h3>
      <p id="question-text">Loading question...</p>
      <div id="answer-options-container"></div>
      <button class="submit-button" onclick="checkAnswer()">Submit</button>
    </div>
  </div>

  <script>
    const questionsDatabase = [
      {
        question: "If Maria has 2/3 of a pizza and wants to share it with her friend equally, how much pizza will each person get?",
        answer: "b) 1/3",
        choices: ["a) 1/6", "b) 1/3", "c) 1/2", "d) 2/3"]
      },
      {
        question: "Three friends are sharing 1/2 gallon of lemonade. If they divide it equally, how much lemonade will each friend get?",
        answer: "c) 1/6 gallon",
        choices: ["a) 1/3 gallon", "b) 1/4 gallon", "c) 1/6 gallon", "d) 1/5 gallon"]
      },
      {
        question: "Which of these is the result of 648 divided by 6?",
        answer: "b) 108",
        choices: ["a) 102", "b) 108", "c) 110", "d) 104"]
      },
      {
        question: "What is 2.5 × 2.0?",
        answer: "a) 5",
        choices: ["a) 5", "b) 5.5", "c) 50", "d) 0.5"]
      },
      {
        question: "Which of these is a factor of both 36 and 48?",
        answer: "b) 12",
        choices: ["a) 3", "b) 12", "c) 16", "d) 9"]
      },
      {
        question: "If the temperature is -5°C today and was -10°C yesterday, which day was colder?",
        answer: "b) Yesterday",
        choices: ["a) Today", "b) Yesterday", "c) Both were equally cold", "d) There isn't enough information"]
      },
      {
        question: "Which of these represents a depth below sea level?",
        answer: "c) -5m",
        choices: ["a) 5m", "b) 0m", "c) -5m", "d) 15m"]
      },
      {
        question: "If you placed 3 and -3 on a number line, which one would be to the left?",
        answer: "b) -3",
        choices: ["a) 3", "b) -3", "c) Both in the middle", "d) There isn't enough information"]
      },
      {
        question: "Which quadrant will the point (-5,3) fall into on a graph?",
        answer: "b) Quadrant II",
        choices: ["a) Quadrant I", "b) Quadrant II", "c) Quadrant III", "d) Quadrant IV"]
      },
      {
        question: "Which number is farther from zero on a number line?",
        answer: "a) -7",
        choices: ["a) -7", "b) 5", "c) Both are the same distance", "d) 0"]
      },
      {
        question: "If someone owes you $10, what's the absolute value of the amount they owe you?",
        answer: "b) 10",
        choices: ["a) -$10", "b) 10", "c) $0", "d) 20"]
      },
      {
        question: "Which number is greater?",
        answer: "b) -5",
        choices: ["a) -3", "b) -5", "c) 0", "d) They're both the same"]
      },
      {
        question: "If a submarine is 30 meters below sea level, which of these represents its depth?",
        answer: "c) -30",
        choices: ["a) 30", "b) |30|", "c) -30", "d) |-30|"]
      },
      {
        question: "Which point is in the bottom right quadrant of a graph?",
        answer: "c) (-3,-3)",
        choices: ["a) (3,3)", "b) (-3,3)", "c) (-3,-3)", "d) (3,-3)"]
      },
      {
        question: "If two points on a graph have the same x-coordinate of 4, what is the distance between them?",
        answer: "c) 0 units",
        choices: ["a) 4 units", "b) 8 units", "c) 0 units", "d) Cannot be determined from the information given."]
      }
    ];

    let currentQuestionIndex = 0;

    function displayNextQuestion() {
      const questionObject = questionsDatabase[currentQuestionIndex];
      document.getElementById('question-text').innerText = questionObject.question;

      const answerOptionsContainer = document.getElementById('answer-options-container');
      answerOptionsContainer.innerHTML = '';
      for (let choice of questionObject.choices) {
        const choiceButton = document.createElement('button');
        choiceButton.classList.add('choice-button');
        choiceButton.innerText = choice;
        choiceButton.onclick = () => {
          checkAnswer(choice, questionObject.answer);
        }
        answerOptionsContainer.appendChild(choiceButton);
      }
    }

    function checkAnswer(userAnswer, correctAnswer) {
      if (userAnswer === correctAnswer) {
        currentQuestionIndex++;
        if (currentQuestionIndex < questionsDatabase.length) {
          displayNextQuestion();
        } else {
          alert('Congratulations! You have completed all the questions.');
        }
      } else {
        alert('Incorrect Answer. Try Again!');
      }
    }

    displayNextQuestion();
  </script>
</body>

</html>

U3

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Numera - Challenge Yourself</title>
  <style>
    body {
      font-family: 'Georgia', serif;
      margin: 0;
      padding: 0;
      color: #000033;
      background-color: white;
    }

    .question-container {
      padding: 40px;
      text-align: center;
    }

    .question-box {
      border: 2px solid #000033;
      padding: 20px;
      border-radius: 15px;
      margin: 20px 0;
    }

    .answer-input {
      padding: 10px;
      width: 50%;
      border-radius: 15px;
      border: 2px solid #000033;
      font-size: 1rem;
    }

    .submit-button {
      padding: 10px 20px;
      border-radius: 15px;
      background-color: white;
      color: #000033;
      border: 2px solid #000033;
      cursor: pointer;
    }

    .choices-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    .choice-button {
      padding: 10px 20px;
      border-radius: 15px;
      background-color: white;
      color: #000033;
      border: 2px solid #000033;
      cursor: pointer;
      margin: 10px 0;
    }
  </style>
</head>

<body>
  <div class="question-container">
    <div class="question-box">
      <h3>Question:</h3>
      <p id="question-text">Loading question...</p>
      <div id="answer-options-container"></div>
      <button class="submit-button" onclick="checkAnswer()">Submit</button>
    </div>
  </div>

  <script>
    const questionsDatabase = [
      {
        question: "What is the value of 3^(2/3)?",
        answer: "c) 9",
        choices: ["a) 5", "b) 6", "c) 9", "d) 11"]
      },
      {
        question: "Which expression represents 'Add 4 to a number x'?",
        answer: "c) x+4",
        choices: ["a) -4x", "b) 4x", "c) x+4", "d) x/4"]
      },
      {
        question: "In the expression 5x+3y, what is the coefficient of x?",
        answer: "5",
        choices: ["a) 5", "b) 3", "c) 1/5x", "d) 1/3y"]
      },
      {
        question: "Given a=2 and b=3, what is the value of a^2+b?",
        answer: "b) 10",
        choices: ["a) 7", "b) 10", "c) 5", "d) 4"]
      },
      {
        question: "What is the value of 4+3x2?",
        answer: "a) 10",
        choices: ["a) 10", "b) 14", "c) 24", "d) 20"]
      },
      {
        question: "Which expression is equivalent to 3(x+4) using the distributive property?",
        answer: "b) 3x+12",
        choices: ["a) 3/7x+12/7", "b) 3x+12", "c) 1/3x+4", "d) 9/11x+36/11"]
      },
      {
        question: "Which expression is equivalent to (1/3)x+(1/3)x+(1/3)x?",
        answer: "c) (1/3)3x",
        choices: ["a) (1/6)x", "b) (1/9)x", "c) (1/3)3x", "d) (1/4)x"]
      },
      {
        question: "If x+5=10, what is x?",
        answer: "a) 2",
        choices: ["a) 2", "b) 5", "c) 15", "d) 3"]
      },
      {
        question: "If each apple costs $3 and John spent $15 on apples, how many apples did he buy?",
        answer: "c) 5 apples",
        choices: ["a) 2 apples", "b) 3 apples", "c) 5 apples", "d) 8 apples"]
      },
      {
        question: "Which inequality represents 'a number n is less than 7'?",
        answer: "d) n<7",
        choices: ["a) n>7", "b) n≤7", "c) n≥7", "d) n<7"]
      },
      {
        question: "Which number is a solution to the inequality x>5?",
        answer: "c) 6",
        choices: ["a) 3", "b) 5", "c) 6", "d) 0"]
      },
      {
        question: "If y represents the total cost and x represents the number of toys bought at $5 each, which equation represents this relationship?",
        answer: "a) y=x+5",
        choices: ["a) y=x+5", "b) y=x-5", "c) y=5x", "d) y=x/5"]
      },
      {
        question: "In the equation d=65t, if d=130, what is t?",
        answer: "b) 2",
        choices: ["a) 1", "b) 2", "c) 0.5", "d) 65"]
      },
      {
        question: "If you graph the equation y=3x, what will the y-value be when x=4?",
        answer: "d) 12",
        choices: ["a) 7", "b) 12", "c) 13", "d) 15"]
      },
      {
        question: "In a scenario where y is the total price and x is the number of shirts bought, which variable is the independent variable?",
        answer: "b) x",
        choices: ["a) y", "b) x", "c) Both are dependent", "d) Cannot determine"]
      }
    ];

    let currentQuestionIndex = 0;

    function displayNextQuestion() {
      const questionObject = questionsDatabase[currentQuestionIndex];
      document.getElementById('question-text').innerText = questionObject.question;

      const answerOptionsContainer = document.getElementById('answer-options-container');
      answerOptionsContainer.innerHTML = '';
      for (let choice of questionObject.choices) {
        const choiceButton = document.createElement('button');
        choiceButton.classList.add('choice-button');
        choiceButton.innerText = choice;
        choiceButton.onclick = () => {
          checkAnswer(choice, questionObject.answer);
        }
        answerOptionsContainer.appendChild(choiceButton);
      }
    }

    function checkAnswer(userAnswer, correctAnswer) {
      if (userAnswer === correctAnswer) {
        currentQuestionIndex++;
        if (currentQuestionIndex < questionsDatabase.length) {
          displayNextQuestion();
        } else {
          alert('Congratulations! You have completed all the questions.');
        }
      } else {
        alert('Incorrect Answer. Try Again!');
      }
    }

    displayNextQuestion();
  </script>
</body>

</html>



U4 


<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Numera - Challenge Yourself</title>
  <style>
    body {
      font-family: 'Georgia', serif;
      margin: 0;
      padding: 0;
      color: #000033;
      background-color: white;
    }

    .question-container {
      padding: 40px;
      text-align: center;
    }

    .question-box {
      border: 2px solid #000033;
      padding: 20px;
      border-radius: 15px;
      margin: 20px 0;
    }

    .answer-input {
      padding: 10px;
      width: 50%;
      border-radius: 15px;
      border: 2px solid #000033;
      font-size: 1rem;
    }

    .submit-button {
      padding: 10px 20px;
      border-radius: 15px;
      background-color: white;
      color: #000033;
      border: 2px solid #000033;
      cursor: pointer;
    }

    .choices-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    .choice-button {
      padding: 10px 20px;
      border-radius: 15px;
      background-color: white;
      color: #000033;
      border: 2px solid #000033;
      cursor: pointer;
      margin: 10px 0;
    }
  </style>
</head>
<body>
  <div class="question-container">
    <div class="question-box">
      <h3>Question:</h3>
      <p id="question-text">Loading question...</p>
      <div id="answer-options-container"></div>
      <button class="submit-button" onclick="checkAnswer()">Submit</button>
    </div>
  </div>

  <script>
    const questionsDatabase = [
      {
        question: "A right triangle has a base of 3 units and a height of 4 units. What is its area?",
        answer: "a) 6 sq. units",
        choices: ["a) 6 sq. units", "b) 12 sq. units", "c) 7 sq. units", "d) 14 sq. units"]
      },
      {
        question: "What is the area of a square with a side length of 4 units?",
        answer: "b) 16 sq. units",
        choices: ["a) 8 sq. units", "b) 16 sq. units", "c) 12 sq. units", "d) 4 sq. units"]
      },
      {
        question: "A box has a length of 2 units, a width of 3 units, and a height of 4 units. What is its volume?",
        answer: "b) 24 cu. units",
        choices: ["a) 20 cu. units", "b) 24 cu. units", "c) 30 cu. units", "d) 18 cu. units"]
      },
      {
        question: "Given the points (2,2) and (2,5), how long is the line connecting them?",
        answer: "b) 3 units",
        choices: ["a) 2 units", "b) 3 units", "c) 4 units", "d) 5 units"]
      },
      {
        question: "A rectangle has a length of 5 units and a width of 3 units. What is its area?",
        answer: "d) 15 sq. units",
        choices: ["a) 8 sq. units", "b) 10 sq. units", "c) 15 sq. units", "d) 15 sq. units"]
      },
      {
        question: "A cube has 6 faces. If each face has an area of 4 sq. units, what's the total surface area?",
        answer: "b) 24 sq. units",
        choices: ["a) 12 sq. units", "b) 24 sq. units", "c) 16 sq. units", "d) 18 sq. units"]
      },
      {
        question: "A hexagon is divided into 6 triangles. If one triangle has an area of 2 sq. units, what's the hexagon's total area?",
        answer: "b) 12 sq. units",
        choices: ["a) 6 sq. units", "b) 12 sq. units", "c) 8 sq. units", "d) 10 sq. units"]
      },
      {
        question: "Which inequality represents \"a number is less than 7\"?",
        answer: "c) x < 7",
        choices: ["a) x > 7", "b) x = 7", "c) x < 7", "d) x ≥ 7"]
      },
      {
        question: "A prism has 3 rectangular faces. If each face has an area of 6 sq. units, what's the total surface area of those 3 faces?",
        answer: "c) 18 sq. units",
        choices: ["a) 10 sq. units", "b) 12 sq. units", "c) 18 sq. units", "d) 15 sq. units"]
      },
      {
        question: "What's the formula to find the volume of a rectangular prism?",
        answer: "b) lwh",
        choices: ["a) l + w + h", "b) lwh", "c) lw/h", "d) l-w+h"]
      },
      {
        question: "A large rectangle is composed of 3 smaller rectangles. Two have an area of 5 sq. units and one has an area of 10 sq. units. What's the total area of the large rectangle?",
        answer: "c) 20 sq. units",
        choices: ["a) 15 sq. units", "b) 20 sq. units", "c) 20 sq. units", "d) 25 sq. units"]
      },
      {
        question: "A triangle in the coordinate plane has vertices at (1,1), (1,3), and (3,1). What's the length of the triangle's base?",
        answer: "c) 2 units",
        choices: ["a) 1 unit", "b) 1.5 units", "c) 2 units", "d) 2.5 units"]
      },
      {
        question: "A trapezoid has bases of 4 units and 6 units, and a height of 3 units. What is its area?",
        answer: "b) 15 sq. units",
        choices: ["a) 12 sq. units", "b) 15 sq. units", "c) 16 sq. units", "d) 18 sq. units"]
      },
      {
        question: "A rectangular prism has a length of 1/2 unit, a width of 1 unit, and a height of 2 units. What is its volume?",
        answer: "b) 1 cu. units",
        choices: ["a) 1 cu. unit", "b) 1 cu. unit", "c) 2 cu. units", "d) 3 cu. units"]
      },
      {
        question: "If a pyramid's base has an area of 5 sq. units, and each of its 3 triangular faces has an area of 3 sq. units, what's the total surface area?",
        answer: "c) 26 sq. units",
        choices: ["a) 11 sq. units", "b) 14 sq. units", "c) 26 sq. units", "d) 18 sq. units"]
      },
      {
        question: "If the height of a right triangle is twice its base, and its base is 4 units, what is the triangle's area?",
        answer: "b) 8 sq. units",
        choices: ["a) 4 sq. units", "b) 8 sq. units", "c) 12 sq. units", "d) 16 sq. units"]
      },
      {
        question: "If a square has a perimeter of 16 units, what is its area?",
        answer: "b) 16 sq. units",
        choices: ["a) 8 sq. units", "b) 16 sq. units", "c) 24 sq. units", "d) 32 sq. units"]
      },
      {
        question: "If a hexagon can be split into six congruent triangles with an area of 6 sq. units each, what is the total area of the hexagon?",
        answer: "b) 36 sq. units",
        choices: ["a) 12 sq. units", "b) 36 sq. units", "c) 72 sq. units", "d) 108 sq. units"]
      },
      {
        question: "A rectangular prism has a height of 5 units and a base area of 4 sq. units. What is its volume?",
        answer: "a) 20 cu. units",
        choices: ["a) 20 cu. units", "b) 5 cu. units", "c) 2 cu. units", "d) 8 cu. units"]
      },
      {
        question: "What is the volume of a right rectangular prism with a length of 2 units, a width of 3 units, and a height of 4 units?",
        answer: "d) 24 cu. units",
        choices: ["a) 6 cu. units", "b) 12 cu. units", "c) 18 cu. units", "d) 24 cu. units"]
      },
      {
        question: "Four vertices of a quadrilateral have the same y-coordinate. What type of shape does this describe?",
        answer: "a) Trapezoid",
        choices: ["a) Trapezoid", "b) Parallelogram", "c) Rhombus", "d) Rectangle"]
      },
      {
        question: "If a cube has a surface area of 54 sq. units, what is the area of one of its faces?",
        answer: "b) 9 sq. units",
        choices: ["a) 6 sq. units", "b) 9 sq. units", "c) 18 sq. units", "d) 27 sq. units"]
      },
      {
        question: "A triangle has a base that is twice its height. If the base is 8 units, what is the area of the triangle?",
        answer: "a) 16 sq. units",
        choices: ["a) 16 sq. units", "b) 32 sq. units", "c) 4 sq. units", "d) 8 sq. units"]
      },
      {
        question: "A parallelogram is divided into 2 triangles of equal area. If one triangle has an area of 12 sq. units, what is the total area of the parallelogram?",
        answer: "b) 24 sq. units",
        choices: ["a) 6 sq. units", "b) 24 sq. units", "c) 36 sq. units", "d) 48 sq. units"]
      },
      {
        question: "A rectangular box has a base that's twice as long as it is wide. If its width is 3 units, height is 2 units, and length is 6 units, what's the volume of the box?",
        answer: "c) 36 cu. units",
        choices: ["a) 6 cu. units", "b) 30 cu. units", "c) 36 cu. units", "d) 72 cu. units"]
      },
      {
        question: "A trapezoid has two parallel sides measuring 4 units and 6 units. If the height of the trapezoid is 3 units, what is its area?",
        answer: "b) 15 sq. units",
        choices: ["a) 12 sq. units", "b) 15 sq. units", "c) 16 sq. units", "d) 18 sq. units"]
      },
      {
        question: "A net of a triangular prism consists of two congruent triangles and three congruent rectangles. If the triangle has an area of 5 sq. units and each rectangle has an area of 4 sq. units, what is the surface area of the prism?",
        answer: "d) 31 sq. units",
        choices: ["a) 13 sq. units", "b) 17 sq. units", "c) 25 sq. units", "d) 31 sq. units"]
      },
      {
        question: "A large square is divided into four smaller congruent squares. If one of the smaller squares has an area of 9 sq. units, what is the area of the large square?",
        answer: "d) 36 sq. units",
        choices: ["a) 6 sq. units", "b) 9 sq. units", "c) 18 sq. units", "d) 36 sq. units"]
      },
      {
        question: "A cylinder has a radius of 2 units and a height of 5 units. Using the formula V = πr^2h, what is the volume of the cylinder? (Use 3.14 for π)",
        answer: "d) 62.8 cu. units",
        choices: ["a) 6.28 cu. units", "b) 12.56 cu. units", "c) 37.68 cu. units", "d) 62.8 cu. units"]
      }
    ];

    let currentQuestionIndex = 0;

    function displayNextQuestion() {
      const questionObject = questionsDatabase[currentQuestionIndex];
      document.getElementById('question-text').innerText = questionObject.question;

      const answerOptionsContainer = document.getElementById('answer-options-container');
      answerOptionsContainer.innerHTML = '';
      for (let choice of questionObject.choices) {
        const choiceButton = document.createElement('button');
        choiceButton.classList.add('choice-button');
        choiceButton.innerText = choice;
        choiceButton.onclick = () => {
          checkAnswer(choice, questionObject.answer);
        };
        answerOptionsContainer.appendChild(choiceButton);
      }
    }

    function checkAnswer(userAnswer, correctAnswer) {
      if (userAnswer === correctAnswer) {
        currentQuestionIndex++;
        if (currentQuestionIndex < questionsDatabase.length) {
          displayNextQuestion();
        } else {
          alert('Congratulations! You have completed all the questions.');
        }
      } else {
        alert('Incorrect Answer. Try Again!');
      }
    }

    displayNextQuestion();

  </script>
</body>

</html>

U5 

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Numera - Challenge Yourself</title>
  <style>
    body {
      font-family: 'Georgia', serif;
      margin: 0;
      padding: 0;
      color: #000033;
      background-color: white;
    }

    .question-container {
      padding: 40px;
      text-align: center;
    }

    .question-box {
      border: 2px solid #000033;
      padding: 20px;
      border-radius: 15px;
      margin: 20px 0;
    }

    .answer-input {
      padding: 10px;
      width: 50%;
      border-radius: 15px;
      border: 2px solid #000033;
      font-size: 1rem;
    }

    .submit-button {
      padding: 10px 20px;
      border-radius: 15px;
      background-color: white;
      color: #000033;
      border: 2px solid #000033;
      cursor: pointer;
    }

    .choices-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    .choice-button {
      padding: 10px 20px;
      border-radius: 15px;
      background-color: white;
      color: #000033;
      border: 2px solid #000033;
      cursor: pointer;
      margin: 10px 0;
    }
  </style>
</head>

<body>
  <div class="question-container">
    <div class="question-box">
      <h3>Question:</h3>
      <p id="question-text">Loading question...</p>
      <div id="answer-options-container"></div>
      <button class="submit-button" onclick="checkAnswer()">Submit</button>
    </div>
  </div>

  <script>
    const questionsDatabase = [
      {
        question: "What is the area of a circle with a radius of 7 units? (Use 3.14 for π and round the answer to the nearest hundredth.)",
        answer: "d) 153.94 sq. units",
        choices: ["a) 43.96 sq. units", "b) 107.78 sq. units", "c) 130.68 sq. units", "d) 153.94 sq. units"]
      },
      {
        question: "What is the sum of the exterior angles in a triangle?",
        answer: "a) 360 degrees",
        choices: ["a) 360 degrees", "b) 180 degrees", "c) 120 degrees", "d) 90 degrees"]
      },
      {
        question: "What is the area of a triangle with a base of 5 units and a height of 8 units?",
        answer: "a) 20 sq. units",
        choices: ["a) 20 sq. units", "b) 40 sq. units", "c) 80 sq. units", "d) 160 sq. units"]
      },
      {
        question: "What is the average of 2, 5, 7, and 10?",
        answer: "c) 6",
        choices: ["a) 5", "b) 7", "c) 6", "d) 24"]
      },
      {
        question: "What is the value of the digit 6 in the number 4,568?",
        answer: "a) 6,000",
        choices: ["a) 6,000", "b) 600", "c) 60", "d) 6"]
      },
      {
        question: "What is the area of a rectangle with a length of 12 units and a width of 5 units?",
        answer: "d) 60 sq. units",
        choices: ["a) 7 sq. units", "b) 17 sq. units", "c) 29 sq. units", "d) 60 sq. units"]
      },
      {
        question: "What is the value of y in the equation y - 7 = -4?",
        answer: "c) 3",
        choices: ["a) 11", "b) 10", "c) 3", "d) -11"]
      },
      {
        question: "What is the midpoint of the line segment that connects the points (-3, 1) and (5, 7)?",
        answer: "a) (1, 4)",
        choices: ["a) (1, 4)", "b) (4, 1)", "c) (-1, -4)", "d) (-4, -1)"]
      },
      {
        question: "Which question expects different answers from different people?",
        answer: "d) How many books do students in the class read monthly?",
        choices: ["a) What is your name?", "b) How old are you?", "c) What day is today?", "d) How many books do students in the class read monthly?"]
      },
      {
        question: "Which term describes the most common number in a data set?",
        answer: "b) Mode",
        choices: ["a) Range", "b) Mode", "c) Median", "d) Mean"]
      },
      {
        question: "What is the term for the middle number in a sorted data set?",
        answer: "c) Median",
        choices: ["a) Mean", "b) Range", "c) Median", "d) Mode"]
      },
      {
        question: "Which number tells you the average of a data set?",
        answer: "d) Mean",
        choices: ["a) Median", "b) Mode", "c) Range", "d) Mean"]
      },
      {
        question: "What should you report first about a data set?",
        answer: "b) The total count of numbers",
        choices: ["a) The highest value", "b) The total count of numbers", "c) The shape of the data", "d) The lowest value"]
      },
      {
        question: "If studying student heights, what are you investigating?",
        answer: "c) Height",
        choices: ["a) Age", "b) Weight", "c) Height", "d) Hair color"]
      },
      {
        question: "Which tells you how spread apart the numbers in a data set are?",
        answer: "c) Range",
        choices: ["a) Median", "b) Mode", "c) Range", "d) Mean"]
      },
      {
        question: "If most students score 80-90 on a test, but one scored 55, that 55 is called:",
        answer: "c) A unique score",
        choices: ["a) Median", "b) Mode", "c) A unique score", "d) Average"]
      },
      {
        question: "If there are a few very high test scores, which average is least affected?",
        answer: "b) Median",
        choices: ["a) Mean", "b) Median", "c) Mode", "d) Range"]
      },
      {
        question: "In which graph are numbers grouped into sections?",
        answer: "d) Histogram",
        choices: ["a) Pie chart", "b) Line graph", "c) Bar graph", "d) Histogram"]
      },
      {
        question: "If you measure how much water you drink, what unit might you use?",
        answer: "b) Liters",
        choices: ["a) Feet", "b) Liters", "c) Pounds", "d) Minutes"]
      },
      {
        question: "What does a box plot show?",
        answer: "c) Middle 50% of scores",
        choices: ["a) Average score", "b) Most common score", "c) Middle 50% of scores", "d) Highest score"]
      },
      {
        question: "When talking about test scores, saying they're from a math test is giving:",
        answer: "d) The test type",
        choices: ["a) The subject", "b) The date", "c) The student names", "d) The test type"]
      },
      {
        question: "Why is it important to say how you got your data?",
        answer: "b) To show it's trustworthy",
        choices: ["a) To make it sound fancy", "b) To show it's trustworthy", "c) To make it look longer", "d) To fill space in a report"]
      },
      {
        question: "If you ask students how many pets they have, why might answers vary?",
        answer: "b) Some might not remember.",
        choices: ["a) All students have the same number of pets.", "b) Some might not remember.", "c) It's a statistical question.", "d) Pets are hard to count."]
      }
    ];

    let currentQuestionIndex = 0;

    function displayNextQuestion() {
      const questionObject = questionsDatabase[currentQuestionIndex];
      document.getElementById('question-text').innerText = questionObject.question;

      const answerOptionsContainer = document.getElementById('answer-options-container');
      answerOptionsContainer.innerHTML = '';
      for (let choice of questionObject.choices) {
        const choiceButton = document.createElement('button');
        choiceButton.classList.add('choice-button');
        choiceButton.innerText = choice;
        choiceButton.onclick = () => {
          checkAnswer(choice, questionObject.answer);
        };
        answerOptionsContainer.appendChild(choiceButton);
      }
    }

    function checkAnswer(userAnswer, correctAnswer) {
      if (userAnswer === correctAnswer || parseInt(userAnswer) === parseInt(correctAnswer)) {
        currentQuestionIndex++;
        if (currentQuestionIndex < questionsDatabase.length) {
          displayNextQuestion();
        } else {
          alert('Congratulations! You have completed all the questions.');
        }
      } else {
        alert('Incorrect Answer. Try Again!');
      }
    }

    displayNextQuestion();
  </script>
</body>

</html>


## GRADE 1 Questions

	

U1 Cambridge
 
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Numera - Challenge Yourself</title>
  <style>
    body {
      font-family: "Georgia", serif;
      margin: 0;
      padding: 0;
      color: #000033;
      background-color: white;
    }

    .header {
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: white;
      color: #000033;
      padding: 10px;
    }

    .header h1 {
      margin: 0;
    }

    .question-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      margin: 40px 0;
    }

    .question-box {
      border: 2px solid #000033;
      padding: 20px;
      border-radius: 15px;
      margin: 0 20px;
      width: 80%;
      max-width: 800px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .question-label {
      font-size: 24px;
    }

    .question-content {
      font-size: 20px;
      margin-top: 10px;
    }

    .answer-option-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 20px;
    }

    .answer-option {
      padding: 10px;
      border-radius: 15px;
      margin: 5px;
      width: 150px;
      height: 50px;
      background-color: #eeeeee;
      color: #000033;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
    }

    .answer-option:hover {
      background-color: #cccccc;
    }

    .true-false-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      margin-top: 20px;
    }

    .true-false-option-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 0 10px;
    }

    .true-false-option {
      padding: 10px;
      border-radius: 15px;
      margin: 5px auto;
      width: 200px;
      height: 50px;
      background-color: #eeeeee;
      color: #000033;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
    }

    .true-false-option:hover {
      background-color: #cccccc;
    }

    .answer-option-container:after {
      content: '';
      flex: 1 0 150px;
    }

    .true-false-label {
      margin-top: 5px;
    }

    .footer {
      background-color: white;
      color: #000033;
      padding: 10px;
      text-align: center;
      position: absolute;
      bottom: 0;
      width: 100%;
    }

    .footer__content {
      margin: 0;
    }
  </style>
</head>

<body>
  <header class="header" style="background-color: white;">
    <h1 style="color: #000033;">Numera</h1>
  </header>
  <div class="question-container">
    <div class="question-box">
      <h3 id="question-heading"><span class="question-number">1. </span></h3>
      <p id="question-text">Loading question...</p>
      <div id="answer-input"></div>
    </div>
  </div>
  <footer class="footer" style="background-color: white;">
    <p class="footer__content" style="color: #000033;">Numera, Inc &copy; 2023 | Established in MMXXIII</p>
  </footer>
  <script>
    const questionsDatabase = [
      {
        question: "What is 2 + 3?",
        answer: "5",
        options: ["3", "4", "5", "6"],
        type: "MC",
      },
      {
        question: "What is 6 + 4?",
        answer: "10",
        options: ["8", "10", "12", "14"],
        type: "MC",
      },
      {
        question: "What is 7 + 1?",
        answer: "8",
        options: ["7", "8", "9", "10"],
        type: "MC",
      },
      {
        question: "What is 9 + 2?",
        answer: "11",
        options: ["9", "11", "13", "15"],
        type: "MC",
      },
      {
        question: "What is 14 - 5?",
        answer: "9",
        options: ["7", "8", "9", "10"],
        type: "MC",
      },
      {
        question: "What is 18 - 2?",
        answer: "16",
        options: ["14", "16", "18", "20"],
        type: "MC",
      },
      {
        question: "What is 10 - 4?",
        answer: "6",
        options: ["5", "6", "7", "8"],
        type: "MC",
      },
      {
        question: "What is 6 + 6?",
        answer: "12",
        options: ["9", "10", "11", "12"],
        type: "MC",
      },
      {
        question: "What is 3 + 9?",
        answer: "12",
        options: ["10", "12", "14", "16"],
        type: "MC",
      },
      {
        question: "What is 11 - 5?",
        answer: "6",
        options: ["5", "6", "7", "8"],
        type: "MC",
      },
    ];

    let currentQuestionIndex = 0;

    function shuffleArray(array) {
      for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
      }
      return array;
    }

    function displayNextQuestion() {
      const questionObject = questionsDatabase[currentQuestionIndex];
      document.getElementById("question-heading").innerHTML = `<h3 class="question-number">${currentQuestionIndex + 1}. </h3>`;
      document.getElementById("question-text").innerText = questionObject.question;
      if (questionObject.type === "MC") {
        const shuffledOptions = shuffleArray([...questionObject.options]);
        let options = "";
        for (let option of shuffledOptions) {
          options += `<button class="answer-option" type="button" value="${option}">${option}</button>`;
        }
        document.getElementById("answer-input").innerHTML = `<div class="answer-option-container">${options}</div>`;
        const answerOptions = document.querySelectorAll('.answer-option');
        answerOptions.forEach((option) => {
          option.addEventListener('click', () => {
            checkAnswer(option.value);
          });
        });
      }
    }

    function checkAnswer(userAnswer) {
      if (userAnswer === questionsDatabase[currentQuestionIndex].answer) {
        currentQuestionIndex++;
        if (currentQuestionIndex < questionsDatabase.length) {
          displayNextQuestion();
        } else {
          document.getElementById("answer-input").innerHTML = `<button class="answer-option" onclick="location.reload()" style="background-color: #000033; color: white;">Congratulations! You completed all the questions! Click here to restart...</button>`;
          document.getElementById("answer-input").parentNode.style.height = "inherit";
        }
      } else {
        alert("Incorrect answer. Please try again.");
      }
    }

    shuffleArray(questionsDatabase);
    displayNextQuestion();
  </script>
</body>

</html>



U2



<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Numera - Challenge Yourself</title>
  <style>
    body {
      font-family: "Georgia", serif;
      margin: 0;
      padding: 0;
      color: #000033;
      background-color: white;
    }

    .header {
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: white;
      color: #000033;
      padding: 10px;
    }

    .header h1 {
      margin: 0;
    }

    .question-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      margin: 40px 0;
    }

    .question-box {
      border: 2px solid #000033;
      padding: 20px;
      border-radius: 15px;
      margin: 0 20px;
      width: 80%;
      max-width: 800px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .question-label {
      font-size: 24px;
    }

    .question-content {
      font-size: 20px;
      margin-top: 10px;
    }

    .answer-option-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 20px;
    }

    .answer-option {
      padding: 10px;
      border-radius: 15px;
      margin: 5px;
      width: 150px;
      height: 50px;
      background-color: #eeeeee;
      color: #000033;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
    }

    .answer-option:hover {
      background-color: #cccccc;
    }

    .true-false-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      margin-top: 20px;
    }

    .true-false-option-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 0 10px;
    }

    .true-false-option {
      padding: 10px;
      border-radius: 15px;
      margin: 5px auto;
      width: 200px;
      height: 50px;
      background-color: #eeeeee;
      color: #000033;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
    }

    .true-false-option:hover {
      background-color: #cccccc;
    }

    .answer-option-container:after {
      content: '';
      flex: 1 0 150px;
    }

    .true-false-label {
      margin-top: 5px;
    }

    .footer {
      background-color: white;
      color: #000033;
      padding: 10px;
      text-align: center;
      position: absolute;
      bottom: 0;
      width: 100%;
    }

    .footer__content {
      margin: 0;
    }
  </style>
</head>

<body>
  <header class="header" style="background-color: white;">
    <h1 style="color: #000033;">Numera</h1>
  </header>
  <div class="question-container">
    <div class="question-box">
      <h3 id="question-heading"><span class="question-number">1. </span></h3>
      <p id="question-text">Loading question...</p>
      <div id="answer-input"></div>
    </div>
  </div>
  <footer class="footer" style="background-color: white;">
    <p class="footer__content" style="color: #000033;">Numera, Inc &copy; 2023 | Established in MMXXIII</p>
  </footer>
  <script>
    const questionsDatabase = [
      
      {
        question: "What is the value of '4' in the number 42?",
        answer: "tens",
        options: ["hundreds", "tens", "ones"],
        type: "MC",
      },
      {
        question: "What is the value of '7' in the number 76?",
        answer: "tens",
        options: ["hundreds", "tens", "ones"],
        type: "MC",
      },
      {
        question: "What is the value of '9' in the number 94?",
        answer: “Tens”,
        options: ["hundreds", "tens", "ones"],
        type: "MC",
      },
      {
        question: "What is the value of '3' in the number 23?",
        answer: "ones",
        options: ["hundreds", "tens", "ones"],
        type: "MC",
      },
      {
        question: "What is the value of '5' in the number 65?",
        answer: “ones”,
        options: ["hundreds", "tens", "ones"],
        type: "MC",
      },
      {
        question: "What is 10 represented as?",
        answer: “Ten ones",
        options: [“Ten ones-10, “Ten tens-100“, “Ten hundreds-1000”, “Ten thousands-10,000”],
        type: "MC",
      },
      {
        question: "What is the value of '6' in the number 67?",
        answer: "ones",
        options: ["hundreds", "tens", "ones"],
        type: "MC",
      },
      {
        question: "What is the value of '8' in the number 89?",
        answer: “tens”,
        options: ["hundreds", "tens", "ones"],
        type: "MC",
      },
      {
        question: "What is 15 represented as?",
        answer: "A bundle of ten ones and five ones",
        options: ["A bundle of ten ones and five ones", "A bundle of ten ones and five tens", "A bundle of ten ones and five hundreds", "A bundle of ten ones and five thousands"],
        type: "MC",
      },
      {
        question: "What is the two-digit number that has 5 tens and 4 ones?",
        answer: "54",
        options: ["36", "45", "54", "63"],
        type: "MC",
      },
      {
        question: "What is the numeral representation of the number in words - seventeen",
        answer: "17",
        options: ["7", "10", "17", "70"],
        type: "MC",
      },
      {
        question: “Twenty-five,
        answer: "25",
        options: ["20", "21", "25", "30"],
        type: "MC",
      },
      {
        question: “Forty-six",
        answer: "46",
        options: ["36", "46", "56", "66"],
        type: "MC",
      },
      {
        question: “Fifty-two",
        answer: "52",
        options: ["25", "42", "52", "62"],
        type: "MC",
      },
      {
        question: "What are the two digits in the number '25' called?",
        answer: "Tens and ones",
        options: ["Hundreds and tens", "Tens and ones", "Ones and thousands", "Tens and thousands"],
        type: "MC",
      },
      {
        question: "What are the two digits in the number '63' called?",
        answer: "Tens and ones",
        options: ["Hundreds and tens", "Tens and ones", "Ones and thousands", "Tens and thousands"],
        type: "MC",
      },
      {
        question: "What are the two digits in the number '88' called?",
        answer: "Tens and ones",
        options: ["Hundreds and tens", "Tens and ones", "Ones and thousands", "Tens and thousands"],
        type: "MC",
      },
      {
        question: "What are the two digits in the number '32' called?",
        answer: "Tens and ones",
        options: ["Hundreds and tens", "Tens and ones", "Ones and thousands", "Tens and thousands"],
        type: "MC",
      },
      {
        question: "What are the two digits in the number '79' called?",
        answer: "Tens and ones",
        options: ["Hundreds and tens", "Tens and ones", "Ones and thousands", "Tens and thousands"],
        type: "MC",
      },
      {
        question: “Smallest to biggest to the number 19?”,
        answer: "ten, eleven, twelve, thirteen ... ninety-nine",
        options: ["ten, twenty, thirty, ... ninety", "eleven, twelve, thirteen, ... ninety-nine", "ten, eleven, twelve, thirteen ... ninety-nine", "twenty, thirty, forty, ... hundred"],
        type: "MC",
      },
    ];

    let currentQuestionIndex = 0;

    function shuffleArray(array) {
      for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
      }
      return array;
    }

    function displayNextQuestion() {
      const questionObject = questionsDatabase[currentQuestionIndex];
      document.getElementById("question-heading").innerHTML = `<h3 class="question-number">${currentQuestionIndex + 1}. </h3>`;
      document.getElementById("question-text").innerText = questionObject.question;
      if (questionObject.type === "MC") {
        const shuffledOptions = shuffleArray([...questionObject.options]);
        let options = "";
        for (let option of shuffledOptions) {
          options += `<button class="answer-option" type="button" value="${option}">${option}</button>`;
        }
        document.getElementById("answer-input").innerHTML = `<div class="answer-option-container">${options}</div>`;
        const answerOptions = document.querySelectorAll('.answer-option');
        answerOptions.forEach((option) => {
          option.addEventListener('click', () => {
            checkAnswer(option.value);
          });
        });
      }
    }

    function checkAnswer(userAnswer) {
      if (userAnswer === questionsDatabase[currentQuestionIndex].answer) {
        currentQuestionIndex++;
        if (currentQuestionIndex < questionsDatabase.length) {
          displayNextQuestion();
        } else {
          document.getElementById("answer-input").innerHTML = `<button class="answer-option" onclick="location.reload()" style="background-color: #000033; color: white;">Congratulations! You completed all the questions! Click here to restart...</button>`;
          document.getElementById("answer-input").parentNode.style.height = "inherit";
        }
      } else {
        alert("Incorrect answer. Please try again.");
      }
    }

    shuffleArray(questionsDatabase);
    displayNextQuestion();
  </script>
</body>

</html>


U3


<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Numera - Challenge Yourself</title>
    <style>
      body {
        font-family: "Georgia", serif;
        margin: 0;
        padding: 0;
        color: #000033;
        background-color: white;
      }

      .header {
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: white;
        color: #000033;
        padding: 10px;
      }

      .header h1 {
        margin: 0;
      }

      .question-container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        margin: 40px 0;
      }

      .question-box {
        border: 2px solid #000033;
        padding: 20px;
        border-radius: 15px;
        margin: 0 20px;
        width: 80%;
        max-width: 800px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
      }

      .question-label {
        font-size: 24px;
      }

      .question-content {
        font-size: 20px;
        margin-top: 10px;
      }

      .answer-option-container {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        margin-top: 20px;
      }

      .answer-option {
        padding: 10px;
        border-radius: 15px;
        margin: 5px;
        width: 150px;
        height: 50px;
        background-color: #eeeeee;
        color: #000033;
        text-align: center;
        cursor: pointer;
        transition: background-color 0.2s ease;
        border: none;
        font-size: 16px;
      }

      .answer-option:hover {
        background-color: #cccccc;
      }

      .true-false-container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        margin-top: 20px;
      }

      .true-false-option-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        margin: 0 10px;
      }

      .true-false-option {
        padding: 10px;
        border-radius: 15px;
        margin: 5px auto;
        width: 200px;
        height: 50px;
        background-color: #eeeeee;
        color: #000033;
        text-align: center;
        cursor: pointer;
        transition: background-color 0.2s ease;
        border: none;
        font-size: 16px;
      }

      .true-false-option:hover {
        background-color: #cccccc;
      }

      .answer-option-container:after {
        content: "";
        flex: 1 0 150px;
      }

      .true-false-label {
        margin-top: 5px;
      }

      .footer {
        background-color: white;
        color: #000033;
        padding: 10px;
        text-align: center;
        position: absolute;
        bottom: 0;
        width: 100%;
      }

      .footer__content {
        margin: 0;
      }
    </style>
  </head>

  <body>
    <header class="header" style="background-color: white;">
      <h1 style="color: #000033;">Numera</h1>
    </header>
    <div class="question-container">
      <div class="question-box">
        <h3 id="question-heading"><span class="question-number">1. </span></h3>
        <p id="question-text">Loading question...</p>
        <div id="answer-input"></div>
      </div>
    </div>
    <footer class="footer" style="background-color: white;">
      <p class="footer__content" style="color: #000033;">Numera, Inc &copy; 2023 | Established in MMXXIII</p>
    </footer>
    <script>
      const questionsDatabase = [
        {
          question: "Sandra has 3 toy cars. James has 2 toy cars. Who has more toy cars?",
          answer: "Sandra",
          options: ["Sandra", "James"],
          type: "MC",
        },
        {
          question: "How many crayons are in a box of 8 crayons?",
          answer: "8",
          options: ["4", "8", "12"],
          type: "MC",
        },
        {
          question: "If you have 5 toys and you give away 2, how many toys do you have left?",
          answer: "3",
          options: ["3", "4", "5"],
          type: "MC",
        },
        {
          question: "What time is it if the big hand is on 12 and the little hand is on 6?",
          answer: "6",
          options: ["4", "6", "10"],
          type: "MC",
        },
        {
          question: "If it's 2 o'clock now, what time will it be in ONE hour?",
          answer: "3",
          options: ["2", "3", "4"],
          type: "MC",
        },
        {
          question: "Which coin is worth more: a nickel or a penny? Nickel is 5 cents, and , Penny is 1 cent.”
          answer: "Nickel",
          options: ["Nickel", "Penny"],
          type: "MC",
        },
        {
          question: "How much money is 2 dimes and 3 pennies. Dime = 10. Pennies = 1?”,
          answer: "23",
          options: ["13", "23", "33"],
          type: "MC",
        },
        {
          question: "If a toy costs 25 cents and you have 50 cents, how much change will you get?",
          answer: "25",
          options: ["10", "15", "25"],
          type: "MC",
        },
      ];

      let currentQuestionIndex = 0;

      function shuffleArray(array) {
        for (let i = array.length - 1; i > 0; i--) {
          const j = Math.floor(Math.random() * (i + 1));
          [array[i], array[j]] = [array[j], array[i]];
        }
        return array;
      }

      function displayNextQuestion() {
        const questionObject = questionsDatabase[currentQuestionIndex];
        document.getElementById("question-heading").innerHTML = `<h3 class="question-number">${currentQuestionIndex + 1}. </h3>`;
        document.getElementById("question-text").innerText = questionObject.question;
        if (questionObject.type === "MC") {
          const shuffledOptions = shuffleArray([...questionObject.options]);
          let options = "";
          for (let option of shuffledOptions) {
            options += `<button class="answer-option" type="button" value="${option}">${option}</button>`;
          }
          document.getElementById("answer-input").innerHTML = `<div class="answer-option-container">${options}</div>`;
          const answerOptions = document.querySelectorAll(".answer-option");
          answerOptions.forEach((option) => {
            option.addEventListener("click", () => {
              checkAnswer(option.value);
            });
          });
        }
      }

      function checkAnswer(userAnswer) {
        if (userAnswer === questionsDatabase[currentQuestionIndex].answer) {
          currentQuestionIndex++;
          if (currentQuestionIndex < questionsDatabase.length) {
            displayNextQuestion();
          } else {
            document.getElementById(
              "answer-input"
            ).innerHTML = `<button class="answer-option" onclick="location.reload()" style="background-color: #000033; color: white;">Congratulations! You completed all the questions! Click here to restart...</button>`;
            document.getElementById("answer-input").parentNode.style.height = "inherit";
          }
        } else {
          alert("Incorrect answer. Please try again.");
        }
      }

      shuffleArray(questionsDatabase);
      displayNextQuestion();
    </script>
  </body>
</html>


U4



<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Numera - Challenge Yourself</title>
  <style>
    body {
      font-family: "Georgia", serif;
      margin: 0;
      padding: 0;
      color: #000033;
      background-color: white;
    }

    .header {
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: white;
      color: #000033;
      padding: 10px;
    }

    .header h1 {
      margin: 0;
    }

    .question-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      margin: 40px 0;
    }

    .question-box {
      border: 2px solid #000033;
      padding: 20px;
      border-radius: 15px;
      margin: 0 20px;
      width: 80%;
      max-width: 800px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .question-label {
      font-size: 24px;
    }

    .question-content {
      font-size: 20px;
      margin-top: 10px;
    }

    .answer-option-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 20px;
    }

    .answer-option {
      padding: 10px;
      border-radius: 15px;
      margin: 5px;
      width: 150px;
      height: 50px;
      background-color: #eeeeee;
      color: #000033;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
    }

    .answer-option:hover {
      background-color: #cccccc;
    }

    .true-false-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      margin-top: 20px;
    }

    .true-false-option-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 0 10px;
    }

    .true-false-option {
      padding: 10px;
      border-radius: 15px;
      margin: 5px auto;
      width: 200px;
      height: 50px;
      background-color: #eeeeee;
      color: #000033;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
    }

    .true-false-option:hover {
      background-color: #cccccc;
    }

    .answer-option-container:after {
      content: '';
      flex: 1 0 150px;
    }

    .true-false-label {
      margin-top: 5px;
    }

    .footer {
      background-color: white;
      color: #000033;
      padding: 10px;
      text-align: center;
      position: absolute;
      bottom: 0;
      width: 100%;
    }

    .footer__content {
      margin: 0;
    }
  </style>
</head>

<body>
  <header class="header" style="background-color: white;">
    <h1 style="color: #000033;">Numera</h1>
  </header>
  <div class="question-container">
    <div class="question-box">
      <h3 id="question-heading"><span class="question-number">1. </span></h3>
      <p id="question-text">Loading question...</p>
      <div id="answer-input"></div>
    </div>
  </div>
  <footer class="footer" style="background-color: white;">
    <p class="footer__content" style="color: #000033;">Numera, Inc &copy; 2023 | Established in MMXXIII</p>
  </footer>
  <script>
    const questionsDatabase = [
      {
        question: “Shape with three sides?”,
        answer: "c",
        options: ["a) Circle", "b) Square", "c) Triangle", "d) Rectangle"],
        type: "MC",
      },
      {
        question: "What are flat shapes?",
        answer: "d",
        options: ["a) Circles", "b) Triangles", "c) Squares", "d) All of the them”],
        type: "MC",
      },
      {
        question: "How many sides does a rectangle have?",
        answer: "c",
        options: ["a) 2", "b) 3", "c) 4", "d) 5"],
        type: "MC",
      },
      {
        question: "How many corners does a triangle have?",
        answer: "c",
        options: ["a) 1", "b) 2", "c) 3", "d) 4"],
        type: "MC",
      },
      {
        question: "What is a circle?”,
        answer: "c",
        options: ["a) Three sides and three angles", "b) Four sides and four angles", "c) Has a curved edge and no corners", "d) Has equal sides and equal angles"],
        type: "MC",
      },
      {
        question: "What's the difference between a half and quarter slice of pizza?",
        answer: "c",
        options: ["a) More cheese", "b) Less pizza", "c) Size", "d) All of the above"],
        type: "MC",
      },
      {
        question: "Can two squares make a rectangle?",
        answer: "a",
        options: ["a) Yes", "b) No"],
        type: "MC",
      },
      {
     
      {
        question: "How many sides does a die have?",
        answer: "b",
        options: ["a) 4", "b) 6", "c) 8", "d) 10"],
        type: "MC",
      },
   ];

    let currentQuestionIndex = 0;

    function shuffleArray(array) {
      for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
      }
      return array;
    }

    function displayNextQuestion() {
      const questionObject = questionsDatabase[currentQuestionIndex];
      document.getElementById("question-heading").innerHTML = `<h3 class="question-number">${currentQuestionIndex + 1}. </h3>`;
      document.getElementById("question-text").innerText = questionObject.question;
      if (questionObject.type === "MC") {
        const shuffledOptions = shuffleArray([...questionObject.options]);
        let options = "";
        for (let option of shuffledOptions) {
          options += `<button class="answer-option" type="button" value="${option.substring(0, 1)}">${option}</button>`;
        }
        document.getElementById("answer-input").innerHTML = `<div class="answer-option-container">${options}</div>`;
        const answerOptions = document.querySelectorAll('.answer-option');
        answerOptions.forEach((option) => {
          option.addEventListener('click', () => {
            checkAnswer(option.value);
          });
        });
      } else if (questionObject.type === "TF") {
        document.getElementById("answer-input").innerHTML = `<div class="true-false-container"><div class="true-false-option-container"><button class="true-false-option" type="button" value="true">True</button><p class="true-false-label">True</p></div><div class="true-false-option-container"><button class="true-false-option" type="button" value="false">False</button><p class="true-false-label">False</p></div></div>`;
        const trueFalseOptions = document.querySelectorAll('.true-false-option');
        trueFalseOptions.forEach((option) => {
          option.addEventListener('click', () => {
            checkAnswer(String(option.value));
          });
        });
      }
    }

    function checkAnswer(userAnswer) {
      if (userAnswer === questionsDatabase[currentQuestionIndex].answer) {
        currentQuestionIndex++;
        if (currentQuestionIndex < questionsDatabase.length) {
          displayNextQuestion();
        } else {
          document.getElementById("answer-input").innerHTML = `<button class="answer-option" onclick="location.reload()" style="background-color: #000033; color: white;">Congratulations! You completed all the questions! Click here to restart...</button>`;
          document.getElementById("answer-input").parentNode.style.height = "inherit";
        }
      } else {
        alert("Incorrect answer. Please try again.");
      }
    }

    shuffleArray(questionsDatabase);
    displayNextQuestion();
  </script>
</body>

</html>

## Grade 2 Questions Cambridge  


U1 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Operations and Algebraic Thinking Quiz for Grade 2</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-radio {
            margin: 10px;
            display: none;
        }
        .answer-label {
            display: inline-block;
            border-radius: 25px;
            padding: 10px 20px;
            color: #000033;
            border: 2px solid #000033;
            font-size: 1rem;
            margin: 10px;
            cursor: pointer;
        }
        .answer-label:hover {
            background-color: #000033;
            color: white;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 25px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin-top: 20px;
        }
        .submit-button:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <form id="answer-form">
            </form>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                category: "Operations and Algebraic Thinking",
                question: "Which operation would you use to solve this problem: 'Samantha has 13 apples and she gave 4 to her friend. How many apples does Samantha have now?'",
                answers: ["Addition", "Subtraction", "Multiplication", "Division"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is the sum of 7 and 8?",
                answers: ["14", "15 ", "16", "17"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "If a rectangle has 4 rows of 6 squares each, how many squares are there in total?",
                answers: ["10", "20", "24", "40"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "Find the missing number: 7 + __ = 14",
                answers: ["6", "8", "10", "14"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "Julie has 9 stickers and she gets 4 more from her friend. How many stickers does she have in total?",
                answers: ["11", "12", "13", "14"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "Which operation would you use to solve this problem: 'Ben has 15 toy cars. He put 3 cars in each of his 5 boxes. How many cars are there in total?'",
                answers: ["Addition", "Subtraction", "Multiplication (Correct)", "Division"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is the difference between 14 and 7?",
                answers: ["6", "7", "8", "9"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "If a rectangle has 3 rows of 5 squares each, how many squares are there in total?",
                answers: ["8", "12", "15", "20"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "Find the missing number: 17 - __ = 8",
                answers: ["6", "8", "9", "10"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "Charlotte has 12 crayons and she divides them equally among 4 friends. How many crayons will each friend get?",
                answers: ["2", "3", "4", "5"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            // Remove previous answer choices
            const oldAnswerChoices = document.querySelectorAll('.answer-label');
            oldAnswerChoices.forEach(function(choice) {
                choice.remove();
            });

            // Create and append new label elements for each answer choice
            const answerForm = document.getElementById('answer-form');
            questionObject.answers.forEach(function(choice, index) {
                const inputId = `answer-${index}`;
                const label = document.createElement('label');
                label.setAttribute('for', inputId);
                label.classList.add('answer-label');
                label.innerText = choice;
                const input = document.createElement('input');
                input.setAttribute('type', 'radio');
                input.setAttribute('name', 'answer');
                input.setAttribute('id', inputId);
                input.setAttribute('value', choice);
                input.classList.add('answer-radio');
                answerForm.append(input, label);
            });
        }

        function checkAnswer() {
            const userAnswer = document.querySelector('input[name="answer"]:checked').value;
            const correctAnswer = questionsDatabase[currentQuestionIndex].answers[1];
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
            document.querySelector('input[name="answer"]:checked').checked = false;
        }

        displayNextQuestion();
    </script>
</body>
</html>



U2 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Number and Operations in Base Ten Quiz for Grade 2</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-radio {
            margin: 10px;
            display: none;
        }
        .answer-label {
            display: inline-block;
            border-radius: 25px;
            padding: 10px 20px;
            color: #000033;
            border: 2px solid #000033;
            font-size: 1rem;
            margin: 10px;
            cursor: pointer;
        }
        .answer-label:hover {
            background-color: #000033;
            color: white;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 25px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin-top: 20px;
        }
        .submit-button:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <form id="answer-form">
            </form>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                category: "Number and Operations in Base Ten",
                question: "What number is 3 tens and 5 ones?",
                answers: ["35", "53", "30", "None of the above"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What number comes before 87?",
                answers: ["86", "88", "89", "None of the above"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "Which digit is in the tens place in the number 254?",
                answers: ["2", "5", "4", "None of the above"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What number is represented by the base-ten blocks below?" + "<br>" + "[Fourteen ones blocks]",
                answers: ["14", "1", "4", "None of the above"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "Which number is larger: 75 or 57?",
                answers: ["75", "57", "They are equal", "None of the above"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the expanded form of the number 390?",
                answers: ["300 + 9", "30 + 9", "390", "3 + 9"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "How many ones are in the number 305?",
                answers: ["5", "3", "0", "None of the above"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What number comes next in the pattern 2, 12, 22, 32...?",
                answers: ["40", "42", "35", "36"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What number is 5 tens and 2 ones?",
                answers: ["52", "25", "50", "None of the above"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the value of the digit 6 in the number 326?",
                answers: ["60", "600", "6", "None of the above"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "Which strategy can be used to add 44 + 23?",
                answers: ["Counting on from the larger number", "Counting back from the smaller number", "Adding the ones digits first, then the tens digits", "Subtracting the smaller number from the larger number"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What number is represented by the base-ten blocks below?" + "<br>" + "[Two hundred blocks]",
                answers: ["200", "20", "2", "None of the above"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "Which digit is in the ones place in the number 839?",
                answers: ["9", "8", "3", "None of the above"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the value of the digit 2 in the number 432?",
                answers: ["20", "2", "200", "None of the above"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "Which number is larger: 86 or 68?",
                answers: ["86", "68", "They are equal", "None of the above"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerHTML = questionObject.question;

            // Remove previous answer choices
            const oldAnswerChoices = document.querySelectorAll('.answer-label');
            oldAnswerChoices.forEach(function(choice) {
                choice.remove();
            });

            // Create and append new label elements for each answer choice
            const answerForm = document.getElementById('answer-form');
            questionObject.answers.forEach(function(choice, index) {
                const inputId = `answer-${index}`;
                const label = document.createElement('label');
                label.setAttribute('for', inputId);
                label.classList.add('answer-label');
                label.innerHTML = choice;
                const input = document.createElement('input');
                input.setAttribute('type', 'radio');
                input.setAttribute('name', 'answer');
                input.setAttribute('id', inputId);
                input.setAttribute('value', choice);
                input.classList.add('answer-radio');
                answerForm.append(input, label);
            });
        }

        function checkAnswer() {
            const userAnswer = document.querySelector('input[name="answer"]:checked').value;
            const correctAnswer = questionsDatabase[currentQuestionIndex].answers[0];
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
            document.querySelector('input[name="answer"]:checked').checked = false;
        }

        displayNextQuestion();
    </script>
</body>
</html>



U3 



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Measurement and Data Quiz for Grade 2</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-radio {
            margin: 10px;
            display: none;
        }
        .answer-label {
            display: inline-block;
            border-radius: 25px;
            padding: 10px 20px;
            color: #000033;
            border: 2px solid #000033;
            font-size: 1rem;
            margin: 10px;
            cursor: pointer;
        }
        .answer-label:hover {
            background-color: #000033;
            color: white;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 25px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin-top: 20px;
        }
        .submit-button:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <form id="answer-form">
            </form>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                category: "Measurement and Data",
                question: "Which tool is used to measure length to the nearest inch?",
                answers: ["Ruler (Correct)", "Measuring tape", "Meter stick", "None of the above"]
            },
            {
                category: "Measurement and Data",
                question: "How many feet are in a yard?",
                answers: ["2", "3 (Correct)", "4", "None of the above"]
            },
            {
                category: "Measurement and Data",
                question: "Which statement is correct?",
                answers: ["An inch is shorter than a foot", "A yard is longer than a meter (Correct)", "A centimeter is longer than a kilometer", "None of the above"]
            },
            {
                category: "Measurement and Data",
                question: "What unit of length is best used to measure the distance between two cities?",
                answers: ["Kilometers (Correct)", "Meters", "Inches", "Feet"]
            },
            {
                category: "Measurement and Data",
                question: "Which statement is true?",
                answers: ["A centimeter is longer than a millimeter (Correct)", "A meter is shorter than a yard", "An inch is equal to 2.54 centimeters", "None of the above"]
            },
            {
                category: "Measurement and Data",
                question: "How many centimeters are in a meter?",
                answers: ["10", "100 (Correct)", "1000", "None of the above"]
            },
            {
                category: "Measurement and Data",
                question: "Which tool is best used to measure a curved object?",
                answers: ["Ruler", "Measuring tape (Correct)", "Meter stick", "None of the above"]
            },
            {
                category: "Measurement and Data",
                question: "What is the standard unit of length in the customary system?",
                answers: ["Centimeters", "Inches (Correct)", "Meters", "Yards"]
            },
            {
                category: "Measurement and Data",
                question: "A marathon is 26.2 miles long. How many kilometers is that?",
                answers: ["16.34", "42.16 (Correct)", "67.06", "None of the above"]
            },
            {
                category: "Measurement and Data",
                question: "If a piece of string measures 8 inches and you cut off 3 inches, how long is the string now?",
                answers: ["6 inches", "5 inches (Correct)", "11 inches", "None of the above"]
            },
            {
                category: "Measurement and Data",
                question: "Which unit of measurement is the best for measuring the length of a classroom?",
                answers: ["Feet", "Meters (Correct)", "Inches", "Centimeters"]
            },
            {
                category: "Measurement and Data",
                question: "You measured the length of a table with an inch ruler and a foot ruler. How are the measurements different?",
                answers: ["They are the same", "The inch ruler is longer", "The foot ruler is shorter", "The foot ruler is longer (Correct)"]
            },
            {
                category: "Measurement and Data",
                question: "If you need to measure the height of a tree, which tool is the best to use?",
                answers: ["Inch ruler", "Foot ruler", "Measuring tape", "Yardstick (Correct)"]
            },
            {
                category: "Measurement and Data",
                question: "What measurement would you use to describe the length of your fingernail?",
                answers: ["Feet", "Inches", "Centimeters (Correct)", "Meters"]
            },
            {
                category: "Measurement and Data",
                question: "Which of the following units of measurement is the smallest?",
                answers: ["Yard", "Inch", "Foot", "Centimeter (Correct)"]
            },
            {
                category: "Measurement and Data",
                question: "Which unit of measurement is best used to describe the distance between two countries?",
                answers: ["Inches", "Feet", "Meters", "Kilometers (Correct)"]
            },
            {
                category: "Measurement and Data",
                question: "What is the smallest unit of time?",
                answers: ["Hour", "Minute", "Second (Correct)", "Day"]
            },
            {
                category: "Measurement and Data",
                question: "How many minutes are in an hour?",
                answers: ["10", "60 (Correct)", "100", "None of the above"]
            },
            {
                category: "Measurement and Data",
                question: "Which unit of time is used to describe a period of 24 hours?",
                answers: ["Minute", "Hour", "Day (Correct)", "Week"]
            },
            {
                category: "Measurement and Data",
                question: "What is the total number of minutes in 2 hours and 20 minutes?",
                answers: ["220", "120", "100 (Correct)", "None of the above"]
            },
            {
                category: "Measurement and Data",
                question: "If a clock shows 3:20 pm, what time will it be in 1 hour and 35 minutes?",
                answers: ["4:45 pm (Correct)", "4:55 pm", "3:55 pm", "3:25 pm"]
            },
            {
                category: "Measurement and Data",
                question: "Which of the following is not a coin?",
                answers: ["Penny (Correct)", "Dime", "Quarter", "Dollar"]
            },
            {
                category: "Measurement and Data",
                question: "If you have 4 quarters and 3 dimes, how many cents do you have?",
                answers: ["35 (Correct)", "40", "45", "50"]
            },
            {
                category: "Measurement and Data",
                question: "Which symbol is used to represent cents?",
                answers: ["$", "€", "¥", "¢ (Correct)"]
            },
            {
                category: "Measurement and Data",
                question: "If you have a dollar bill and 5 dimes, how many cents do you have?",
                answers: ["60", "65 (Correct)", "70", "75"]
            },
            {
                category: "Measurement and Data",
                question: "If you have 2 quarters and 4 pennies, how many cents do you have?",
                answers: ["54", "56", "62 (Correct)", "64"]
            },
            {
                category: "Measurement and Data",
                question: "If you have $3 and 3 quarters, how many dollars do you have?",
                answers: ["$3.75 (Correct)", "$2.75", "$3.25", "$4.00"]
            },
            {
                category: "Measurement and Data",
                question: "Which type of graph uses pictures to represent data?",
                answers: ["Bar Graph", "Line Plot", "Pie Chart", "Pictograph (Correct)"]
            },
            {
                category: "Measurement and Data",
                question: "Which type of graph shows how many of each category there are?",
                answers: ["Bar Graph (Correct)", "Line Plot", "Pie Chart", "Pictograph"]
            },
            {
                category: "Measurement and Data",
                question: "If a bar graph shows how many books each student read, which axis would show the number of books?",
                answers: ["X-axis", "Y-axis", "Z-axis", "None of the above (Correct)"]
            },
            {
                category: "Measurement and Data",
                question: "Which type of graph is used to show how data changes over time?",
                answers: ["Bar Graph", "Line Plot (Correct)", "Pie Chart", "Pictograph"]
            },
            {
                category: "Measurement and Data",
                question: "How many students scored an A on the math test?",
                answers: ["2 (Correct)", "5", "7", "8"]
            },
            {
                category: "Measurement and Data",
                question: "How many more books did Sarah read than Tim?",
                answers: ["2", "3", "4", "5 (Correct)"]
            },
            {
                category: "Measurement and Data",
                question: "If 6 students like pizza, how many like hamburgers?",
                answers: ["2", "3", "4 (Correct)", "5"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            // Remove previous answer choices
            const oldAnswerChoices = document.querySelectorAll('.answer-label');
            oldAnswerChoices.forEach(function(choice) {
                choice.remove();
            });

            // Create and append new label elements for each answer choice
            const answerForm = document.getElementById('answer-form');
            questionObject.answers.forEach(function(choice, index) {
                const inputId = `answer-${index}`;
                const label = document.createElement('label');
                label.setAttribute('for', inputId);
                label.classList.add('answer-label');
                label.innerText = choice;
                const input = document.createElement('input');
                input.setAttribute('type', 'radio');
                input.setAttribute('name', 'answer');
                input.setAttribute('id', inputId);
                input.setAttribute('value', choice);
                input.classList.add('answer-radio');
                answerForm.append(input, label);
            });
        }

        function checkAnswer() {
            const userAnswer = document.querySelector('input[name="answer"]:checked');
            if (userAnswer) {
                const userAnswerValue = userAnswer.value;
                const correctAnswer = questionsDatabase[currentQuestionIndex].answers[0];
                if (userAnswerValue === correctAnswer) {
                    currentQuestionIndex++;
                    if (currentQuestionIndex < questionsDatabase.length) {
                        displayNextQuestion();
                    } else {
                        alert('Congratulations! You have completed all the questions.');
                    }
                } else {
                    alert('Incorrect Answer. Try Again!');
                }
                userAnswer.checked = false;
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>



U4


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Geometry Quiz for Grade 2</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-radio {
            margin: 10px;
            display: none;
        }
        .answer-label {
            display: inline-block;
            border-radius: 25px;
            padding: 10px 20px;
            color: #000033;
            border: 2px solid #000033;
            font-size: 1rem;
            margin: 10px;
            cursor: pointer;
        }
        .answer-label:hover {
            background-color: #000033;
            color: white;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 25px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin-top: 20px;
        }
        .submit-button:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <form id="answer-form">
            </form>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                category: "Geometry",
                question: "Which shape has three sides?",
                answers: ["Triangle (Correct)", "Square", "Rectangle", "Circle"]
            },
            {
                category: "Geometry",
                question: "Which shape has four sides that are the same length and four right angles?",
                answers: ["Square (Correct)", "Rectangle", "Triangle", "Circle"]
            },
            {
                category: "Geometry",
                question: "Which shape has one pair of parallel sides?",
                answers: ["Trapezoid (Correct)", "Square", "Rectangle", "Triangle"]
            },
            {
                category: "Geometry",
                question: "Which shape has two pairs of parallel sides?",
                answers: ["Rectangle (Correct)", "Square", "Rhombus", "Triangle"]
            },
            {
                category: "Geometry",
                question: "If a square is cut into 4 equal parts, what shape are the parts?",
                answers: ["Smaller squares (Correct)", "Rectangles", "Triangles", "Circles"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            // Remove previous answer choices
            const oldAnswerChoices = document.querySelectorAll('.answer-label');
            oldAnswerChoices.forEach(function(choice) {
                choice.remove();
            });

            // Create and append new label elements for each answer choice
            const answerForm = document.getElementById('answer-form');
            questionObject.answers.forEach(function(choice, index) {
                const inputId = `answer-${index}`;
                const label = document.createElement('label');
                label.setAttribute('for', inputId);
                label.classList.add('answer-label');
                label.innerText = choice;
                const input = document.createElement('input');
                input.setAttribute('type', 'radio');
                input.setAttribute('name', 'answer');
                input.setAttribute('id', inputId);
                input.setAttribute('value', choice);
                input.classList.add('answer-radio');
                answerForm.append(input, label);
            });
        }

        function checkAnswer() {
            const userAnswer = document.querySelector('input[name="answer"]:checked');
            if (userAnswer) {
                const userAnswerValue = userAnswer.value;
                const correctAnswer = questionsDatabase[currentQuestionIndex].answers[0];
                if (userAnswerValue === correctAnswer) {
                    currentQuestionIndex++;
                    if (currentQuestionIndex < questionsDatabase.length) {
                        displayNextQuestion();
                    } else {
                        alert('Congratulations! You have completed all the questions.');
                    }
                } else {
                    alert('Incorrect Answer. Try Again!');
                }
                userAnswer.checked = false;
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


      {
                category: "Geometry",
                question: "Which shape is not a quadrilateral?",
                answers: ["Triangle (Correct)", "Square", "Rectangle", "Rhombus"]
            },
            {
                category: "Geometry",
                question: "How many equal faces does a cube have?",
                answers: ["3", "4", "5", "6 (Correct)"]
            },



  "What comes after a thousand?",
            "How many minutes are in an hour?",
            "If an apple costs $2, how much do 3 apples cost?",
            "What number is 10 more than 32?",



## Grade 4 Cambridge 

 Questions 

Unit 1: Operations and Algebraic Thinking

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Operations and Algebraic Thinking Quiz for Grade 4</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-radio {
            margin: 10px;
            display: none;
        }
        .answer-label {
            display: inline-block;
            border-radius: 25px;
            padding: 10px 20px;
            color: #000033;
            border: 2px solid #000033;
            font-size: 1rem;
            margin: 10px;
            cursor: pointer;
        }
        .answer-label:hover {
            background-color: #000033;
            color: white;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 25px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin-top: 20px;
        }
        .submit-button:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <form id="answer-form">
            </form>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                category: "Operations and Algebraic Thinking",
                question: "What is 4 x 7?",
                answers: ["28", "33", "42 (Correct)", "48"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is 3 + 4 x 2?",
                answers: ["14 (Correct)", "20", "10", "24"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "If 7x + 9 = 58, what is the value of x?",
                answers: ["7", "5", "6", "8 (Correct)"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is the difference between 63 and 45?",
                answers: ["18 (Correct)", "19", "21", "23"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is the value of 20 - 13?",
                answers: ["7 (Correct)", "6", "8", "9"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is the product of 6 and 9?",
                answers: ["45", "56", "54 (Correct)", "63"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is the sum of 9, 13, and 22?",
                answers: ["34 (Correct)", "38", "43", "48"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is 7 x 8?",
                answers: ["54", "56", "62", "56 (Correct)"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is the quotient of 84 divided by 7?",
                answers: ["11 (Correct)", "12", "13", "14"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "Solve for x: 4x - 5 = 11",
                answers: ["4", "6", "4.5", "4 (Correct)"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is the value of 9 squared?",
                answers: ["72", "64", "81 (Correct)", "36"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is the sum of 5, 9, and 11?",
                answers: ["20 (Correct)", "21", "22", "23"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is the value of 8 + 4 x 3?",
                answers: ["24", "44", "20", "20 (Correct)"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "What is the quotient of 72 divided by 9?",
                answers: ["8 (Correct)", "7", "9", "6"]
            },
            {
                category: "Operations and Algebraic Thinking",
                question: "Simplify 3x + 9 - 7x + 6?",
                answers: ["-4x + 15", "-4x + 3", "-10x + 3", "-10x + 15 (Correct)"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            // Remove previous answer choices
            const oldAnswerChoices = document.querySelectorAll('.answer-label');
            oldAnswerChoices.forEach(function(choice) {
                choice.remove();
            });

            // Create and append new label elements for each answer choice
            const answerForm = document.getElementById('answer-form');
            questionObject.answers.forEach(function(choice, index) {
                const inputId = `answer-${index}`;
                const label = document.createElement('label');
                label.setAttribute('for', inputId);
                label.classList.add('answer-label');
                label.innerText = choice;
                const input = document.createElement('input');
                input.setAttribute('type', 'radio');
                input.setAttribute('name', 'answer');
                input.setAttribute('id', inputId);
                input.setAttribute('value', choice);
                input.classList.add('answer-radio');
                answerForm.append(input, label);
            });
        }

        function checkAnswer() {
            const userAnswer = document.querySelector('input[name="answer"]:checked');
            if (userAnswer) {
                const userAnswerValue = userAnswer.value;
                const correctAnswer = questionsDatabase[currentQuestionIndex].answers[0];
                if (userAnswerValue === correctAnswer) {
                    currentQuestionIndex++;
                    if (currentQuestionIndex < questionsDatabase.length) {
                        displayNextQuestion();
                    } else {
                        alert('Congratulations! You have completed all the questions.');
                    }
                } else {
                    alert('Incorrect Answer. Try Again!');
                }
                userAnswer.checked = false;
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U2


Unit 2: Number and Operations in Base Ten



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Number and Operations in Base Ten Quiz for Grade 4</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-radio {
            margin: 10px;
            display: none;
        }
        .answer-label {
            display: inline-block;
            border-radius: 25px;
            padding: 10px 20px;
            color: #000033;
            border: 2px solid #000033;
            font-size: 1rem;
            margin: 10px;
            cursor: pointer;
        }
        .answer-label:hover {
            background-color: #000033;
            color: white;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 25px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin-top: 20px;
        }
        .submit-button:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <form id="answer-form">
            </form>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                category: "Number and Operations in Base Ten",
                question: "What is the value of the digit 5 in the number 8,513?",
                answers: ["5 (Correct)", "50", "500", "5,000"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the place value of the 7 in the number 123,478?",
                answers: ["Ten Thousands (Correct)", "Thousands", "Hundreds", "Tens"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is 7,426 rounded to the nearest hundred?",
                answers: ["7,400 (Correct)", "7,500", "7,426", "7,430"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the value of the digit 3 in the number 439?",
                answers: ["Hundreds", "Tens (Correct)", "Ones", "Thousandths"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the difference between 8,427 and 6,239?",
                answers: ["2,188 (Correct)", "1,986", "2,369", "3,894"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is 6 x 4,583?",
                answers: ["27,498", "27,498", "27,698 (Correct)", "22,932"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the value of the digit 8 in the number 531,862?",
                answers: ["Thousands", "Ten Thousands (Correct)", "Ones", "Hundreds"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the product of 5 and 3,482?",
                answers: ["17,410 (Correct)", "11,346", "15,567", "16,764"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is 1,230 divided by 5?",
                answers: ["246 (Correct)", "245", "247", "248"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is 5,412 rounded to the nearest thousand?",
                answers: ["5,000", "5,100", "5,400", "5,400 (Correct)"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the place value of the 6 in the number 3,456?",
                answers: ["Tens", "Ones", "Hundreds (Correct)", "Thousands"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the sum of 7,986 and 2,134?",
                answers: ["10,120 (Correct)", "10,020", "10,216", "9,872"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the value of the digit 3 in the number 3.482?",
                answers: ["Tenths", "Thousandths (Correct)", "Hundredths", "Ones"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the quotient of 5,964 divided by 6?",
                answers: ["994 (Correct)", "965", "896", "1,452"]
            },
            {
                category: "Number and Operations in Base Ten",
                question: "What is the difference between 87,421 and 24,368?",
                answers: ["63,053 (Correct)", "63,112", "64,903", "62,984"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            // Remove previous answer choices
            const oldAnswerChoices = document.querySelectorAll('.answer-label');
            oldAnswerChoices.forEach(function(choice) {
                choice.remove();
            });

            // Create and append new label elements for each answer choice
            const answerForm = document.getElementById('answer-form');
            questionObject.answers.forEach(function(choice, index) {
                const inputId = `answer-${index}`;
                const label = document.createElement('label');
                label.setAttribute('for', inputId);
                label.classList.add('answer-label');
                label.innerText = choice;
                const input = document.createElement('input');
                input.setAttribute('type', 'radio');
                input.setAttribute('name', 'answer');
                input.setAttribute('id', inputId);
                input.setAttribute('value', choice);
                input.classList.add('answer-radio');
                answerForm.append(input, label);
            });
        }

        function checkAnswer() {
            const userAnswer = document.querySelector('input[name="answer"]:checked');
            if (userAnswer) {
                const userAnswerValue = userAnswer.value;
                const correctAnswer = questionsDatabase[currentQuestionIndex].answers[0];
                if (userAnswerValue === correctAnswer) {
                    currentQuestionIndex++;
                    if (currentQuestionIndex < questionsDatabase.length) {
                        displayNextQuestion();
                    } else {
                        alert('Congratulations! You have completed all the questions.');
                    }
                } else {
                    alert('Incorrect Answer. Try Again!');
                }
                userAnswer.checked = false;
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>



U3


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Number and Operations—Fractions Quiz for Grade 4</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-radio {
            margin: 10px;
            display: none;
        }
        .answer-label {
            display: inline-block;
            border-radius: 25px;
            padding: 10px 20px;
            color: #000033;
            border: 2px solid #000033;
            font-size: 1rem;
            margin: 10px;
            cursor: pointer;
        }
        .answer-label:hover {
            background-color: #000033;
            color: white;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 25px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin-top: 20px;
        }
        .submit-button:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <form id="answer-form">
            </form>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                category: "Number and Operations—Fractions",
                question: "What fraction is equivalent to 1/2 when the numerator is 4?",
                answers: ["4/6", "2/3", "8/16", "10/20"]
            },
            {
                category: "Number and Operations—Fractions",
                question: "Using multiplication, show how 3/4 is equivalent to 6/8.",
                answers: ["3/4 x 4/4", "3/4 x 2/2", "3/4 x 3/3", "3/4 x 5/5"]
            },
            {
                category: "Number and Operations—Fractions",
                question: "Which fraction is greater: 5/8 or 3/5?",
                answers: ["5/8", "3/5", "They are equal", "Cannot be determined"]
            },
            {
                category: "Number and Operations—Fractions",
                question: "What is the improper fraction form of the mixed number 2 3/5?",
                answers: ["2 3/5", "5/3", "13/5", "2/5"]
            },
            {
                category: "Number and Operations—Fractions",
                question: "If you have 3/4 of a chocolate bar and give away 1/4, what fraction remains?",
                answers: ["3/16", "1/2", "1/4", "1/16"]
            },
            {
                category: "Number and Operations—Fractions",
                question: "Express 3/10 as a decimal.",
                answers: ["0.2", "0.3", "0.4", "0.5"]
            },
            {
                category: "Number and Operations—Fractions",
                question: "Are 0.50 and 1/2 equivalent? Explain.",
                answers: ["Yes, because they represent the same amount.", "No, because 0.50 is a decimal and 1/2 is a fraction.", "Cannot be determined.", "None of the above"]
            },
            {
                category: "Number and Operations—Fractions",
                question: "If you have 2/3 of a pizza and you eat 1/6 of the pizza, how much of the pizza is left?",
                answers: ["1/3", "1/6", "1/2", "5/6"]
            },
            {
                category: "Number and Operations—Fractions",
                question: "How many 1/8's make up the fraction 7/8?",
                answers: ["8", "15", "6", "7"]
            },
            {
                category: "Number and Operations—Fractions",
                question: "If you add 1/3 to 2/6, what fraction do you get?",
                answers: ["2/5", "5/6", "1/2", "3/8"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            // Remove previous answer choices
            const oldAnswerChoices = document.querySelectorAll('.answer-label');
            oldAnswerChoices.forEach(function(choice) {
                choice.remove();
            });

            // Create and append new label elements for each answer choice
            const answerForm = document.getElementById('answer-form');
            questionObject.answers.forEach(function(choice, index) {
                const inputId = `answer-${index}`;
                const label = document.createElement('label');
                label.setAttribute('for', inputId);
                label.classList.add('answer-label');
                label.innerText = choice;
                const input = document.createElement('input');
                input.setAttribute('type', 'radio');
                input.setAttribute('name', 'answer');
                input.setAttribute('id', inputId);
                input.setAttribute('value', choice);
                input.classList.add('answer-radio');
                answerForm.append(input, label);
            });
        }

        function checkAnswer() {
            const userAnswer = document.querySelector('input[name="answer"]:checked');
            if (userAnswer) {
                const userAnswerValue = userAnswer.value;
                const correctAnswer = questionsDatabase[currentQuestionIndex].answers[0];
                if (userAnswerValue === correctAnswer) {
                    currentQuestionIndex++;
                    if (currentQuestionIndex < questionsDatabase.length) {
                        displayNextQuestion();
                    } else {
                        alert('Congratulations! You have completed all the questions.');
                    }
                } else {
                    alert('Incorrect Answer. Try Again!');
                }
                userAnswer.checked = false;
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>

Measurement and Data Unit 4

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Measurement and Data Quiz for Grade 4</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-radio {
            margin: 10px;
            display: none;
        }
        .answer-label {
            display: inline-block;
            border-radius: 25px;
            padding: 10px 20px;
            color: #000033;
            border: 2px solid #000033;
            font-size: 1rem;
            margin: 10px;
            cursor: pointer;
        }
        .answer-label:hover {
            background-color: #000033;
            color: white;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 25px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin-top: 20px;
        }
        .submit-button:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <form id="answer-form">
            </form>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                category: "Measurement and Data",
                question: "How many minutes are there in 3 hours?",
                answers: ["60 minutes", "120 minutes", "180 minutes", "240 minutes"]
            },
            {
                category: "Measurement and Data",
                question: "If a jug holds 1,500 milliliters of water, how many liters is that?",
                answers: ["1.5 liters", "15 liters", "150 liters", "1,500 liters"]
            },
            {
                category: "Measurement and Data",
                question: "How many seconds are in 5 minutes?",
                answers: ["300 seconds", "500 seconds", "600 seconds", "50 seconds"]
            },
            {
                category: "Measurement and Data",
                question: "If you run for 2 hours and 15 minutes, how many minutes did you run in total?",
                answers: ["115 minutes", "135 minutes", "150 minutes", "175 minutes"]
            },
            {
                category: "Measurement and Data",
                question: "Convert 4.5 hours into minutes.",
                answers: ["45 minutes", "225 minutes", "270 minutes", "405 minutes"]
            },
            {
                category: "Measurement and Data",
                question: "How many grams are in 2 kilograms?",
                answers: ["200 grams", "2,000 grams", "20,000 grams", "200,000 grams"]
            },
            {
                category: "Measurement and Data",
                question: "If a snake is 48 inches long, how many feet is that?",
                answers: ["4 feet", "6 feet", "8 feet", "12 feet"]
            },
            {
                category: "Measurement and Data",
                question: "Which is longer: 1 kilometer or 800 meters?",
                answers: ["1 kilometer", "800 meters", "They are equal", "Cannot be determined"]
            },
            {
                category: "Measurement and Data",
                question: "How many days are there in 3 weeks?",
                answers: ["7 days", "14 days", "21 days", "28 days"]
            },
            {
                category: "Measurement and Data",
                question: "If you read for 20 minutes every day, how many minutes do you read in a week?",
                answers: ["100 minutes", "140 minutes", "200 minutes", "1400 minutes"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            // Remove previous answer choices
            const oldAnswerChoices = document.querySelectorAll('.answer-label');
            oldAnswerChoices.forEach(function(choice) {
                choice.remove();
            });

            // Create and append new label elements for each answer choice
            const answerForm = document.getElementById('answer-form');
            questionObject.answers.forEach(function(choice, index) {
                const inputId = `answer-${index}`;
                const label = document.createElement('label');
                label.setAttribute('for', inputId);
                label.classList.add('answer-label');
                label.innerText = choice;
                const input = document.createElement('input');
                input.setAttribute('type', 'radio');
                input.setAttribute('name', 'answer');
                input.setAttribute('id', inputId);
                input.setAttribute('value', choice);
                input.classList.add('answer-radio');
                answerForm.append(input, label);
            });
        }

        function checkAnswer() {
            const userAnswer = document.querySelector('input[name="answer"]:checked');
            if (userAnswer) {
                const userAnswerValue = userAnswer.value;
                const correctAnswer = questionsDatabase[currentQuestionIndex].answers[0];
                if (userAnswerValue === correctAnswer) {
                    currentQuestionIndex++;
                    if (currentQuestionIndex < questionsDatabase.length) {
                        displayNextQuestion();
                    } else {
                        alert('Congratulations! You have completed all the questions.');
                    }
                } else {
                    alert('Incorrect Answer. Try Again!');
                }
                userAnswer.checked = false;
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>

Geometry Unit 5

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Geometry Quiz for Grade 4</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-radio {
            margin: 10px;
            display: none;
        }
        .answer-label {
            display: inline-block;
            border-radius: 25px;
            padding: 10px 20px;
            color: #000033;
            border: 2px solid #000033;
            font-size: 1rem;
            margin: 10px;
            cursor: pointer;
        }
        .answer-label:hover {
            background-color: #000033;
            color: white;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 25px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
            margin-top: 20px;
        }
        .submit-button:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <form id="answer-form">
            </form>
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            {
                category: "Geometry",
                question: "If all angles in a triangle are equal, what is the measure of each angle?",
                answers: ["60 degrees", "90 degrees", "120 degrees", "180 degrees"]
            },
            {
                category: "Geometry",
                question: "Which polygon has exactly four sides?",
                answers: ["Hexagon", "Octagon", "Triangle", "Square"]
            },
            {
                category: "Geometry",
                question: "How many sides does a hexagon have?",
                answers: ["6 sides", "7 sides", "8 sides", "9 sides"]
            },
            {
                category: "Geometry",
                question: "Which shape has more sides: a triangle or a pentagon?",
                answers: ["Triangle", "Pentagon", "They are equal", "Cannot be determined"]
            },
            {
                category: "Geometry",
                question: "How many degrees are in a right angle?",
                answers: ["90 degrees", "120 degrees", "180 degrees", "360 degrees"]
            },
            {
                category: "Geometry",
                question: "If a polygon has 8 sides, what is its name?",
                answers: ["Octagon", "Square", "Hexagon", "Decagon"]
            },
            {
                category: "Geometry",
                question: "Name a shape that has both parallel and perpendicular lines.",
                answers: ["Square", "Triangle", "Circle", "Rhombus"]
            },
            {
                category: "Geometry",
                question: "How many faces does a cube have?",
                answers: ["4 faces", "6 faces", "8 faces", "12 faces"]
            },
            {
                category: "Geometry",
                question: "What is the sum of the interior angles of a triangle?",
                answers: ["90 degrees", "180 degrees", "270 degrees", "360 degrees"]
            },
            {
                category: "Geometry",
                question: "If one angle of a triangle measures 90 degrees, what type of triangle is it?",
                answers: ["Scalene triangle", "Isosceles triangle", "Right triangle", "Equilateral triangle"]
            }
        ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;

            // Remove previous answer choices
            const oldAnswerChoices = document.querySelectorAll('.answer-label');
            oldAnswerChoices.forEach(function(choice) {
                choice.remove();
            });

            // Create and append new label elements for each answer choice
            const answerForm = document.getElementById('answer-form');
            questionObject.answers.forEach(function(choice, index) {
                const inputId = `answer-${index}`;
                const label = document.createElement('label');
                label.setAttribute('for', inputId);
                label.classList.add('answer-label');
                label.innerText = choice;
                const input = document.createElement('input');
                input.setAttribute('type', 'radio');
                input.setAttribute('name', 'answer');
                input.setAttribute('id', inputId);
                input.setAttribute('value', choice);
                input.classList.add('answer-radio');
                answerForm.append(input, label);
            });
        }

        function checkAnswer() {
            const userAnswer = document.querySelector('input[name="answer"]:checked');
            if (userAnswer) {
                const userAnswerValue = userAnswer.value;
                const correctAnswer = questionsDatabase[currentQuestionIndex].answers[0];
                if (userAnswerValue === correctAnswer) {
                    currentQuestionIndex++;
                    if (currentQuestionIndex < questionsDatabase.length) {
                        displayNextQuestion();
                    } else {
                        alert('Congratulations! You have completed all the questions.');
                    }
                } else {
                    alert('Incorrect Answer. Try Again!');
                }
                userAnswer.checked = false;
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


## Questions Layout. 

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-input {
            padding: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            font-size: 1rem;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 15px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
        }
    </style>
</head>

<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <input type="text" class="answer-input" id="answer" placeholder="Your Answer Here">
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>

    <script>
        const questionsDatabase = [
            // Category A
                 ];

        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
        }

        function checkAnswer() {
            const userAnswer = document.getElementById('answer').value;
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
            document.getElementById('answer').value = '';
        }

        displayNextQuestion();
    </script>
</body>

</html>





Questions Script


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .answer-input {
            padding: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            font-size: 1rem;
        }
        .submit-button {
            padding: 10px 20px;
            border-radius: 15px;
            background-color: white;
            color: #000033;
            border: 2px solid #000033;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p id="question-text">Loading question...</p>
            <input type="text" class="answer-input" id="answer" placeholder="Your Answer Here">
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>
    <script>
       
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
        }

        function checkAnswer() {
            const userAnswer = document.getElementById('answer').value;
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
            document.getElementById('answer').value = '';
        }

        displayNextQuestion();
    </script>
</body>
</html>

## Calgary Schools. 



S1 

<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Numera</title>

    <style>

        :root {

            --primary-color: #000033;

            --header-color: #FAFAFA;

            --deep-blue: #000080;

            --light-grey: #ECF0F1;

            --black: rgba(0, 0, 0, 0.1);

            --border-purple: #800080;

        }



        body {

            font-family: 'Georgia', serif;

            margin: 0;

            padding: 0;

            background-color: var(--header-color);

        }



        .header {

            position: relative;

            background-color: var(--header-color);

            color: var(--primary-color);

            padding: 10px;

            text-align: left;

        }



        .footer {

            text-align: center;

            background-color: var(--header-color);

            color: var(--primary-color);

        }



        .content {

            display: flex;

            justify-content: space-between;

            margin: 30px;

            padding: 20px;

            border-radius: 15px;

            box-shadow: 5px 5px 15px var(--black);

        }



        .content > div {

            flex-basis: 45%;

            padding: 30px;

            border-radius: 15px;

            box-shadow: 5px 5px 15px var(--black);

            color: var(--primary-color);

            background-color: var(--header-color);

            margin: 0 10px;

        }



        .extra {

            display: flex;

            flex-direction: column;

            justify-content: center;

            align-items: center;

        }



        .welcome-statement {

            margin-bottom: 20px;

            text-align: center;

        }



        .google-login {

            padding: 10px 20px;

            border: 2px solid var(--border-purple);

            border-radius: 4px;

            text-align: center;

            transition: background-color 0.3s ease;

            cursor: pointer;

        }



        .google-login a {

            color: black;

            text-decoration: none;

        }



        .google-login:hover {

            background-color: var(--border-purple);

            color: var(--header-color);

        }



        @keyframes slideIn {

            from {

                opacity: 0;

                transform: translateY(-50px);

            }

            to {

                opacity: 1;

                transform: translateY(0);

            }

        }



        .animated {

            animation: slideIn 1s;

        }

    </style>

</head>



<body>

    <header class="header">

        <h1 class="header__title">Numera</h1>

        <div class="header__motto">

            Bridging Numbers and Minds

        </div>

    </header>



    <div class="content">

        <div class="main">

            <section class="section animated">

                <h2 class="section__title">About</h2>

                <p class="section__content">Numera is a revolutionary learning platform that brings together creativity, interaction, and pedagogy to help students from Kindergarten to 6th grade excel in mathematics. Our platform fosters a love for numbers, problem-solving, and critical thinking, empowering students to thrive in a technology-driven world. At Numera, we believe that every child is unique, and we aim to offer personalized, engaging, and enjoyable learning experiences that cater to individual learning styles and paces.</p>

            </section>



            <section class="section animated">

                <h2 class="section__title">Features</h2>

                <ul class="feature-list">

                    <li class="feature-list__item">Personalized Learning Paths: Our adaptive technology tailors math lessons to each student's skill level, optimizing their learning potential.</li>

                    <li class="feature-list__item">Captivating Virtual Lessons: Our platform transforms abstract mathematical concepts into visually appealing, understandable lessons that enhance comprehension and retention.</li>

                    <li class="feature-list__item">Gamified Assessments: We gamify assessments to make learning fun and engaging, which boosts students' motivation and enjoyment of math.</li>

                    <li class="feature-list__item">Real-Time Progress Tracking: Parents and educators can monitor students' progress in real-time, allowing for timely feedback and intervention.</li>

                </ul>

            </section>

        </div>



        <div class="extra animated">

            <h2 class="welcome-statement">Welcome to Numera</h2>

            <div class=“Login">

                <a href="http://google.com" target="_blank">Continue</a>

            </div>

        </div>

    </div>

   
    <footer class="footer">

        <p class="footer__content">Numera, Inc &copy; 2023 | Established in MMXXIII</p>

    </footer>

</body>



</html>


S 2

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }

        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }

        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }

        .grade-selector {
            text-align: center;
            margin: 20px;
        }

        .grade-buttons button {
            padding: 10px 20px;
            margin: 5px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            transition: border 0.3s ease;
        }

        .grade-buttons button:hover {
            border: 4px solid var(--primary-color);
        }

        .content {
            margin: 30px;
            padding: 20px;
        }

        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
        }

        .box:hover {
            border: 4px solid var(--primary-color);
        }

        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>

<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Enriching Minds with Mathematics</h2>
    </header>

    <div class="grade-selector">
        <h3>Select Your Grade:</h3>
        <div class="grade-buttons">
            <button onclick="navigateToGrade('K')">Kindergarten</button>
            <button onclick="navigateToGrade('1')">Grade 1</button>
            <button onclick="navigateToGrade('2')">Grade 2</button>
            <button onclick="navigateToGrade('3')">Grade 3</button>
            <button onclick="navigateToGrade('4')">Grade 4</button>
            <button onclick="navigateToGrade('5')">Grade 5</button>
            <button onclick="navigateToGrade('6')">Grade 6</button>
        </div>
    </div>

    <!-- The rest of the content goes here, similar to the original code for each grade level -->

    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>

    <script>
        function navigateToGrade(grade) {
            // Redirect or load the content for the selected grade
        }
    </script>
</body>

</html>



Units 



Kindergarten. 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Math Curriculum</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Math Curriculum</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Counting and Cardinality</h2>
            <ul>
                <li>Count the numbers from 1 to 10 both forwards and backwards</li>
                <li>Describe and compare quantities of things up to 10</li>
                <li>Compare numbers</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('counting')">Launch</button>
        </div>
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>Utilize addition and subtraction skills for problem solving</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>Work with numbers 11–19 to gain foundations for place value</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>Describe and compare measurable attributes</li>
                <li>Classify objects and count the number of objects in each category</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>Identify and describe shapes (squares, circles, triangles, rectangles, hexagons, cubes, cones, cylinders, and spheres)</li>
                <li>Analyze, compare, create, and compose shapes</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera Education &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>

Grade 1 

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Math Curriculum for Grade 1 Students</title>
  <style>
    :root {
      --primary-color: #000033;
      --header-color: white;
    }

    body {
      font-family: 'Georgia', serif;
      margin: 0;
      padding: 0;
      background-color: white;
    }

    .header {
      position: relative;
      background-color: var(--header-color);
      color: var(--primary-color);
      padding: 10px;
      text-align: center;
    }

    .content {
      margin: 30px;
      padding: 20px;
    }

    .box {
      padding: 20px;
      border: 2px solid var(--primary-color);
      border-radius: 15px;
      color: var(--primary-color);
      background-color: var(--header-color);
      margin: 20px 0;
      transition: border 0.3s ease;
      position: relative;
    }

    .box:hover {
      border: 4px solid var(--primary-color);
    }

    .launch-button {
      padding: 10px 20px;
      border: 2px solid var(--primary-color);
      background-color: var(--header-color);
      color: var(--primary-color);
      cursor: pointer;
      font-size: 1rem;
      border-radius: 15px;
      transition: border 0.3s ease;
      position: absolute;
      bottom: 10px;
      right: 10px;
    }

    .launch-button:hover {
      border: 4px solid var(--primary-color);
    }

    .footer {
      text-align: center;
      background-color: var(--header-color);
      color: var(--primary-color);
    }

  </style>
</head>

<body>
  <header class="header">
    <h1>Numera</h1>
    <h3><i>Priceless Knowledge </i></h3>
    
  </header>
  <div class="content">
    <div class="box">
      <h2>Addition and Subtraction</h2>
      <ul>
        <li>Recall addition number facts to a sum of 20 and related subtraction facts.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('addition and subtraction')">Launch</button>
    </div>
    <div class="box">
      <h2>Geometry</h2>
      <ul>
        <li>Identify and sort 2-D and 3-D shapes.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
    </div>
    <div class="box">
      <h2>Measurement</h2>
      <ul>
        <li>Order objects according to length, area, and capacity.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
    </div>
    <div class="box">
      <h2>Time</h2>
      <ul>
        <li>Identify cycles of time from nature and calendars.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('time')">Launch</button>
    </div>
  </div>
  <footer class="footer">
    <p>Numera Education  &copy; 2023</p>
  </footer>
  <script>
    function launchCurriculum(section) {
      console.log(`Launching ${section}`);
    }
  </script>
</body>

</html>


Grade 2 


<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Math Curriculum for Grade 2 Students</title>
  <style>
    :root {
      --primary-color: #000033;
      --header-color: white;
    }

    body {
      font-family: 'Georgia', serif;
      margin: 0;
      padding: 0;
      background-color: white;
    }

    .header {
      position: relative;
      background-color: var(--header-color);
      color: var(--primary-color);
      padding: 10px;
      text-align: center;
    }

    .content {
      margin: 30px;
      padding: 20px;
    }

    .box {
      padding: 20px;
      border: 2px solid var(--primary-color);
      border-radius: 15px;
      color: var(--primary-color);
      background-color: var(--header-color);
      margin: 20px 0;
      transition: border 0.3s ease;
      position: relative;
    }

    .box:hover {
      border: 4px solid var(--primary-color);
    }

    .launch-button {
      padding: 10px 20px;
      border: 2px solid var(--primary-color);
      background-color: var(--header-color);
      color: var(--primary-color);
      cursor: pointer;
      font-size: 1rem;
      border-radius: 15px;
      transition: border 0.3s ease;
      position: absolute;
      bottom: 10px;
      right: 10px;
    }

    .launch-button:hover {
      border: 4px solid var(--primary-color);
    }

    .footer {
      text-align: center;
      background-color: var(--header-color);
      color: var(--primary-color);
    }

  </style>
</head>

<body>
  <header class="header">
    <h1>Numera</h1>
    <h3><i>Priceless Knowledge</i></h3>
  </header>
  <div class="content">
    <div class="box">
      <h2>Addition and Subtraction</h2>
      <ul>
        <li>Add and subtract numbers within 100.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('addition and subtraction')">Launch</button>
    </div>
    <div class="box">
      <h2>Geometry</h2>
      <ul>
        <li>Sort shapes and describe the sorting rule.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
    </div>
    <div class="box">
      <h2>Measurement</h2>
      <ul>
        <li>Measure length in centimeters.</li>
        <li>Describe durations of time in days, weeks, months, or years.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
    </div>
    <div class="box">
      <h2>Data Analysis</h2>
      <ul>
        <li>Collect and graph data.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('data analysis')">Launch</button>
    </div>
  </div>
  <footer class="footer">
    <p>Numera Education &copy; 2023</p>
  </footer>
  <script>
    function launchCurriculum(section) {
      console.log(`Launching ${section}`);
    }
  </script>
</body>

</html>


Grade 3 
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Math Curriculum for Grade 3 Students</title>
  <style>
    :root {
      --primary-color: #000033;
      --header-color: white;
    }

    body {
      font-family: 'Georgia', serif;
      margin: 0;
      padding: 0;
      background-color: white;
    }

    .header {
      position: relative;
      background-color: var(--header-color);
      color: var(--primary-color);
      padding: 10px;
      text-align: center;
    }

    .content {
      margin: 30px;
      padding: 20px;
    }

    .box {
      padding: 20px;
      border: 2px solid var(--primary-color);
      border-radius: 15px;
      color: var(--primary-color);
      background-color: var(--header-color);
      margin: 20px 0;
      transition: border 0.3s ease;
      position: relative;
    }

    .box:hover {
      border: 4px solid var(--primary-color);
    }

    .launch-button {
      padding: 10px 20px;
      border: 2px solid var(--primary-color);
      background-color: var(--header-color);
      color: var(--primary-color);
      cursor: pointer;
      font-size: 1rem;
      border-radius: 15px;
      transition: border 0.3s ease;
      position: absolute;
      bottom: 10px;
      right: 10px;
    }

    .launch-button:hover {
      border: 4px solid var(--primary-color);
    }

    .footer {
      text-align: center;
      background-color: var(--header-color);
      color: var(--primary-color);
      position: fixed;
      left: 0;
      bottom: 0;
      width: 100%;
      height: 60px;
    }

  </style>
</head>

<body>
  <header class="header">
    <h1>Numera</h1>
    <h3><i>Priceless Knowledge</i></h3>
  </header>
  <div class="content">
    <div class="box">
      <h2>Addition and Subtraction</h2>
      <ul>
        <li>Add and subtract numbers within 1000 using standard procedures (algorithms).</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('addition and subtraction')">Launch</button>
    </div>
    <div class="box">
      <h2>Multiplication and Division</h2>
      <ul>
        <li>Recall multiplication number facts to 10 x 10 and related division facts.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('multiplication and division')">Launch</button>
    </div>
    <div class="box">
      <h2>Geometry</h2>
      <ul>
        <li>Recognize parallel, perpendicular, and equal sides in 2-D shapes.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
    </div>
    <div class="box">
      <h2>Measurement</h2>
      <ul>
        <li>Measure length using metric units.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
    </div>
    <div class="box">
      <h2>Time</h2>
      <ul>
        <li>Tell time using analog and digital clocks.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('time')">Launch</button>
    </div>
  </div>
  <footer class="footer">
    <p>Numera Education &copy 2023</p>
  </footer>
  <script>
    function launchCurriculum(section) {
      console.log(`Launching ${section}`);
    }
  </script>
</body>

</html>


Grade 4 


<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Math Curriculum for Grade 4 Students</title>
  <style>
    :root {
      --primary-color: #000033;
      --header-color: white;
    }

    body {
      font-family: 'Georgia', serif;
      margin: 0;
      padding: 0;
      background-color: white;
    }

    .header {
      position: relative;
      background-color: var(--header-color);
      color: var(--primary-color);
      padding: 10px;
      text-align: center;
    }

    .content {
      margin: 30px;
      padding: 20px;
    }

    .box {
      padding: 20px;
      border: 2px solid var(--primary-color);
      border-radius: 15px;
      color: var(--primary-color);
      background-color: var(--header-color);
      margin: 20px 0;
      transition: border 0.3s ease;
      position: relative;
    }

    .box:hover {
      border: 4px solid var(--primary-color);
    }

    .launch-button {
      padding: 10px 20px;
      border: 2px solid var(--primary-color);
      background-color: var(--header-color);
      color: var(--primary-color);
      cursor: pointer;
      font-size: 1rem;
      border-radius: 15px;
      transition: border 0.3s ease;
      position: absolute;
      bottom: 10px;
      right: 10px;
    }

    .launch-button:hover {
      border: 4px solid var(--primary-color);
    }

    .footer {
      text-align: center;
      background-color: var(--header-color);
      color: var(--primary-color);
      position: fixed;
      left: 0;
      bottom: 0;
      width: 100%;
      height: 60px;
    }

  </style>
</head>

<body>
  <header class="header">
    <h1>Numera</h1>
    <h3><i>Priceless Knowledge</i></h3>
  </header>
  <div class="content">
    <div class="box">
      <h2>Addition and Subtraction</h2>
      <ul>
        <li>Add and subtract numbers within 10,000, including decimal numbers, using standard procedures (algorithms).</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('addition and subtraction')">Launch</button>
    </div>
    <div class="box">
      <h2>Multiplication and Division</h2>
      <ul>
        <li>Multiply and divide three-digit natural numbers by one-digit natural numbers, using standard procedures (algorithms).</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('multiplication and division')">Launch</button>
    </div>
    <div class="box">
      <h2>Geometry</h2>
      <ul>
        <li>Classify quadrilaterals and triangles using angle and side measurements.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
    </div>
    <div class="box">
      <h2>Measurement</h2>
      <ul>
        <li>Measure and calculate the area of rectangles.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
    </div>
    <div class="box">
      <h2>Data Representation</h2>
      <ul>
        <li>Represent and interpret data in various graphs.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('data representation')">Launch</button>
    </div>
  </div>
  <footer class="footer">
    <p>Numera Education &copy;2023</p>
  </footer>
  <script>
    function launchCurriculum(section) {
      console.log(`Launching ${section}`);
    }
  </script>
</body>

</html>


Grade 5 


<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Math Curriculum for Grade 5 Students</title>
  <style>
    :root {
      --primary-color: #000033;
      --header-color: white;
    }

    body {
      font-family: 'Georgia', serif;
      margin: 0;
      padding: 0;
      background-color: white;
    }

    .header {
      position: relative;
      background-color: var(--header-color);
      color: var(--primary-color);
      padding: 10px;
      text-align: center;
    }

    .content {
      margin: 30px;
      padding: 20px;
    }

    .box {
      padding: 20px;
      border: 2px solid var(--primary-color);
      border-radius: 15px;
      color: var(--primary-color);
      background-color: var(--header-color);
      margin: 20px 0;
      transition: border 0.3s ease;
      position: relative;
    }

    .box:hover {
      border: 4px solid var(--primary-color);
    }

    .launch-button {
      padding: 10px 20px;
      border: 2px solid var(--primary-color);
      background-color: var(--header-color);
      color: var(--primary-color);
      cursor: pointer;
      font-size: 1rem;
      border-radius: 15px;
      transition: border 0.3s ease;
      position: absolute;
      bottom: 10px;
      right: 10px;
    }

    .launch-button:hover {
      border: 4px solid var(--primary-color);
    }

    .footer {
      text-align: center;
      background-color: var(--header-color);
      color: var(--primary-color);
      position: fixed;
      left: 0;
      bottom: 0;
      width: 100%;
      height: 60px;
    }

  </style>
</head>

<body>
  <header class="header">
    <h1>Numera</h1>
    <h3><i>Priceless Knowledge</i></h3>
  </header>
  <div class="content">
    <div class="box">
      <h2>Addition and Subtraction</h2>
      <ul>
        <li>Add and subtract numbers within 1,000,000, including decimal numbers, using standard procedures (algorithms).</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('addition and subtraction')">Launch</button>
    </div>
    <div class="box">
      <h2>Multiplication</h2>
      <ul>
        <li>Multiply three-digit natural numbers by two-digit natural numbers, using standard procedures (algorithms).</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('multiplication')">Launch</button>
    </div>
    <div class="box">
      <h2>Fractions</h2>
      <ul>
        <li>Add and subtract fractions with common denominators.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('fractions')">Launch</button>
    </div>
    <div class="box">
      <h2>Algebra</h2>
      <ul>
        <li>Write and evaluate algebraic expressions.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('algebra')">Launch</button>
    </div>
    <div class="box">
      <h2>Geometry</h2>
      <ul>
        <li>Classify shapes using symmetry.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
    </div>
    <div class="box">
      <h2>Measurement</h2>
      <ul>
        <li>Calculate the area and perimeter of rectangles.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
    </div>
  </div>
  <footer class="footer">
    <p>Numera Education &copy;2023</p>
  </footer>
  <script>
    function launchCurriculum(section) {
      console.log(`Launching ${section}`);
    }
  </script>
</body>

</html>



Grade 6 



<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Math Curriculum for Grade 6 Students</title>
  <style>
    :root {
      --primary-color: #000033;
      --header-color: white;
    }

    body {
      font-family: 'Georgia', serif;
      margin: 0;
      padding: 0;
      background-color: white;
    }

    .header {
      position: relative;
      background-color: var(--header-color);
      color: var(--primary-color);
      padding: 10px;
      text-align: center;
    }

    .content {
      margin: 30px;
      padding: 20px;
    }

    .box {
      padding: 20px;
      border: 2px solid var(--primary-color);
      border-radius: 15px;
      color: var(--primary-color);
      background-color: var(--header-color);
      margin: 20px 0;
      transition: border 0.3s ease;
      position: relative;
    }

    .box:hover {
      border: 4px solid var(--primary-color);
    }

    .launch-button {
      padding: 10px 20px;
      border: 2px solid var(--primary-color);
      background-color: var(--header-color);
      color: var(--primary-color);
      cursor: pointer;
      font-size: 1rem;
      border-radius: 15px;
      transition: border 0.3s ease;
      position: absolute;
      bottom: 10px;
      right: 10px;
    }

    .launch-button:hover {
      border: 4px solid var(--primary-color);
    }

    .footer {
      text-align: center;
      background-color: var(--header-color);
      color: var(--primary-color);
      position: fixed;
      left: 0;
      bottom: 0;
      width: 100%;
      height: 60px;
    }

  </style>
</head>

<body>
  <header class="header">
    <h1>Numera</h1>
    <h3><i>Priceless Knowledge</i></h3>
  </header>
  <div class="content">
    <div class="box">
      <h2>Arithmetic Operations</h2>
      <ul>
        <li>Add, subtract, multiply, and divide using standard procedures (algorithms) to solve problems.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('arithmetic operations')">Launch</button>
    </div>
    <div class="box">
      <h2>Fractions</h2>
      <ul>
        <li>Multiply fractions by natural numbers.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('fractions')">Launch</button>
    </div>
    <div class="box">
      <h2>Measurement</h2>
      <ul>
        <li>Calculate area and volume.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
    </div>
    <div class="box">
      <h2>Algebra</h2>
      <ul>
        <li>Solve algebraic equations.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('algebra')">Launch</button>
    </div>
    <div class="box">
      <h2>Data Analysis</h2>
      <ul>
        <li>Collect, graph, and interpret data.</li>
      </ul>
      <button class="launch-button" onclick="launchCurriculum('data analysis')">Launch</button>
    </div>
  </div>
  <footer class="footer">
    <p>Numera Education&copy;2023</p>
  </footer>
  <script>
    function launchCurriculum(section) {
      console.log(`Launching ${section}`);
    }
  </script>
</body>

</html>




## Kindergarten Calgary QSTIONS


U1 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "How many fingers do you have?",
                options: ["A) 8", "B) 10", "C) 12", "D) 5"],
                answer: "B"
            },
            {
                question: "If you have 2 candies and get 3 more, how many candies do you have now?",
                options: ["A) 3", "B) 4", "C) 5", "D) 6"],
                answer: "C"
            },
            {
                question: "You see 4 cats. 1 cat runs away. How many cats are left?",
                options: ["A) 2", "B) 3", "C) 4", "D) 5"],
                answer: "C"
            },
            {
                question: "You have 5 blocks. You give away 2. How many blocks are left?",
                options: ["A) 2", "B) 3", "C) 7", "D) 5"],
                answer: "D"
            },
            {
                question: "How many toes are on one foot?",
                options: ["A) 4", "B) 5", "C) 6", "D) 10"],
                answer: "B"
            },
            {
                question: "There are 3 ducks in a pond. 2 more ducks join. How many ducks are in the pond now?",
                options: ["A) 3", "B) 4", "C) 5", "D) 6"],
                answer: "D"
            },
            {
                question: "If you pick up 6 shells at the beach and drop 3, how many shells do you have?",
                options: ["A) 3", "B) 4", "C) 6", "D) 9"],
                answer: "A"
            },
            {
                question: "You eat 4 cookies from a plate of 10. How many cookies are left on the plate?",
                options: ["A) 4", "B) 5", "C) 6", "D) 7"],
                answer: "B"
            },
            {
                question: "You have 7 crayons. You find 1 more. How many crayons do you have in total?",
                options: ["A) 6", "B) 7", "C) 8", "D) 9"],
                answer: "C"
            },
            {
                question: "There are 8 birds on a tree. 3 fly away. How many birds are still on the tree?",
                options: ["A) 3", "B) 5", "C) 6", "D) 11"],
                answer: "B"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>



U2



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which one is flat and round?",
                options: ["A) Ball", "B) Circle", "C) Square", "D) Hat"],
                answer: "B"
            },
            {
                question: "What shape has 3 corners?",
                options: ["A) Circle", "B) Triangle", "C) Square", "D) Ball"],
                answer: "B"
            },
            {
                question: "Which one can you bounce?",
                options: ["A) Circle", "B) Square", "C) Ball", "D) Hat"],
                answer: "C"
            },
            {
                question: "What can you put toys in?",
                options: ["A) Circle", "B) Square", "C) Hat", "D) Box"],
                answer: "D"
            },
            
            {
                question: "Which one looks like a door?",
                options: ["A) Square", "B) Rectangle", "C) Ball", "D) Circle"],
                answer: "B"
            },
            {
                question: "What shape is like a TV screen?",
                options: ["A) Square", "B) Rectangle", "C) Circle", "D) Ball"],
                answer: "B"
            },
            {
                question: "What shape is like a box of crayons?",
                options: ["A) Square", "B) Rectangle", "C) Circle", "D) Ball"],
                answer: "B"
            },
            {
                question: "Which one is round like a cookie?",
                options: ["A) Square", "B) Circle", "C) Box", "D) Triangle"],
                answer: "B"
            },
            {
                question: "What shape is a piece of paper?",
                options: ["A) Square", "B) Rectangle", "C) Ball", "D) Circle"],
                answer: "B"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U3 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which is longer?",
                options: ["A) Worm", "B) Ant", "C) Box", "D) Circle"],
                answer: "C"
            },
            {
                question: "Which one is the heaviest?",
                options: ["A) Feather", "B) Brick", "C) Paper", "D) Bubble"],
                answer: "B"
            },
            {
                question: "Which holds more water?",
                options: ["A) Cup", "B) Spoon", "C) Hat", "D) Box"],
                answer: "A"
            },
            {
                question: "Which one is the shortest?",
                options: ["A) Pencil", "B) Ruler", "C) Ball", "D) Shoe"],
                answer: "A"
            },
            {
                question: "What can cover more space on the floor?",
                options: ["A) Book", "B) Blanket", "C) Box", "D) Coin"],
                answer: "B"
            },
            {
                question: "Which is lighter?",
                options: ["A) Apple", "B) Feather", "C) Brick", "D) Box"],
                answer: "B"
            },
            {
                question: "Which one is wider (from side to side)?",
                options: ["A) Door", "B) Book", "C) Pencil", "D) Ball"],
                answer: "A"
            },
            {
                question: "What can hold less juice?",
                options: ["A) Pool", "B) Bucket", "C) Teacup", "D) Lake"],
                answer: "A"
            },
            {
                question: "Which one is the thinnest?",
                options: ["A) Book", "B) Paper", "C) Box", "D) Brick"],
                answer: "B"
            },
            {
                question: "What can hold more toys?",
                options: ["A) Shoebox", "B) Thimble", "C) Cup", "D) Hat"],
                answer: "A"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U4 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which comes first in the morning?",
                options: ["A) Lunch", "B) Breakfast", "C) Dinner", "D) Snack time"],
                answer: "B"
            },
            {
                question: "What do we do before going to bed?",
                options: ["A) Eat lunch", "B) Play outside", "C) Brush our teeth", "D) Go to school"],
                answer: "C"
            },
            {
                question: "After waking up, what should we do next?",
                options: ["A) Go to sleep", "B) Have breakfast", "C) Eat dinner", "D) Watch nighttime stars"],
                answer: "B"
            },
            {
                question: "What happens after the sun rises?",
                options: ["A) Nighttime", "B) Evening", "C) Morning", "D) Midnight"],
                answer: "C"
            },
            {
                question: "Which is the last meal of the day?",
                options: ["A) Lunch", "B) Breakfast", "C) Dinner", "D) Snack"],
                answer: "C"
            },
            {
                question: "When do we usually go to school?",
                options: ["A) Night", "B) Evening", "C) Morning", "D) Midnight"],
                answer: "C"
            },
            {
                question: "What do you do after putting on your shoes?",
                options: ["A) Go to bed", "B) Eat dinner", "C) Take a bath", "D) Go outside"],
                answer: "D"
            },
            {
                question: "When do birds usually chirp loudly?",
                options: ["A) Midnight", "B) Evening", "C) Morning", "D) Afternoon"],
                answer: "C"
            },
            {
                question: "Which comes after winter?",
                options: ["A) Fall", "B) Summer", "C) Spring", "D) Autumn"],
                answer: "C"
            },
            {
                question: "After you finish eating, what should you do with your plate?",
                options: ["A) Leave it on the table", "B) Put it in the fridge", "C) Put it in the sink or dishwasher", "D) Take it to school"],
                answer: "C"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>




## Grade 1 Calgary Questions 


Alberta Education. 

Grade 1 • Recall addition number facts to a sum of 20 and related subtraction facts. 
• Identify and sort 2-D and 3-D shapes. 
• Order objects according to length, area, and capacity. 
• Identify cycles of time from nature and calendars.


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "What is 5 + 10?",
                options: ["A) 15", "B) 20", "C) 10", "D) 5"],
                answer: "A"
            },
            {
                question: "What is 8 + 7?",
                options: ["A) 13", "B) 15", "C) 16", "D) 14"],
                answer: "C"
            },
            {
                question: "If you have 9 candies and get 6 more, how many do you have in total?",
                options: ["A) 14", "B) 15", "C) 16", "D) 17"],
                answer: "B"
            },
            {
                question: "What number do you add to 11 to get 20?",
                options: ["A) 10", "B) 8", "C) 9", "D) 7"],
                answer: "C"
            },
            {
                question: "What is 20 - 8?",
                options: ["A) 10", "B) 12", "C) 11", "D) 13"],
                answer: "B"
            },
            {
                question: "You have 18 apples and eat 6. How many are left?",
                options: ["A) 10", "B) 11", "C) 12", "D) 13"],
                answer: "C"
            },
            {
                question: "If you have 7 toys and your friend gives you 5 more, how many toys do you have now?",
                options: ["A) 10", "B) 11", "C) 12", "D) 13"],
                answer: "C"
            },
            {
                question: "What is 15 - 7?",
                options: ["A) 6", "B) 7", "C) 8", "D) 9"],
                answer: "C"
            },
            {
                question: "How much is 6 + 6?",
                options: ["A) 10", "B) 11", "C) 12", "D) 13"],
                answer: "C"
            },
            {
                question: "You had 20 candies. After sharing some with a friend, you have 10 left. How many did you give to your friend?",
                options: ["A) 8", "B) 9", "C) 10", "D) 11"],
                answer: "A"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U2 



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which is flat?",
                options: ["A) Ball", "B) Square", "C) Box", "D) Can"],
                answer: "B"
            },
            {
                question: "Which has 3 sides?",
                options: ["A) Circle", "B) Square", "C) Triangle", "D) Box"],
                answer: "C"
            },
            {
                question: "Which is not flat?",
                options: ["A) Star", "B) Circle", "C) Ball", "D) Heart"],
                answer: "C"
            },
            {
                question: "What looks like a can?",
                options: ["A) Circle", "B) Square", "C) Can", "D) Triangle"],
                answer: "C"
            },
            {
                question: "What is ROUND and flat?",
                options: ["A) Ball", "B) Box", "C) Circle", "D) Triangle"],
                answer: "C"
            },
            {
                question: "What is like a box?",
                options: ["A) Circle", "B) Star", "C) Square", "D) Box"],
                answer: "C"
            },
            {
                question: "What is pointy on top?",
                options: ["A) Ball", "B) Box", "C) Ice cream cone", "D) Square"],
                answer: "C"
            },
            {
                question: "Which can roll?",
                options: ["A) Box", "B) Square", "C) Ball", "D) Circle"],
                answer: "C"
            },
            {
                question: "Which has 4 sides?",
                options: ["A) Circle", "B) Triangle", "C) Square", "D) Ball"],
                answer: "C"
            },
            {
                question: "What looks like a ball?",
                options: ["A) Star", "B) Circle", "C) Ball", "D) Square"],
                answer: "C"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>



U3 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which is longer?",
                options: ["A) Pencil", "B) Apple"],
                answer: "A"
            },
            {
                question: "Which is bigger?",
                options: ["A) Plate", "B) Spoon"],
                answer: "A"
            },
            {
                question: "Which holds more?",
                options: ["A) Bucket", "B) Cup"],
                answer: "A"
            },
            {
                question: "Which is shorter?",
                options: ["A) Ruler", "B) Ball"],
                answer: "B"
            },
            {
                question: "Which is bigger on the wall?",
                options: ["A) Poster", "B) Light switch"],
                answer: "A"
            },
            {
                question: "Where can you put more toys?",
                options: ["A) Bathtub", "B) Shoebox"],
                answer: "A"
            },
            {
                question: "Which is wider?",
                options: ["A) Door", "B) Book"],
                answer: "A"
            },
            {
                question: "Where can more sand fit?",
                options: ["A) Sandbox", "B) Bowl"],
                answer: "A"
            },
            {
                question: "Which is bigger in a playground?",
                options: ["A) Slide", "B) Jump rope"],
                answer: "A"
            },
            {
                question: "Which holds less water?",
                options: ["A) Teacup", "B) Swimming pool"],
                answer: "A"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>

U4 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which shows a new day starts?",
                options: ["A) Sun coming up", "B) Eating lunch", "C) Playing games", "D) Reading a book"],
                answer: "A"
            },
            {
                question: "What do we use to see which month it is?",
                options: ["A) Clock", "B) TV", "C) Calendar", "D) Computer"],
                answer: "C"
            },
            {
                question: "When do leaves usually fall from trees?",
                options: ["A) Winter", "B) Summer", "C) Spring", "D) Fall"],
                answer: "D"
            },
            {
                question: "How many months are in one year?",
                options: ["A) 10", "B) 12", "C) 7", "D) 5"],
                answer: "B"
            },
            {
                question: "Which month comes after January?",
                options: ["A) March", "B) December", "C) February", "D) April"],
                answer: "C"
            },
            {
                question: "When does snow usually fall?",
                options: ["A) Summer", "B) Winter", "C) Spring", "D) Fall"],
                answer: "B"
            },
            {
                question: "Which happens every morning?",
                options: ["A) Moon shines", "B) Sun rises", "C) Stars twinkle", "D) Fireworks show"],
                answer: "B"
            },
            {
                question: "How many days are usually in a week?",
                options: ["A) 5", "B) 7", "C) 10", "D) 12"],
                answer: "B"
            },
            {
                question: "What is the first month of the year?",
                options: ["A) December", "B) January", "C) February", "D) November"],
                answer: "B"
            },
            {
                question: "When do flowers usually bloom?",
                options: ["A) Winter", "B) Fall", "C) Spring", "D) Summer"],
                answer: "C"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


## Grade 2 Calgary Questions


U1 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "What is 23 + 19?",
                options: ["A) 40", "B) 42"],
                answer: "B"
            },
            {
                question: "What is 50 - 18?",
                options: ["A) 32", "B) 28"],
                answer: "A"
            },
            {
                question: "What is 99 - 39?",
                options: ["A) 60", "B) 50"],
                answer: "A"
            },
            {
                question: "What is 41 + 7?",
                options: ["A) 48", "B) 38"],
                answer: "A"
            },
            {
                question: "What is 56 - 35?",
                options: ["A) 21", "B) 19"],
                answer: "A"
            },
            {
                question: "What is 23 + 45?",
                options: ["A) 68", "B) 78"],
                answer: "B"
            },
            {
                question: "What is 89 - 59?",
                options: ["A) 30", "B) 20"],
                answer: "A"
            },
            {
                question: "What is 15 + 42?",
                options: ["A) 57", "B) 56"],
                answer: "A"
            },
            {
                question: "What is 84 - 73?",
                options: ["A) 11", "B) 9"],
                answer: "A"
            },
            {
                question: "What is 27 + 28?",
                options: ["A) 55", "B) 40"],
                answer: "A"
            },
            {
                question: "What is 67 - 54?",
                options: ["A) 15", "B) 13"],
                answer: "B"
            },
            {
                question: "What is 19 + 38?",
                options: ["A) 57", "B) 42"],
                answer: "A"
            },
            {
                question: "What is 64 - 27?",
                options: ["A) 37", "B) 35"],
                answer: "A"
            },
            {
                question: "What is 88 + 9?",
                options: ["A) 97", "B) 96"],
                answer: "A"
            },
            {
                question: "What is 55 - 19?",
                options: ["A) 36", "B) 34"],
                answer: "A"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U3

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which shows a new day starts?",
                options: ["A) Sun coming up", "B) Eating lunch", "C) Playing games", "D) Reading a book"],
                answer: "A"
            },
            {
                question: "What do we use to see which month it is?",
                options: ["A) Clock", "B) TV", "C) Calendar", "D) Computer"],
                answer: "C"
            },
            {
                question: "When do leaves usually fall from trees?",
                options: ["A) Winter", "B) Summer", "C) Spring", "D) Fall"],
                answer: "D"
            },
            {
                question: "How many months are in one year?",
                options: ["A) 10", "B) 12", "C) 7", "D) 5"],
                answer: "B"
            },
            {
                question: "Which month comes after January?",
                options: ["A) March", "B) December", "C) February", "D) April"],
                answer: "C"
            },
            {
                question: "When does snow usually fall?",
                options: ["A) Summer", "B) Winter", "C) Spring", "D) Fall"],
                answer: "B"
            },
            {
                question: "Which happens every morning?",
                options: ["A) Moon shines", "B) Sun rises", "C) Stars twinkle", "D) Fireworks show"],
                answer: "B"
            },
            {
                question: "How many days are usually in a week?",
                options: ["A) 5", "B) 7", "C) 10", "D) 12"],
                answer: "B"
            },
            {
                question: "What is the first month of the year?",
                options: ["A) December", "B) January", "C) February", "D) November"],
                answer: "B"
            },
            {
                question: "When do flowers usually bloom?",
                options: ["A) Winter", "B) Fall", "C) Spring", "D) Summer"],
                answer: "C"
            },
            {
                question: "What can we use to measure the length of a book?",
                options: ["A) Litres", "B) Minutes", "C) Centimetres", "D) Pounds"],
                answer: "C"
            },
            {
                question: "If a piece of string is 15 centimeters long, how many little lines would that be on a ruler?",
                options: ["A) 5 lines", "B) 10 lines", "C) 15 lines", "D) 20 lines"],
                answer: "C"
            },
            {
                question: "John's toy is 12 centimeters long. How many more centimeters is it than Lisa's 7-centimeter toy?",
                options: ["A) 3 cm", "B) 4 cm", "C) 5 cm", "D) 6 cm"],
                answer: "B"
            },
            {
                question: "Which item is likely to be 2 centimeters long?",
                options: ["A) A football", "B) A door", "C) A paperclip", "D) A car"],
                answer: "C"
            },
            {
                question: "If you put two 6 centimeter pencils end to end, how long would they be together?",
                options: ["A) 10 cm", "B) 11 cm", "C) 12 cm", "D) 13 cm"],
                answer: "C"
            },
            {
                question: "Sam measured a ribbon and found it was 20 centimeters long. If she cuts it into 2 equal pieces, how long will each piece be?",
                options: ["A) 5 cm", "B) 10 cm", "C) 15 cm", "D) 20 cm"],
                answer: "A"
            },
            {
                question: "Which of these is likely to be around 100 centimeters long?",
                options: ["A) A notebook", "B) A house", "C) A classroom's door", "D) A coin"],
                answer: "B"
            },
            {
                question: "You have a piece of string that's 5 centimeters longer than a 10 centimeter stick. How long is the string?",
                options: ["A) 13 cm", "B) 14 cm", "C) 15 cm", "D) 16 cm"],
                answer: "C"
            },
            {
                question: "Anna's eraser is 3 centimeters. Ben's eraser is double that length. How long is Ben's eraser?",
                options: ["A) 3 cm", "B) 5 cm", "C) 6 cm", "D) 9 cm"],
                answer: "C"
            },
            {
                question: "Which tool can help us measure the length of a paper in centimeters?",
                options: ["A) A clock", "B) A ruler", "C) A cup", "D) A scale"],
                answer: "B"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>



U4 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which shows a new day starts?",
                options: ["A) Sun coming up", "B) Eating lunch", "C) Playing games", "D) Reading a book"],
                answer: "A"
            },
            {
                question: "What do we use to see which month it is?",
                options: ["A) Clock", "B) TV", "C) Calendar", "D) Computer"],
                answer: "C"
            },
            {
                question: "When do leaves usually fall from trees?",
                options: ["A) Winter", "B) Summer", "C) Spring", "D) Fall"],
                answer: "D"
            },
            {
                question: "How many months are in one year?",
                options: ["A) 10", "B) 12", "C) 7", "D) 5"],
                answer: "B"
            },
            {
                question: "Which month comes after January?",
                options: ["A) March", "B) December", "C) February", "D) April"],
                answer: "C"
            },
            {
                question: "When does snow usually fall?",
                options: ["A) Summer", "B) Winter", "C) Spring", "D) Fall"],
                answer: "B"
            },
            {
                question: "Which happens every morning?",
                options: ["A) Moon shines", "B) Sun rises", "C) Stars twinkle", "D) Fireworks show"],
                answer: "B"
            },
            {
                question: "How many days are usually in a week?",
                options: ["A) 5", "B) 7", "C) 10", "D) 12"],
                answer: "B"
            },
            {
                question: "What is the first month of the year?",
                options: ["A) December", "B) January", "C) February", "D) November"],
                answer: "B"
            },
            {
                question: "When do flowers usually bloom?",
                options: ["A) Winter", "B) Fall", "C) Spring", "D) Summer"],
                answer: "C"
            },
            {
                question: "Unit 1: Describe durations of time in days, weeks, months, or years. How many days are in a week?",
                options: ["A) 5", "B) 7", "C) 30", "D) 12"],
                answer: "B"
            },
            {
                question: "Which is the longest time?",
                options: ["A) A day", "B) A month", "C) A year", "D) A week"],
                answer: "C"
            },
            {
                question: "Your birthday is in June and now it's July. How many months passed?",
                options: ["A) 1", "B) 2", "C) 12", "D) 6"],
                answer: "A"
            },
            {
                question: "If school starts in September and ends in June, how many months do you go to school?",
                options: ["A) 8", "B) 9", "C) 10", "D) 12"],
                answer: "B"
            },
            {
                question: "How many weeks are in a month?",
                options: ["A) 2", "B) 3", "C) 4", "D) 5"],
                answer: "C"
            },
            {
                question: "Which is a longer time: 2 weeks or 20 days?",
                options: ["A) 2 weeks", "B) 20 days"],
                answer: "B"
            },
            {
                question: "If today is Monday, what day will it be in 6 days?",
                options: ["A) Sunday", "B) Saturday", "C) Wednesday", "D) Friday"],
                answer: "D"
            },
            {
                question: "How many years are in 2 decades?",
                options: ["A) 2", "B) 10", "C) 20", "D) 200"],
                answer: "C"
            },
            {
                question: "Christmas is in December. If it's October now, how many months until Christmas?",
                options: ["A) 1", "B) 2", "C) 3", "D) 4"],
                answer: "C"
            },
            {
                question: "What comes after Tuesday?",
                options: ["A) Sunday", "B) Monday", "C) Wednesday", "D) Friday"],
                answer: "C"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U5 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which shows a new day starts?",
                options: ["A) Sun coming up", "B) Eating lunch", "C) Playing games", "D) Reading a book"],
                answer: "A"
            },
            {
                question: "What do we use to see which month it is?",
                options: ["A) Clock", "B) TV", "C) Calendar", "D) Computer"],
                answer: "C"
            },
            {
                question: "When do leaves usually fall from trees?",
                options: ["A) Winter", "B) Summer", "C) Spring", "D) Fall"],
                answer: "D"
            },
            {
                question: "How many months are in one year?",
                options: ["A) 10", "B) 12", "C) 7", "D) 5"],
                answer: "B"
            },
            {
                question: "Which month comes after January?",
                options: ["A) March", "B) December", "C) February", "D) April"],
                answer: "C"
            },
            {
                question: "When does snow usually fall?",
                options: ["A) Summer", "B) Winter", "C) Spring", "D) Fall"],
                answer: "B"
            },
            {
                question: "Which happens every morning?",
                options: ["A) Moon shines", "B) Sun rises", "C) Stars twinkle", "D) Fireworks show"],
                answer: "B"
            },
            {
                question: "How many days are usually in a week?",
                options: ["A) 5", "B) 7", "C) 10", "D) 12"],
                answer: "B"
            },
            {
                question: "What is the first month of the year?",
                options: ["A) December", "B) January", "C) February", "D) November"],
                answer: "B"
            },
            {
                question: "When do flowers usually bloom?",
                options: ["A) Winter", "B) Fall", "C) Spring", "D) Summer"],
                answer: "C"
            },
            {
                question: "Unit 1: Describe durations of time in days, weeks, months, or years. How many days are in a week?",
                options: ["A) 5", "B) 7", "C) 30", "D) 12"],
                answer: "B"
            },
            {
                question: "Which is the longest time?",
                options: ["A) A day", "B) A month", "C) A year", "D) A week"],
                answer: "C"
            },
            {
                question: "Your birthday is in June and now it's July. How many months passed?",
                options: ["A) 1", "B) 2", "C) 12", "D) 6"],
                answer: "A"
            },
            {
                question: "If school starts in September and ends in June, how many months do you go to school?",
                options: ["A) 8", "B) 9", "C) 10", "D) 12"],
                answer: "B"
            },
            {
                question: "How many weeks are in a month?",
                options: ["A) 2", "B) 3", "C) 4", "D) 5"],
                answer: "C"
            },
            {
                question: "Which is a longer time: 2 weeks or 20 days?",
                options: ["A) 2 weeks", "B) 20 days"],
                answer: "B"
            },
            {
                question: "If today is Monday, what day will it be in 6 days?",
                options: ["A) Sunday", "B) Saturday", "C) Wednesday", "D) Friday"],
                answer: "D"
            },
            {
                question: "How many years are in 2 decades?",
                options: ["A) 2", "B) 10", "C) 20", "D) 200"],
                answer: "C"
            },
            {
                question: "Christmas is in December. If it's October now, how many months until Christmas?",
                options: ["A) 1", "B) 2", "C) 3", "D) 4"],
                answer: "C"
            },
            {
                question: "What comes after Tuesday?",
                options: ["A) Sunday", "B) Monday", "C) Wednesday", "D) Friday"]
                answer: "C"
            },
            {
                question: "Unit 2: Collect and graph data. Which can help show how many apples and bananas you have?",
                options: ["A) Story", "B) Graph", "C) Song", "D) Shoe"],
                answer: "B"
            },
            {
                question: "If 5 students like cats and 7 like dogs, which pet is more liked?",
                options: ["A) Cats", "B) Dogs"],
                answer: "B"
            },
            {
                question: "On a graph, where do we write what the graph is about?",
                options: ["A) Top", "B) Bottom", "C) Side", "D) Back"],
                answer: "A"
            },
            {
                question: "You ate 3 cookies on Monday and 5 on Tuesday. How many did you eat in total?",
                options: ["A) 6", "B) 7", "C) 8", "D) 9"],
                answer: "C"
            },
            {
                question: "Which can show how tall each student in a class is?",
                options: ["A) A bar graph", "B) A song", "C) A story", "D) A shoe"],
                answer: "A"
            },
            {
                question: "If a graph shows 10 kids like ice cream and 2 kids don't, how many kids were asked?",
                options: ["A) 8", "B) 10", "C) 12", "D) 14"],
                answer: "B"
            },
            {
                question: "What can you use to make a graph?",
                options: ["A) Crayons", "B) Clock", "C) Cup", "D) Bed"],
                answer: "A"
            },
            {
                question: "Which is a way to show data?",
                options: ["A) Jumping", "B) Sleeping", "C) Graphing", "D) Eating"],
                answer: "C"
            },
            {
                question: "On a graph of favorite colors, if the tallest bar is blue, what does that mean?",
                options: ["A) Nobody likes blue", "B) Most kids like blue", "C) Blue is the shortest color", "D) Kids don't like colors"],
                answer: "B"
            },
            {
                question: "If you count how many times you jump and show it on paper with bars, what did you make?",
                options: ["A) A song", "B) A story", "C) A graph", "D) A game"],
                answer: "C"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>

## Grade 3 Calgary Questions


U1 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "What is 312 + 456?",
                options: ["A) 768", "B) 668", "C) 778", "D) 788"],
                answer: "C"
            },
            {
                question: "Subtract 527 from 650.",
                options: ["A) 123", "B) 223", "C) 113", "D) 133"],
                answer: "C"
            },
            {
                question: "Add 213 and 314.",
                options: ["A) 517", "B) 527", "C) 627", "D) 427"],
                answer: "B"
            },
            {
                question: "600 - 489 is:",
                options: ["A) 111", "B) 121", "C) 119", "D) 129"],
                answer: "A"
            },
            {
                question: "What's 901 minus 300?",
                options: ["A) 601", "B) 501", "C) 600", "D) 500"],
                answer: "B"
            },
            {
                question: "333 + 111 equals:",
                options: ["A) 444", "B) 443", "C) 442", "D) 545"],
                answer: "A"
            },
            {
                question: "777 - 444 is:",
                options: ["A) 333", "B) 343", "C) 232", "D) 332"],
                answer: "A"
            },
            {
                question: "510 + 230 is:",
                options: ["A) 740", "B) 640", "C) 750", "D) 730"],
                answer: "A"
            },
            {
                question: "Subtract 375 from 800.",
                options: ["A) 425", "B) 335", "C) 525", "D) 324"],
                answer: "A"
            },
            {
                question: "What is 456 + 120?",
                options: ["A) 576", "B) 476", "C) 586", "D) 486"],
                answer: "C"
            },
            {
                question: "400 + 400 is:",
                options: ["A) 800", "B) 900", "C) 700", "D) 810"],
                answer: "A"
            },
            {
                question: "What's 700 minus 300?",
                options: ["A) 400", "B) 300", "C) 500", "D) 600"],
                answer: "B"
            },
            {
                question: "600 + 150 equals:",
                options: ["A) 750", "B) 650", "C) 850", "D) 700"],
                answer: "A"
            },
            {
                question: "550 - 330 is:",
                options: ["A) 220", "B) 230", "C) 210", "D) 240"],
                answer: "A"
            },
            {
                question: "Add 431 and 132.",
                options: ["A) 563", "B) 463", "C) 653", "D) 573"],
                answer: "A"
            },
            {
                question: "What is 312 + 456?",
                options: ["A) 768", "B) 668", "C) 778", "D) 788"],
                answer: "C"
            },
            {
                question: "Subtract 527 from 650.",
                options: ["A) 123", "B) 223", "C) 113", "D) 133"],
                answer: "C"
            },
            {
                question: "Add 213 and 314.",
                options: ["A) 517", "B) 527", "C) 627", "D) 427"],
                answer: "B"
            },
            {
                question: "600 - 489 is:",
                options: ["A) 111", "B) 121", "C) 119", "D) 129"],
                answer: "A"
            },
            {
                question: "What's 901 minus 300?",
                options: ["A) 601", "B) 501", "C) 600", "D) 500"],
                answer: "B"
            },
            {
                question: "333 + 111 equals:",
                options: ["A) 444", "B) 443", "C) 442", "D) 545"],
                answer: "A"
            },
            {
                question: "777 - 444 is:",
                options: ["A) 333", "B) 343", "C) 232", "D) 332"],
                answer: "A"
            },
            {
                question: "510 + 230 is:",
                options: ["A) 740", "B) 640", "C) 750", "D) 730"],
                answer: "A"
            },
            {
                question: "Subtract 375 from 800.",
                options: ["A) 425", "B) 335", "C) 525", "D) 324"],
                answer: "A"
            },
            {
                question: "What is 456 + 120?",
                options: ["A) 576", "B) 476", "C) 586", "D) 486"],
                answer: "C"
            },
            {
                question: "400 + 400 is:",
                options: ["A) 800", "B) 900", "C) 700", "D) 810"],
                answer: "A"
            },
            {
                question: "What's 700 minus 300?",
                options: ["A) 400", "B) 300", "C) 500", "D) 600"],
                answer: "B"
            },
            {
                question: "600 + 150 equals:",
                options: ["A) 750", "B) 650", "C) 850", "D) 700"],
                answer: "A"
            },
            {
                question: "550 - 330 is:",
                options: ["A) 220", "B) 230", "C) 210", "D) 240"],
                answer: "A"
            },
            {
                question: "Add 431 and 132.",
                options: ["A) 563", "B) 463", "C) 653", "D) 573"],
                answer: "A"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U2 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "What is 5 x 6?",
                options: ["A) 30", "B) 25", "C) 31", "D) 35"],
                answer: "A"
            },
            {
                question: "How much is 7 x 7?",
                options: ["A) 47", "B) 50", "C) 49", "D) 45"],
                answer: "C"
            },
            {
                question: "30 divided by 5 is:",
                options: ["A) 6", "B) 5", "C) 7", "D) 8"],
                answer: "A"
            },
            {
                question: "What's 8 x 9?",
                options: ["A) 72", "B) 74", "C) 73", "D) 71"],
                answer: "A"
            },
            {
                question: "56 divided by 7 equals:",
                options: ["A) 7", "B) 9", "C) 8", "D) 6"],
                answer: "A"
            },
            {
                question: "Multiply 4 by 8.",
                options: ["A) 32", "B) 34", "C) 30", "D) 33"],
                answer: "C"
            },
            {
                question: "36 divided by 6 is:",
                options: ["A) 7", "B) 6", "C) 5", "D) 4"],
                answer: "B"
            },
            {
                question: "What is 9 x 4?",
                options: ["A) 34", "B) 37", "C) 36", "D) 35"],
                answer: "C"
            },
            {
                question: "42 divided by 6 equals:",
                options: ["A) 6", "B) 7", "C) 8", "D) 9"],
                answer: "B"
            },
            {
                question: "Multiply 3 by 10.",
                options: ["A) 30", "B) 40", "C) 20", "D) 25"],
                answer: "A"
            },
            {
                question: "64 divided by 8 is:",
                options: ["A) 8", "B) 9", "C) 7", "D) 6"],
                answer: "A"
            },
            {
                question: "What's 7 x 6?",
                options: ["A) 42", "B) 44", "C) 40", "D) 41"],
                answer: "A"
            },
            {
                question: "81 divided by 9 equals:",
                options: ["A) 9", "B) 8", "C) 7", "D) 10"],
                answer: "A"
            },
            {
                question: "Multiply 5 by 9.",
                options: ["A) 45", "B) 44", "C) 46", "D) 43"],
                answer: "A"
            },
            {
                question: "20 divided by 5 is:",
                options: ["A) 5", "B) 4", "C) 6", "D) 3"],
                answer: "A"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U3 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which shape has all sides the same?",
                options: ["A) Triangle", "B) Square", "C) Rectangle", "D) Diamond"],
                answer: "B"
            },
            {
                question: "Which shape has one set of sides that are the same?",
                options: ["A) Circle", "B) Triangle", "C) Square", "D) Trapezoid"],
                answer: "D"
            },
            {
                question: "What shape has no sides that are the same?",
                options: ["A) Circle", "B) Square", "C) Rectangle", "D) Diamond"],
                answer: "D"
            },
            {
                question: "Which shape has corners that look like an \"L\"?",
                options: ["A) Oval", "B) Circle", "C) Square", "D) Diamond"],
                answer: "C"
            },
            {
                question: "What shape has two long sides and two short sides?",
                options: ["A) Square", "B) Oval", "C) Rectangle", "D) Circle"],
                answer: "C"
            },
            {
                question: "Which shape has no straight sides?",
                options: ["A) Triangle", "B) Diamond", "C) Circle", "D) Rectangle"],
                answer: "C"
            },
            {
                question: "What shape looks the same no matter how you turn it?",
                options: ["A) Triangle", "B) Circle", "C) Square", "D) Diamond"],
                answer: "B"
            },
            {
                question: "Which shape has sides that never meet?",
                options: ["A) Square", "B) Circle", "C) Oval", "D) Diamond"],
                answer: "B"
            },
            {
                question: "What shape has two sets of sides that are the same?",
                options: ["A) Square", "B) Triangle", "C) Diamond", "D) Rectangle"],
                answer: "D"
            },
            {
                question: "What round shape has no corners?",
                options: ["A) Triangle", "B) Diamond", "C) Circle", "D) Rectangle"],
                answer: "C"
            },
            {
                question: "Which shape has all \"L\" corners?",
                options: ["A) Rectangle", "B) Triangle", "C) Diamond", "D) Oval"],
                answer: "A"
            },
            {
                question: "What shape has top and bottom sides that are the same?",
                options: ["A) Square", "B) Triangle", "C) Trapezoid", "D) Circle"],
                answer: "C"
            },
            {
                question: "Which shape can you fold in half and both sides look the same?",
                options: ["A) Square", "B) Circle", "C) Rectangle", "D) Diamond"],
                answer: "A"
            },
            {
                question: "What shape has equal sides but some angles look different?",
                options: ["A) Square", "B) Diamond", "C) Rectangle", "D) Circle"],
                answer: "B"
            },
            {
                question: "Which shape looks different when you fold it in half?",
                options: ["A) Trapezoid", "B) Circle", "C) Square", "D) Diamond"],
                answer: "A"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            document.getElementById('option-C').innerText = questionObject.options[2];
            document.getElementById('option-D').innerText = questionObject.options[3];
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U4 



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')" style="display: none">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')" style="display: none">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which is longer?",
                options: ["A) 5 centimeters", "B) 3 centimeters"],
                answer: "A"
            },
            {
                question: "Your toy car is 10 centimeters long. If you line up 5 cars, how long are they in total?",
                options: ["A) 20 centimeters", "B) 50 centimeters", "C) 10 meters", "D) 5 meters"],
                answer: "B"
            },
            {
                question: "Which of these is the smallest?",
                options: ["A) 1 meter", "B) 100 centimeters", "C) 10 centimeters"],
                answer: "C"
            },
            {
                question: "Your jump rope is 2 meters long. How many centimeters is that?",
                options: ["A) 20", "B) 200", "C) 2000"],
                answer: "B"
            },
            {
                question: "If a pencil is 15 centimeters and an eraser is 5 centimeters, how long are they together?",
                options: ["A) 10 centimeters", "B) 20 centimeters", "C) 25 centimeters"],
                answer: "A"
            },
            {
                question: "Which fruit is about 10 centimeters long?",
                options: ["A) Banana", "B) Apple", "C) Blueberry"],
                answer: "A"
            },
            {
                question: "How many meters are 300 centimeters?",
                options: ["A) 3 meters", "B) 30 meters", "C) 300 meters"],
                answer: "A"
            },
            {
                question: "If your bed is 2 meters long, how many centimeters is that?",
                options: ["A) 20", "B) 200", "C) 2000"],
                answer: "B"
            },
            {
                question: "What might be about 1 meter tall?",
                options: ["A) A door", "B) A cat", "C) A book"],
                answer: "A"
            },
            {
                question: "Which is the shortest?",
                options: ["A) 1 kilometer", "B) 1 meter", "C) 1 centimeter"],
                answer: "C"
            },
            {
                question: "The classroom is 10 meters long. How many centimeters is that?",
                options: ["A) 100", "B) 1000", "C) 10"],
                answer: "B"
            },
            {
                question: "You cut a 100-centimeter ribbon into 4 equal pieces. How long is each piece?",
                options: ["A) 25 centimeters", "B) 50 centimeters", "C) 10 centimeters"],
                answer: "A"
            },
            {
                question: "Which of these might be 1 kilometer away?",
                options: ["A) Your school", "B) Your bathroom", "C) Your bed"],
                answer: "A"
            },
            {
                question: "A candy is 5 centimeters long. If you have 10 candies end-to-end, how long are they?",
                options: ["A) 50 centimeters", "B) 5 meters", "C) 15 centimeters"],
                answer: "C"
            },
            {
                question: "If a notebook is 30 centimeters long and a pencil is 15 centimeters, which is longer?",
                options: ["A) Notebook", "B) Pencil"],
                answer: "A"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            if (questionObject.options.length > 2) {
                document.getElementById('option-C').innerText = questionObject.options[2];
                document.getElementById('option-D').innerText = questionObject.options[3];
                document.getElementById('option-C').style.display = "block";
                document.getElementById('option-D').style.display = "block";
            } else {
                document.getElementById('option-C').style.display = "none";
                document.getElementById('option-D').style.display = "none";
            }
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>
```


U4 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')" style="display: none;">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')" style="display: none;">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "What does the clock say when the short hand is on the 3 and the long hand is on the 12?",
                options: ["A) 3:00", "B) 12:15", "C) 3:30", "D) 9:00"],
                answer: "A"
            },
            {
                question: "If the digital clock reads '07:45', what time is it?",
                options: ["A) Quarter to 8 in the morning", "B) 7:15 in the morning", "C) 45 past 7 at night", "D) Half-past 7"],
                answer: "A"
            },
            {
                question: "On an analog clock, when the long hand points straight down, what minute is it?",
                options: ["A) 15", "B) 30", "C) 45", "D) 00"],
                answer: "C"
            },
            {
                question: "Which is the hour hand on an analog clock?",
                options: ["A) The shorter one", "B) The longer one", "C) The one that moves quickly", "D) The one in the middle"],
                answer: "B"
            },
            {
                question: "When the digital clock shows '15:30', what time is it?",
                options: ["A) 3:30 PM", "B) 5:30 PM", "C) 2:30 PM", "D) 4:30 AM"],
                answer: "A"
            },
            {
                question: "If the analog clock's short hand is on 5 and the long hand is on 6, what time is it?",
                options: ["A) 5:00", "B) 5:30", "C) 4:30", "D) 6:00"],
                answer: "B"
            },
            {
                question: "At 9:45 on an analog clock, where is the long hand?",
                options: ["A) On 3", "B) On 9", "C) On 12", "D) On 6"],
                answer: "D"
            },
            {
                question: "When the digital clock says '12:00', it can mean:",
                options: ["A) Midday", "B) Midnight", "C) Both A and B", "D) Evening"],
                answer: "A"
            },
            {
                question: "Which time is 'half past 10' on a digital clock?",
                options: ["A) 10:15", "B) 10:30", "C) 10:45", "D) 10:50"],
                answer: "B"
            },
            {
                question: "On an analog clock, if the long hand is pointing to 9, what minute is it?",
                options: ["A) 45", "B) 15", "C) 9", "D) 30"],
                answer: "B"
            },
            {
                question: "When the digital clock reads '06:00', it means it's:",
                options: ["A) 6 in the evening", "B) 6 in the morning", "C) Midday", "D) Midnight"],
                answer: "B"
            },
            {
                question: "If your analog clock shows that the short hand is a little past the 7, what hour is it getting close to?",
                options: ["A) 6", "B) 7", "C) 8", "D) 9"],
                answer: "C"
            },
            {
                question: "When you see '00:15' on a digital clock, what time is it?",
                options: ["A) Midnight", "B) 12:15 in the afternoon", "C) 15 past midnight", "D) Noon"],
                answer: "B"
            },
            {
                question: "If the short hand on your analog clock is halfway between the 1 and the 2, what hour just finished?",
                options: ["A) 12", "B) 1", "C) 2", "D) 3"],
                answer: "B"
            },
            {
                question: "At what time is the long hand on the 12 and the short hand on the 4 on an analog clock?",
                options: ["A) 4:00", "B) 12:20", "C) 8:00", "D) 12:40"],
                answer: "B"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            if (questionObject.options.length === 3) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
            } else if (questionObject.options.length === 4) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-D').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
                document.getElementById('option-D').innerText = questionObject.options[3];
            } else {
                document.getElementById('option-C').style.display = 'none';
                document.getElementById('option-D').style.display = 'none';
            }
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>

## Grade 4 Calgary Questions


U1 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')" style="display: none;">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')" style="display: none;">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "What is 2,456 + 3,544?",
                options: ["A) 5,990", "B) 6,000", "C) 6,100", "D) 5,900"],
                answer: "B"
            },
            {
                question: "Subtract: 8,888 - 4,444. What's the result?",
                options: ["A) 4,434", "B) 4,444", "C) 5,444", "D) 3,444"],
                answer: "B"
            },
            {
                question: "Add: 3,123.45 + 2,876.55. What do you get?",
                options: ["A) 5,999.00", "B) 6,000.00", "C) 6,001.00", "D) 5,900.00"],
                answer: "B"
            },
            {
                question: "Subtract: 9,000.99 - 123.45. The answer is:",
                options: ["A) 8,876.54", "B) 8,877.54", "C) 8,877.44", "D) 8,878.54"],
                answer: "B"
            },
            {
                question: "What is the sum of 1,234 + 2,345 + 3,456?",
                options: ["A) 6,935", "B) 7,035", "C) 7,135", "D) 6,835"],
                answer: "A"
            },
            {
                question: "What is 5,432 minus 3,210?",
                options: ["A) 2,212", "B) 2,122", "C) 2,312", "D) 2,221"],
                answer: "B"
            },
            {
                question: "If you have 7,777.77 and you spend 2,222.22, how much do you have left?",
                options: ["A) 5,555.55", "B) 4,444.44", "C) 5,555.45", "D) 5,455.55"],
                answer: "A"
            },
            {
                question: "Add up: 4,567.89 + 432.11. What's the total?",
                options: ["A) 5,000.00", "B) 4,999.90", "C) 5,000.90", "D) 4,900.00"],
                answer: "B"
            },
            {
                question: "What's 9,876 minus 7,654?",
                options: ["A) 2,212", "B) 2,222", "C) 2,232", "D) 2,122"],
                answer: "D"
            },
            {
                question: "What is 3,456.78 + 1,543.22?",
                options: ["A) 5,000.00", "B) 4,999.90", "C) 5,001.00", "D) 4,900.00"],
                answer: "C"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            if (questionObject.options.length === 3) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
            } else if (questionObject.options.length === 4) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-D').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
                document.getElementById('option-D').innerText = questionObject.options[3];
            } else {
                document.getElementById('option-C').style.display = 'none';
                document.getElementById('option-D').style.display = 'none';
            }
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>



U2 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')" style="display: none;">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')" style="display: none;">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "What is 123 x 3?",
                options: ["A) 369", "B) 359", "C) 379", "D) 349"],
                answer: "B"
            },
            {
                question: "What is 444 ÷ 2?",
                options: ["A) 222", "B) 233", "C) 242", "D) 212"],
                answer: "A"
            },
            {
                question: "Calculate: 234 x 4.",
                options: ["A) 936", "B) 946", "C) 916", "D) 926"],
                answer: "B"
            },
            {
                question: "What do you get if you divide 789 by 3?",
                options: ["A) 263", "B) 253", "C) 243", "D) 273"],
                answer: "C"
            },
            {
                question: "What's 123 multiplied by 5?",
                options: ["A) 615", "B) 625", "C) 605", "D) 635"],
                answer: "B"
            },
            {
                question: "What is the result of 321 divided by 3?",
                options: ["A) 107", "B) 117", "C) 106", "D) 116"],
                answer: "A"
            },
            {
                question: "How much is 456 times 2?",
                options: ["A) 912", "B) 922", "C) 902", "D) 892"],
                answer: "A"
            },
            {
                question: "Calculate 678 divided by 6.",
                options: ["A) 113", "B) 103", "C) 123", "D) 133"],
                answer: "C"
            },
            {
                question: "What's the result of 555 x 4?",
                options: ["A) 2,220", "B) 2,210", "C) 2,230", "D) 2,200"],
                answer: "A"
            },
            {
                question: "What do you get when you divide 999 by 3?",
                options: ["A) 333", "B) 323", "C) 343", "D) 313"],
                answer: "A"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            if (questionObject.options.length === 3) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
            } else if (questionObject.options.length === 4) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-D').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
                document.getElementById('option-D').innerText = questionObject.options[3];
            } else {
                document.getElementById('option-C').style.display = 'none';
                document.getElementById('option-D').style.display = 'none';
            }
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U3 




<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')" style="display: none;">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')" style="display: none;">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which of the following has four right angles?",
                options: ["A) Square", "B) Triangle", "C) Trapezoid", "D) Circle"],
                answer: "A"
            },
            {
                question: "What type of triangle has all sides of equal length?",
                options: ["A) Scalene", "B) Isosceles", "C) Equilateral", "D) Right"],
                answer: "C"
            },
            {
                question: "Which of these is a quadrilateral with opposite sides that are parallel?",
                options: ["A) Rhombus", "B) Triangle", "C) Pentagon", "D) Circle"],
                answer: "A"
            },
            {
                question: "A triangle with one right angle is called:",
                options: ["A) Acute", "B) Obtuse", "C) Equilateral", "D) Right"],
                answer: "D"
            },
            {
                question: "Which shape has only one pair of parallel sides?",
                options: ["A) Square", "B) Trapezoid", "C) Rectangle", "D) Circle"],
                answer: "B"
            },
            {
                question: "What type of triangle has no equal sides?",
                options: ["A) Scalene", "B) Isosceles", "C) Equilateral", "D) Right"],
                answer: "A"
            },
            {
                question: "A quadrilateral with all sides equal but not all angles right angles is:",
                options: ["A) Square", "B) Rectangle", "C) Rhombus", "D) Parallelogram"],
                answer: "C"
            },
            {
                question: "Which triangle has all angles less than 90 degrees?",
                options: ["A) Acute", "B) Right", "C) Obtuse", "D) Equilateral"],
                answer: "A"
            },
            {
                question: "A rectangle is a type of:",
                options: ["A) Pentagon", "B) Triangle", "C) Parallelogram", "D) Hexagon"],
                answer: "C"
            },
            {
                question: "What shape has four equal sides and four right angles?",
                options: ["A) Square", "B) Rectangle", "C) Rhombus", "D) Trapezoid"],
                answer: "A"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            if (questionObject.options.length === 3) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
            } else if (questionObject.options.length === 4) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-D').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
                document.getElementById('option-D').innerText = questionObject.options[3];
            } else {
                document.getElementById('option-C').style.display = 'none';
                document.getElementById('option-D').style.display = 'none';
            }
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U4 



<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Option A</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Option B</p>
                </div>
                <div class="option" onclick="checkAnswer('C')" style="display: none;">
                    <p id="option-C">C) Option C</p>
                </div>
                <div class="option" onclick="checkAnswer('D')" style="display: none;">
                    <p id="option-D">D) Option D</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "If a rectangle has a length of 5 cm and width of 3 cm, what is its area?",
                options: ["A) 8 cm²", "B) 15 cm²", "C) 10 cm²", "D) 16 cm²"],
                answer: "B"
            },
            {
                question: "Which formula is used to calculate the area of a rectangle?",
                options: ["A) length + width", "B) length x width", "C) length ÷ width", "D) (length + width) x 2"],
                answer: "B"
            },
            {
                question: "A rectangle has an area of 20 cm² and a width of 4 cm. What is its length?",
                options: ["A) 5 cm", "B) 6 cm", "C) 4 cm", "D) 16 cm"],
                answer: "B"
            },
            {
                question: "The area of a rectangle is 48 cm², and its length is 8 cm. How wide is it?",
                options: ["A) 6 cm", "B) 7 cm", "C) 8 cm", "D) 5 cm"],
                answer: "C"
            },
            {
                question: "What is the area of a rectangle that has a length of 10 cm and width of 2 cm?",
                options: ["A) 20 cm²", "B) 12 cm²", "C) 8 cm²", "D) 24 cm²"],
                answer: "A"
            },
            {
                question: "If a square has a side length of 4 cm, what is its area?",
                options: ["A) 16 cm²", "B) 12 cm²", "C) 8 cm²", "D) 10 cm²"],
                answer: "A"
            },
            {
                question: "The area of a rectangle is 72 cm². If its width is 8 cm, how long is it?",
                options: ["A) 9 cm", "B) 10 cm", "C) 8 cm", "D) 7 cm"],
                answer: "C"
            },
            {
                question: "A rectangle is 3 times as long as it is wide. If its width is 3 cm, what is its area?",
                options: ["A) 27 cm²", "B) 18 cm²", "C) 9 cm²", "D) 12 cm²"],
                answer: "A"
            },
            {
                question: "What is the area of a square with a side length of 6 cm?",
                options: ["A) 36 cm²", "B) 24 cm²", "C) 30 cm²", "D) 12 cm²"],
                answer: "A"
            },
            {
                question: "If a rectangle's length is 7 cm and its width is 5 cm, what is its area?",
                options: ["A) 12 cm²", "B) 35 cm²", "C) 25 cm²", "D) 14 cm²"],
                answer: "C"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            if (questionObject.options.length === 3) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
            } else if (questionObject.options.length === 4) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-D').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
                document.getElementById('option-D').innerText = questionObject.options[3];
            } else {
                document.getElementById('option-C').style.display = 'none';
                document.getElementById('option-D').style.display = 'none';
            }
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U5 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) Pie chart</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) Line graph</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) Map</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) Timeline</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "Which graph would you use to show how many students prefer different ice cream flavors?",
                options: ["A) Pie chart", "B) Line graph", "C) Map", "D) Timeline"],
                answer: "A"
            },
            {
                question: "If you want to see how the number of rainy days changes each month, which graph should you use?",
                options: ["A) Line graph", "B) Tally chart", "C) Pie chart", "D) Bar graph"],
                answer: "A"
            },
            {
                question: "What type of graph shows data in columns going up and down?",
                options: ["A) Line graph", "B) Tally chart", "C) Pie chart", "D) Bar graph"],
                answer: "D"
            },
            {
                question: "If you want to show the parts of a whole, like slices of a pizza, which graph would be best?",
                options: ["A) Pie chart", "B) Line graph", "C) Bar graph", "D) Tally chart"],
                answer: "A"
            },
            {
                question: "Sarah counted the number of books she read every month. What graph should she use to show the changes over the year?",
                options: ["A) Bar graph", "B) Line graph", "C) Pie chart", "D) Tally chart"],
                answer: "B"
            },
            {
                question: "Which graph can show data with X and Y coordinates?",
                options: ["A) Map", "B) Pie chart", "C) Line graph", "D) Bar graph"],
                answer: "C"
            },
            {
                question: "If a school wants to show the number of students in each grade, which graph is best?",
                options: ["A) Line graph", "B) Pie chart", "C) Bar graph", "D) Map"],
                answer: "C"
            },
            {
                question: "For showing data that doesn't change over time, which graph should you avoid?",
                options: ["A) Pie chart", "B) Line graph", "C) Tally chart", "D) Bar graph"],
                answer: "B"
            },
            {
                question: "If you want to show the percentage of students who passed a test, which graph would be best?",
                options: ["A) Line graph", "B) Pie chart", "C) Bar graph", "D) Tally chart"],
                answer: "B"
            },
            {
                question: "Which graph is best for showing data that represents counts or amounts, like the number of toys in different boxes?",
                options: ["A) Tally chart", "B) Pie chart", "C) Bar graph", "D) Line graph"],
                answer: "C"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            if (questionObject.options.length === 3) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
            } else if (questionObject.options.length === 4) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-D').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
                document.getElementById('option-D').innerText = questionObject.options[3];
            } else {
                document.getElementById('option-C').style.display = 'none';
                document.getElementById('option-D').style.display = 'none';
            }
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>

## Grade 5 Calgary Questions. 


U1 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) 579,801</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) 580,801</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) 578,801</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) 579,800</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "What is the sum of 345,678 and 234,123?",
                options: ["A) 579,801", "B) 580,801", "C) 578,801", "D) 579,800"],
                answer: "A"
            },
            {
                question: "If you subtract 123,456 from 654,321, what is the result?",
                options: ["A) 530,865", "B) 530,765", "C) 530,965", "D) 530,855"],
                answer: "A"
            },
            {
                question: "A charity has $450,000.90 in funds and receives a donation of $123,456.10. How much do they have now?",
                options: ["A) $573,457.00", "B) $573,457.90", "C) $573,456.90", "D) $573,457.10"],
                answer: "B"
            },
            {
                question: "John has $345,123.45. He spent $123,123.45. How much money does he have left?",
                options: ["A) $222,000.00", "B) $221,999.99", "C) $222,000.01", "D) $221,999.00"],
                answer: "B"
            },
            {
                question: "Add 512,345.67 and 234,654.32.",
                options: ["A) 747,000.00", "B) 746,999.99", "C) 747,000.01", "D) 746,999.00"],
                answer: "A"
            },
            {
                question: "What is the result of 123 multiplied by 45?",
                options: ["A) 5,535", "B) 6,535", "C) 5,445", "D) 5,635"],
                answer: "C"
            },
            {
                question: "If you multiply 321 by 12, what is the product?",
                options: ["A) 3,852", "B) 3,942", "C) 3,752", "D) 3,952"],
                answer: "A"
            },
            {
                question: "Calculate the product of 456 and 21.",
                options: ["A) 9,576", "B) 8,576", "C) 9,476", "D) 9,676"],
                answer: "C"
            },
            {
                question: "A factory produces 312 toys every day. If they operate for 15 days, how many toys will they produce?",
                options: ["A) 4,680", "B) 4,780", "C) 4,580", "D) 4,880"],
                answer: "A"
            },
            {
                question: "What's the result of 567 multiplied by 34?",
                options: ["A) 19,278", "B) 19,178", "C) 19,378", "D) 19,078"],
                answer: "B"
            },
            {
                question: "If you add 123,456 to 654,321 and then subtract 100,000, what is the final result?",
                options: ["A) 677,777", "B) 677,677", "C) 678,777", "D) 677,877"],
                answer: "D"
            },
            {
                question: "Sarah bought 234 apples and wants to distribute them in packs of 12. How many packs can she make?",
                options: ["A) 19.5", "B) 20.5", "C) 18.5", "D) 21.5"],
                answer: "B"
            },
            {
                question: "Tom had $345,678. He spent $123,456 and then earned $50,000. How much does he have now?",
                options: ["A) 272,222", "B) 271,222", "C) 272,322", "D) 271,322"],
                answer: "D"
            },
            {
                question: "A manufacturer produces 312 pieces of a product every day. If they sell them in packs of 24, how many packs do they produce daily?",
                options: ["A) 13", "B) 14", "C) 12", "D) 15"],
                answer: "C"
            },
            {
                question: "Multiply 789 by 23 and then subtract 5,000. What's the result?",
                options: ["A) 13,147", "B) 18,147", "C) 17,147", "D) 12,147"],
                answer: "C"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            if (questionObject.options.length === 3) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
            } else if (questionObject.options.length === 4) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-D').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
                document.getElementById('option-D').innerText = questionObject.options[3];
            } else {
                document.getElementById('option-C').style.display = 'none';
                document.getElementById('option-D').style.display = 'none';
            }
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>



U2 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-A">A) 5,525</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) 5,625</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) 5,735</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) 5,535</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "What is the product of 123 and 45?",
                options: ["A) 5,525", "B) 5,625", "C) 5,735", "D) 5,535"],
                answer: "D"
            },
            {
                question: "Multiply 145 by 32.",
                options: ["A) 4,640", "B) 4,540", "C) 4,740", "D) 4,840"],
                answer: "A"
            },
            {
                question: "A store sells 256 apples each day. If they sell them for 14 days, how many apples are sold in total?",
                options: ["A) 3,578", "B) 3,468", "C) 3,678", "D) 3,788"],
                answer: "D"
            },
            {
                question: "What is the result of 312 multiplied by 25?",
                options: ["A) 7,800", "B) 7,900", "C) 7,700", "D) 7,600"],
                answer: "A"
            },
            {
                question: "Find the product of 458 and 12.",
                options: ["A) 5,496", "B) 5,596", "C) 5,396", "D) 5,696"],
                answer: "C"
            },
            {
                question: "A company packages 321 toys in each box. If a store orders 15 boxes, how many toys did they order in total?",
                options: ["A) 4,815", "B) 4,915", "C) 4,715", "D) 4,615"],
                answer: "A"
            },
            {
                question: "Multiply 237 by 43.",
                options: ["A) 10,191", "B) 10,091", "C) 10,291", "D) 10,391"],
                answer: "D"
            },
            {
                question: "If 125 t-shirts are sold each week for 16 weeks, how many t-shirts are sold in total?",
                options: ["A) 2,000", "B) 2,100", "C) 1,900", "D) 2,200"],
                answer: "B"
            },
            {
                question: "What's the result when you multiply 567 by 22?",
                options: ["A) 12,474", "B) 12,574", "C) 12,374", "D) 12,274"],
                answer: "C"
            },
            {
                question: "A bakery produces 316 cookies per batch. If they make 13 batches in a day, how many cookies are produced?",
                options: ["A) 4,108", "B) 4,208", "C) 4,008", "D) 4,308"],
                answer: "B"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            if (questionObject.options.length === 3) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
            } else if (questionObject.options.length === 4) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-D').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
                document.getElementById('option-D').innerText = questionObject.options[3];
            } else {
                document.getElementById('option-C').style.display = 'none';
                document.getElementById('option-D').style.display = 'none';
            }
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>



U3 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            color: #000033;
            background-color: white;
        }
        .header {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100px;
            background-color: white;
            color: #000033;
            font-size: 2rem;
            border-bottom: 2px solid #000033;
        }
        .header h1 {
            color: #000033;
        }
        .footer {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px;
            background-color: #f9f9f9;
            color: #000033;
            font-size: 1rem;
        }
        .question-container {
            padding: 40px;
            text-align: center;
        }
        .question-box {
            border: 2px solid #000033;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        .options-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .option {
            padding: 10px;
            margin: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid #000033;
            text-align: center;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .option:hover {
            background-color: #000033;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1 style="color: #000033;">Numera</h1>
    </div>
    <div class="question-container">
        <div class="question-box">
            <h3 id="question-text">Loading question...</h3>
            <div class="options-container">
                <div class="option" onclick="checkAnswer('A')">
                    <p id="option-A">A) 1/4</p>
                </div>
                <div class="option" onclick="checkAnswer('B')">
                    <p id="option-B">B) 3/8</p>
                </div>
                <div class="option" onclick="checkAnswer('C')">
                    <p id="option-C">C) 3/4</p>
                </div>
                <div class="option" onclick="checkAnswer('D')">
                    <p id="option-D">D) 1/2</p>
                </div>
            </div>
        </div>
    </div>
    <div class="footer">
        <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
        const questionsDatabase = [
            {
                question: "What is 1/4 + 2/4?",
                options: ["A) 1/4", "B) 3/8", "C) 3/4", "D) 1/2"],
                answer: "C"
            },
            {
                question: "Lily had 3/5 of a cake and ate 1/5. How much cake does she have left?",
                options: ["A) 1/5", "B) 2/5", "C) 4/5", "D) 3/5"],
                answer: "B"
            },
            {
                question: "If you combine 5/6 and 1/6 of a chocolate bar, do you have a whole bar?",
                options: ["A) Yes", "B) No"],
                answer: "A"
            },
            {
                question: "Sarah has 7/8 of her juice left. If she drinks another 1/8, how much will she have left?",
                options: ["A) 1/8", "B) 3/4", "C) 6/8", "D) 0"],
                answer: "C"
            },
            {
                question: "Add 2/10 to 3/10.",
                options: ["A) 3/10", "B) 1/5", "C) 4/10", "D) 5/10"],
                answer: "D"
            },
            {
                question: "Brian shared 5/12 of his candy with Jenny and kept the rest. How much candy did Brian keep?",
                options: ["A) 1/12", "B) 6/12", "C) 7/12", "D) 5/12"],
                answer: "C"
            },
            {
                question: "Calculate the sum of 3/7 and 2/7.",
                options: ["A) 5/7", "B) 6/7", "C) 1/7", "D) 1"],
                answer: "A"
            },
            {
                question: "If Jake has 3/15 of a pie and eats 2/15, how much pie is remaining?",
                options: ["A) 5/15", "B) 2/15", "C) 1/15", "D) 3/5"],
                answer: "C"
            },
            {
                question: "When 11/13 is reduced by 2/13, what do you get?",
                options: ["A) 10/13", "B) 9/13", "C) 8/13", "D) 7/13"],
                answer: "B"
            },
            {
                question: "Maria has 3/5 of her allowance left. If she spends another 2/5, how much will she have left?",
                options: ["A) 5/5", "B) 2/5", "C) 1/5", "D) 0"],
                answer: "C"
            },
            {
                question: "Add 1/3 and 2/3.",
                options: ["A) 3/3", "B) 1/2", "C) 1/3", "D) 2/6"],
                answer: "A"
            },
            {
                question: "Oscar had 4/9 of a pizza and shared 3/9 with his brother. How much pizza does Oscar have now?",
                options: ["A) 1/9", "B) 2/9", "C) 3/9", "D) 5/9"],
                answer: "A"
            },
            {
                question: "Find the difference between 5/8 and 3/8.",
                options: ["A) 3/8", "B) 2/8", "C) 1/8", "D) 6/8"],
                answer: "B"
            },
            {
                question: "If you fill a jar 6/10 full with honey and use 1/10 for a recipe, how full is the jar now?",
                options: ["A) 7/10", "B) 5/10", "C) 4/10", "D) 8/10"],
                answer: "B"
            },
            {
                question: "Combine 7/14 with 5/14.",
                options: ["A) 6/14", "B) 8/14", "C) 12/14", "D) 1"],
                answer: "C"
            },
            {
                question: "Noah read 5/6 of a book. If he reads another 1/6, will he finish the book?",
                options: ["A) Yes", "B) No"],
                answer: "A"
            },
            {
                question: "Subtract 7/11 from 10/11.",
                options: ["A) 3/11", "B) 4/11", "C) 2/11", "D) 5/11"],
                answer: "A"
            },
            {
                question: "If you have 3/4 of a chocolate bar and share 1/4 with a friend, how much chocolate will you have left?",
                options: ["A) 1/4", "B) 2/4", "C) 3/4", "D) 4/4"],
                answer: "B"
            }
        ]
        
        let currentQuestionIndex = 0;

        function displayNextQuestion() {
            const questionObject = questionsDatabase[currentQuestionIndex];
            document.getElementById('question-text').innerText = questionObject.question;
            document.getElementById('option-A').innerText = questionObject.options[0];
            document.getElementById('option-B').innerText = questionObject.options[1];
            if (questionObject.options.length === 3) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
            } else if (questionObject.options.length === 4) {
                document.getElementById('option-C').style.display = 'block';
                document.getElementById('option-D').style.display = 'block';
                document.getElementById('option-C').innerText = questionObject.options[2];
                document.getElementById('option-D').innerText = questionObject.options[3];
            } else {
                document.getElementById('option-C').style.display = 'none';
                document.getElementById('option-D').style.display = 'none';
            }
        }

        function checkAnswer(userAnswer) {
            const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
            if (userAnswer === correctAnswer) {
                currentQuestionIndex++;
                if (currentQuestionIndex < questionsDatabase.length) {
                    displayNextQuestion();
                } else {
                    alert('Congratulations! You have completed all the questions.');
                }
            } else {
                alert('Incorrect Answer. Try Again!');
            }
        }

        displayNextQuestion();
    </script>
</body>
</html>


U4 

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Numera - Challenge Yourself</title>
    <style>
      body {
        font-family: "Georgia", serif;
        margin: 0;
        padding: 0;
        color: #000033;
        background-color: white;
      }
      .header {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100px;
        background-color: white;
        color: #000033;
        font-size: 2rem;
        border-bottom: 2px solid #000033;
      }
      .header h1 {
        color: #000033;
      }
      .footer {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        background-color: #f9f9f9;
        color: #000033;
        font-size: 1rem;
      }
      .question-container {
        padding: 40px;
        text-align: center;
      }
      .question-box {
        border: 2px solid #000033;
        padding: 20px;
        border-radius: 15px;
        margin: 20px 0;
      }
      .options-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
      }
      .option {
        padding: 10px;
        margin: 10px;
        width: 50%;
        border-radius: 15px;
        border: 2px solid #000033;
        text-align: center;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s ease;
      }
      .option:hover {
        background-color: #000033;
        color: white;
      }
    </style>
  </head>
  <body>
    <div class="header">
      <h1>Numera</h1>
    </div>
    <div class="question-container">
      <div class="question-box">
        <h3 id="question-text">Loading question...</h3>
        <div class="options-container">
          <div class="option" onclick="checkAnswer('A')">
            <p id="option-A"></p>
          </div>
          <div class="option" onclick="checkAnswer('B')">
            <p id="option-B"></p>
          </div>
          <div class="option" onclick="checkAnswer('C')">
            <p id="option-C"></p>
          </div>
          <div class="option" onclick="checkAnswer('D')">
            <p id="option-D"></p>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
      const questionsDatabase = [
        {
          question: "What is x+2=5?",
          options: ["A) 2", "B) 3", "C) 4", "D) 5"],
          answer: "B"
        },
        {
          question: "If John has j toys and he gets 1 more, how many toys does he have now?",
          options: ["A) j+1", "B) j-1", "C) jx2", "D) j/2"],
          answer: "A"
        },
        {
          question: "Solve for z in the equation z+3=6.",
          options: ["A) 2", "B) 3", "C) 4", "D) 9"],
          answer: "A"
        },
        {
          question: "Find the value of m in m+4=7.",
          options: ["A) 1", "B) 2", "C) 3", "D) 4"],
          answer: "C"
        },
        {
          question: "If b is the number of balls, and you have 5, what is b?",
          options: ["A) 1", "B) 3", "C) 5", "D) 6"],
          answer: "C"
        },
        {
          question: "Solve for n in the equation 2+n=4.",
          options: ["A) 1", "B) 2", "C) 6", "D) 3"],
          answer: "B"
        },
        {
          question: "Evaluate p+2 when p=1.",
          options: ["A) 2", "B) 3", "C) 4", "D) 5"],
          answer: "B"
        },
        {
          question: "If a tree has t apples and 1 falls, which expression represents the remaining apples?",
          options: ["A) t+1", "B) t-1", "C) 2t", "D) t/2"],
          answer: "B"
        },
        {
          question: "What is the value of s if s+1=3?",
          options: ["A) 1", "B) 2", "C) 3", "D) 4"],
          answer: "B"
        },
        {
          question: "If d is the number of days in a week, what is d?",
          options: ["A) 5", "B) 6", "C) 7", "D) 8"],
          answer: "C"
        },
        {
          question: "Solve for w in the equation w+0=w.",
          options: ["A) 0", "B) 1", "C) 2", "D) 3"],
          answer: "A"
        },
        {
          question: "What is the value of k if k+3=5?",
          options: ["A) 1", "B) 2", "C) 3", "D) 8"],
          answer: "B"
        },
        {
          question: "Solve for a in the equation a+2=4.",
          options: ["A) 1", "B) 2", "C) 3", "D) 4"],
          answer: "B"
        },
        {
          question: "Evaluate h+2 when h=0.",
          options: ["A) 0", "B) 1", "C) 2", "D) 3"],
          answer: "C"
        },
        {
          question: "What is the value of r if r+1=2?",
          options: ["A) 0", "B) 1", "C) 3", "D) 4"],
          answer: "B"
        },
        {
          question: "Solve for e in the equation e+0=e.",
          options: ["A) 0", "B) 1", "C) 2", "D) 3"],
          answer: "A"
        },
        {
          question: "Evaluate h+2 when h=0.",
          options: ["A) 0", "B) 1", "C) 2", "D) 3"],
          answer: "C"
        }
      ];

      let currentQuestionIndex = 0;
      const questionText = document.getElementById('question-text');
      const optionA = document.getElementById('option-A');
      const optionB = document.getElementById('option-B');
      const optionC = document.getElementById('option-C');
      const optionD = document.getElementById('option-D');

      function displayQuestion(questionIndex) {
          const question = questionsDatabase[questionIndex];
          questionText.innerText = question.question;
          optionA.innerText = question.options[0];
          optionB.innerText = question.options[1];
          if(question.options[2]) {
              optionC.style.display = "block";
              optionC.innerText = question.options[2];
          }
          else
            optionC.style.display = "none";

          if(question.options[3]) {
              optionD.style.display = "block";
              optionD.innerText = question.options[3];
          }
          else 
            optionD.style.display = "none";
      }

      function checkAnswer(userAnswer) {
          const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
          if(userAnswer === correctAnswer) {
              alert("Correct answer!");
              currentQuestionIndex++;
              if(currentQuestionIndex < questionsDatabase.length) {
                  displayQuestion(currentQuestionIndex);
              }
              else {
                  alert("Congratulations, you've completed the quiz!");
              }
          }
          else {
              alert("Incorrect answer, try again!");
          }
      }

      displayQuestion(currentQuestionIndex);
    </script>
  </body>
</html>



U5 


<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Numera - Challenge Yourself</title>
    <style>
      body {
        font-family: "Georgia", serif;
        margin: 0;
        padding: 0;
        color: #000033;
        background-color: white;
      }
      .header {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100px;
        background-color: white;
        color: #000033;
        font-size: 2rem;
        border-bottom: 2px solid #000033;
      }
      .header h1 {
        color: #000033;
      }
      .footer {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        background-color: #f9f9f9;
        color: #000033;
        font-size: 1rem;
      }
      .question-container {
        padding: 40px;
        text-align: center;
      }
      .question-box {
        border: 2px solid #000033;
        padding: 20px;
        border-radius: 15px;
        margin: 20px 0;
      }
      .options-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
      }
      .option {
        padding: 10px;
        margin: 10px;
        width: 50%;
        border-radius: 15px;
        border: 2px solid #000033;
        text-align: center;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s ease;
      }
      .option:hover {
        background-color: #000033;
        color: white;
      }
    </style>
  </head>
  <body>
    <div class="header">
      <h1>Numera</h1>
    </div>
    <div class="question-container">
      <div class="question-box">
        <h3 id="question-text">Loading question...</h3>
        <div class="options-container">
          <div class="option" onclick="checkAnswer('A')">
            <p id="option-A"></p>
          </div>
          <div class="option" onclick="checkAnswer('B')">
            <p id="option-B"></p>
          </div>
          <div class="option" onclick="checkAnswer('C')">
            <p id="option-C"></p>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
      const questionsDatabase = [
        {
          question: "Which shape always has at least one line of symmetry?",
          options: ["A) Circle", "B) Scalene triangle", "C) Parallelogram"],
          answer: "A"
        },
        {
          question: "How many lines of symmetry does a square have?",
          options: ["A) One", "B) Two", "C) Four"],
          answer: "C"
        },
        {
          question: "If a shape looks the same after being flipped over a line, it has...",
          options: ["A) Rotation", "B) Line symmetry", "C) No symmetry"],
          answer: "B"
        },
        {
          question: "How many lines of symmetry does a rectangle have?",
          options: ["A) One", "B) Two", "C) Three"],
          answer: "B"
        },
        {
          question: "Which of the following shapes has no line of symmetry?",
          options: ["A) Equilateral triangle", "B) Circle", "C) Scalene triangle"],
          answer: "C"
        },
        {
          question: "How many lines of symmetry does an isosceles triangle have?",
          options: ["A) None", "B) One", "C) Two"],
          answer: "B"
        },
        {
          question: "Which letter of the alphabet does NOT have a vertical line of symmetry?",
          options: ["A) M", "B) O", "C) P"],
          answer: "A"
        },
        {
          question: "If a shape has rotational symmetry, it can...",
          options: ["A) Look the same after a turn", "B) Look the same when flipped", "C) Both A and B"],
          answer: "A"
        },
        {
          question: "An equilateral triangle has how many lines of symmetry?",
          options: ["A) One", "B) Two", "C) Three"],
          answer: "C"
        },
        {
          question: "How many lines of symmetry does an oval have?",
          options: ["A) None", "B) One", "C) Two"],
          answer: "C"
        },
        {
          question: "Which of the following shapes does NOT have a horizontal line of symmetry?",
          options: ["A) Triangle", "B) Square", "C) Trapezoid"],
          answer: "A"
        },
        {
          question: "When a heart shape is folded in half vertically, the two halves are...",
          options: ["A) Different", "B) Mirror images", "C) Overlapping"],
          answer: "B"
        },
        {
          question: "Which of the following has both horizontal and vertical lines of symmetry?",
          options: ["A) Right triangle", "B) Rhombus", "C) Pentagon"],
          answer: "B"
        },
        {
          question: "If a hexagon has six equal sides and angles, how many lines of symmetry does it have?",
          options: ["A) Three", "B) Six", "C) None"],
          answer: "B"
        },
        {
          question: "Which number has a vertical line of symmetry when written?",
          options: ["A) 2", "B) 3", "C) 8"],
          answer: "C"
        },
        {
          question: "Which of these shapes always looks the same no matter how you turn it?",
          options: ["A) Square", "B) Scalene triangle", "C) Parallelogram"],
          answer: "A"
        },
        {
          question: "If you fold a kite shape vertically down its middle, the two halves are...",
          options: ["A) Not symmetrical", "B) Symmetrical", "C) Overlapping but not symmetrical"],
          answer: "B"
        },
        {
          question: "How many lines of symmetry does a regular pentagon have?",
          options: ["A) None", "B) Five", "C) Ten"],
          answer: "B"
        },
        {
          question: "The capital letter 'H' has which types of symmetry?",
          options: ["A) Horizontal only", "B) Vertical only", "C) Both horizontal and vertical"],
          answer: "C"
        },
        {
          question: "Which shape cannot have rotational symmetry?",
          options: ["A) Circle", "B) Rectangle", "C) Both can have rotational symmetry"],
          answer: "B"
        }
      ];

      let currentQuestionIndex = 0;
      const questionText = document.getElementById('question-text');
      const optionA = document.getElementById('option-A');
      const optionB = document.getElementById('option-B');
      const optionC = document.getElementById('option-C');
      const optionD = document.getElementById('option-D');

      function displayQuestion(questionIndex) {
          const question = questionsDatabase[questionIndex];
          questionText.innerText = question.question;
          optionA.innerText = question.options[0];
          optionB.innerText = question.options[1];
          if(question.options[2]) {
              optionC.style.display = "block";
              optionC.innerText = question.options[2];
          }
          else
            optionC.style.display = "none";

          if(question.options[3]) {
              optionD.style.display = "block";
              optionD.innerText = question.options[3];
          }
          else 
            optionD.style.display = "none";
      }

      function checkAnswer(userAnswer) {
          const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
          if(userAnswer === correctAnswer) {
              alert("Correct answer!");
              currentQuestionIndex++;
              if(currentQuestionIndex < questionsDatabase.length) {
                  displayQuestion(currentQuestionIndex);
              }
              else {
                  alert("Congratulations, you've completed the quiz!");
              }
          }
          else {
              alert("Incorrect answer, try again!");
          }
      }

      displayQuestion(currentQuestionIndex);
    </script>
  </body>
</html>


U6 


<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Numera - Challenge Yourself</title>
    <style>
      body {
        font-family: "Georgia", serif;
        margin: 0;
        padding: 0;
        color: #000033;
        background-color: white;
      }
      .header {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100px;
        background-color: white;
        color: #000033;
        font-size: 2rem;
        border-bottom: 2px solid #000033;
      }
      .header h1 {
        color: #000033;
      }
      .footer {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        background-color: #f9f9f9;
        color: #000033;
        font-size: 1rem;
      }
      .question-container {
        padding: 40px;
        text-align: center;
      }
      .question-box {
        border: 2px solid #000033;
        padding: 20px;
        border-radius: 15px;
        margin: 20px 0;
      }
      .options-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
      }
      .option {
        padding: 10px;
        margin: 10px;
        width: 50%;
        border-radius: 15px;
        border: 2px solid #000033;
        text-align: center;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s ease;
      }
      .option:hover {
        background-color: #000033;
        color: white;
      }
    </style>
  </head>
  <body>
    <div class="header">
      <h1>Numera</h1>
    </div>
    <div class="question-container">
      <div class="question-box">
        <h3 id="question-text">Loading question...</h3>
        <div class="options-container">
          <div class="option" onclick="checkAnswer('A')">
            <p id="option-A"></p>
          </div>
          <div class="option" onclick="checkAnswer('B')">
            <p id="option-B"></p>
          </div>
          <div class="option" onclick="checkAnswer('C')">
            <p id="option-C"></p>
          </div>
          <div class="option" onclick="checkAnswer('D')">
            <p id="option-D"></p>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
      const questionsDatabase = [
        {
          question: "Which shape always has at least one line of symmetry?",
          options: ["A) Circle", "B) Scalene triangle", "C) Parallelogram"],
          answer: "A"
        },
        {
          question: "How many lines of symmetry does a square have?",
          options: ["A) One", "B) Two", "C) Four"],
          answer: "C"
        },
        {
          question: "If a shape looks the same after being flipped over a line, it has...",
          options: ["A) Rotation", "B) Line symmetry", "C) No symmetry"],
          answer: "B"
        },
        {
          question: "How many lines of symmetry does a rectangle have?",
          options: ["A) One", "B) Two", "C) Three"],
          answer: "B"
        },
        {
          question: "Which of the following shapes has no line of symmetry?",
          options: ["A) Equilateral triangle", "B) Circle", "C) Scalene triangle"],
          answer: "C"
        },
        {
          question: "How many lines of symmetry does an isosceles triangle have?",
          options: ["A) None", "B) One", "C) Two"],
          answer: "B"
        },
        {
          question: "Which letter of the alphabet does NOT have a vertical line of symmetry?",
          options: ["A) M", "B) O", "C) P"],
          answer: "A"
        },
        {
          question: "If a shape has rotational symmetry, it can...",
          options: ["A) Look the same after a turn", "B) Look the same when flipped", "C) Both A and B"],
          answer: "A"
        },
        {
          question: "An equilateral triangle has how many lines of symmetry?",
          options: ["A) One", "B) Two", "C) Three"],
          answer: "C"
        },
        {
          question: "How many lines of symmetry does an oval have?",
          options: ["A) None", "B) One", "C) Two"],
          answer: "C"
        },
        {
          question: "Which of the following shapes does NOT have a horizontal line of symmetry?",
          options: ["A) Triangle", "B) Square", "C) Trapezoid"],
          answer: "A"
        },
        {
          question: "When a heart shape is folded in half vertically, the two halves are...",
          options: ["A) Different", "B) Mirror images", "C) Overlapping"],
          answer: "B"
        },
        {
          question: "Which of the following has both horizontal and vertical lines of symmetry?",
          options: ["A) Right triangle", "B) Rhombus", "C) Pentagon"],
          answer: "B"
        },
        {
          question: "If a hexagon has six equal sides and angles, how many lines of symmetry does it have?",
          options: ["A) Three", "B) Six", "C) None"],
          answer: "B"
        },
        {
          question: "Which number has a vertical line of symmetry when written?",
          options: ["A) 2", "B) 3", "C) 8"],
          answer: "C"
        },
        {
          question: "Which of these shapes always looks the same no matter how you turn it?",
          options: ["A) Square", "B) Scalene triangle", "C) Parallelogram"],
          answer: "A"
        },
        {
          question: "If you fold a kite shape vertically down its middle, the two halves are...",
          options: ["A) Not symmetrical", "B) Symmetrical", "C) Overlapping but not symmetrical"],
          answer: "B"
        },
        {
          question: "How many lines of symmetry does a regular pentagon have?",
          options: ["A) None", "B) Five", "C) Ten"],
          answer: "B"
        },
        {
          question: "The capital letter 'H' has which types of symmetry?",
          options: ["A) Horizontal only", "B) Vertical only", "C) Both horizontal and vertical"],
          answer: "C"
        },
        {
          question: "Which shape cannot have rotational symmetry?",
          options: ["A) Circle", "B) Rectangle", "C) Both can have rotational symmetry"],
          answer: "B"
        },
        {
          question: "What is the area of a rectangle that has a length of 5 cm and a width of 3 cm?",
          options: ["A) 8 cm²", "B) 15 cm²", "C) 16 cm²", "D) 20 cm²"],
          answer: "B"
        },
        {
          question: "A rectangle's length is 10 cm and its width is 4 cm. What is its perimeter?",
          options: ["A) 28 cm", "B) 14 cm", "C) 40 cm", "D) 48 cm"],
          answer: "D"
        },
        {
          question: "If a rectangle has an area of 36 cm² and its length is 6 cm, what is its width?",
          options: ["A) 5 cm", "B) 6 cm", "C) 7 cm", "D) 30 cm"],
          answer: "A"
        },
        {
          question: "The perimeter of a rectangle is 24 cm. If its width is 5 cm, what is its length?",
          options: ["A) 7 cm", "B) 14 cm", "C) 9 cm", "D) 4 cm"],
          answer: "C"
        },
        {
          question: "A rectangle's width is half its length. If the area is 18 cm², what is the length?",
          options: ["A) 3 cm", "B) 4.5 cm", "C) 6 cm", "D) 9 cm"],
          answer: "C"
        },
        {
          question: "What is the area of a square with side length 5 cm?",
          options: ["A) 20 cm²", "B) 10 cm²", "C) 25 cm²", "D) 15 cm²"],
          answer: "C"
        },
        {
          question: "How much longer is the perimeter than the area of a 4 cm by 7 cm rectangle?",
          options: ["A) 2 cm", "B) 4 cm", "C) 6 cm", "D) 10 cm"],
          answer: "C"
        },
        {
          question: "A rectangle's length is increased by 2 cm and its width is reduced by 1 cm. If the new perimeter is 20 cm, what was the original length?",
          options: ["A) 6 cm", "B) 5 cm", "C) 7 cm", "D) 4 cm"],
          answer: "C"
        },
        {
          question: "The difference between a rectangle's length and width is 3 cm. If the perimeter is 26 cm, what is the smaller side?",
          options: ["A) 4 cm", "B) 5 cm", "C) 7 cm", "D) 10 cm"],
          answer: "A"
        },
        {
          question: "If the area of a rectangle is equal to its perimeter and the width is 3 cm, what is the length?",
          options: ["A) 6 cm", "B) 12 cm", "C) 3 cm", "D) 9 cm"],
          answer: "B"
        },
        {
          question: "A rectangular garden has a perimeter of 48 m and a length of 15 m. How wide is the garden?",
          options: ["A) 8 m", "B) 9 m", "C) 10 m", "D) 11 m"],
          answer: "B"
        },
        {
          question: "A picture frame has an area of 72 cm². If the frame is 12 cm long, how wide is it?",
          options: ["A) 5 cm", "B) 6 cm", "C) 7 cm", "D) 60 cm"],
          answer: "B"
        },
        {
          question: "A rectangular playground's width is 3/4 of its length. If its perimeter is 56 m, what is the playground's width?",
          options: ["A) 10 m", "B) 12 m", "C) 14 m", "D) 16 m"],
          answer: "A"
        },
        {
          question: "The area of a rectangle is 45 cm². If its width is 5 cm, how long is it?",
          options: ["A) 8 cm", "B) 9 cm", "C) 10 cm", "D) 7 cm"],
          answer: "B"
        },
        {
          question: "A piece of paper has an area of 81 cm². If its width is 9 cm, what's its perimeter?",
          options: ["A) 36 cm", "B) 38 cm", "C) 42 cm", "D) 44 cm"],
          answer: "C"
        }
      ];

      let currentQuestionIndex = 0;
      const questionText = document.getElementById('question-text');
      const optionA = document.getElementById('option-A');
      const optionB = document.getElementById('option-B');
      const optionC = document.getElementById('option-C');
      const optionD = document.getElementById('option-D');

      function displayQuestion(questionIndex) {
          const question = questionsDatabase[questionIndex];
          questionText.innerText = question.question;
          optionA.innerText = question.options[0];
          optionB.innerText = question.options[1];
          if(question.options[2]) {
              optionC.style.display = "block";
              optionC.innerText = question.options[2];
          }
          else
            optionC.style.display = "none";

          if(question.options[3]) {
              optionD.style.display = "block";
              optionD.innerText = question.options[3];
          }
          else 
            optionD.style.display = "none";
      }

      function checkAnswer(userAnswer) {
          const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
          if(userAnswer === correctAnswer) {
              alert("Correct answer!");
              currentQuestionIndex++;
              if(currentQuestionIndex < questionsDatabase.length) {
                  displayQuestion(currentQuestionIndex);
              }
              else {
                  alert("Congratulations, you've completed the quiz!");
              }
          }
          else {
              alert("Incorrect answer, try again!");
          }
      }

      displayQuestion(currentQuestionIndex);
    </script>
  </body>
</html>.  

## Grade 6 Calgary Questions.


U1 


<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Numera - Challenge Yourself</title>
    <style>
      body {
        font-family: "Georgia", serif;
        margin: 0;
        padding: 0;
        color: #000033;
        background-color: white;
      }
      .header {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100px;
        background-color: white;
        color: #000033;
        font-size: 2rem;
        border-bottom: 2px solid #000033;
      }
      .header h1 {
        color: #000033;
      }
      .footer {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        background-color: #f9f9f9;
        color: #000033;
        font-size: 1rem;
      }
      .question-container {
        padding: 40px;
        text-align: center;
      }
      .question-box {
        border: 2px solid #000033;
        padding: 20px;
        border-radius: 15px;
        margin: 20px 0;
      }
      .options-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
      }
      .option {
        padding: 10px;
        margin: 10px;
        width: 50%;
        border-radius: 15px;
        border: 2px solid #000033;
        text-align: center;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s ease;
      }
      .option:hover {
        background-color: #000033;
        color: white;
      }
    </style>
  </head>
  <body>
    <div class="header">
      <h1>Numera</h1>
    </div>
    <div class="question-container">
      <div class="question-box">
        <h3 id="question-text">Loading question...</h3>
        <div class="options-container">
          <div class="option" onclick="checkAnswer('A')">
            <p id="option-A"></p>
          </div>
          <div class="option" onclick="checkAnswer('B')">
            <p id="option-B"></p>
          </div>
          <div class="option" onclick="checkAnswer('C')">
            <p id="option-C"></p>
          </div>
          <div class="option" onclick="checkAnswer('D')">
            <p id="option-D"></p>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
      const questionsDatabase = [
        {
          question: "Solve: 5 + (6 x 4) = ?",
          options: ["A) 44", "B) 29", "C) 26", "D) 24"],
          answer: "D"
        },
        {
          question: "What is the value of 18 ÷ (3 x 2)?",
          options: ["A) 3", "B) 6", "C) 9", "D) 12"],
          answer: "A"
        },
        {
          question: "Solve: 12 + 18 ÷ 2 = ?",
          options: ["A) 21", "B) 33", "C) 27", "D) 15"],
          answer: "C"
        },
        {
          question: "Determine: 15 - (3 x 2 + 4) = ?",
          options: ["A) 3", "B) 7", "C) 5", "D) 1"],
          answer: "D"
        },
        {
          question: "Calculate: 9 x (5 - 3) = ?",
          options: ["A) 18", "B) 27", "C) 15", "D) 12"],
          answer: "A"
        },
        {
          question: "If (6 x 5) - 12 ÷ 2 = X, what is X?",
          options: ["A) 24", "B) 27", "C) 18", "D) 30"],
          answer: "C"
        },
        {
          question: "Solve for Y: Y = 10 x (4 + 2) - 20 ÷ 2",
          options: ["A) 50", "B) 60", "C) 40", "D) 30"],
          answer: "B"
        },
        {
          question: "Find the result of 48 ÷ (6 + 2) x 3.",
          options: ["A) 18", "B) 24", "C) 6", "D) 12"],
          answer: "B"
        },
        {
          question: "Solve: 12 x 3 + (16 ÷ 4) = ?",
          options: ["A) 38", "B) 40", "C) 36", "D) 42"],
          answer: "A"
        },
        {
          question: "If 6 + 12 x 2 = X, what is X?",
          options: ["A) 24", "B) 30", "C) 36", "D) 40"],
          answer: "D"
        },
        {
          question: "Calculate: 5 x 5 - (15 ÷ 3) = ?",
          options: ["A) 20", "B) 22", "C) 24", "D) 26"],
          answer: "C"
        },
        {
          question: "Determine: 20 ÷ (4 + 1) + 3 = ?",
          options: ["A) 7", "B) 8", "C) 6", "D) 5"],
          answer: "B"
        },
        {
          question: "Solve for Z: Z = 15 ÷ 3 x (2 + 4)",
          options: ["A) 30", "B) 25", "C) 20", "D) 10"],
          answer: "A"
        },
        {
          question: "Find the result of (5 + 5) x 3 ÷ 2.",
          options: ["A) 15", "B) 30", "C) 25", "D) 20"],
          answer: "C"
        },
        {
          question: "Calculate: 9 + 18 ÷ (3 + 3) = ?",
          options: ["A) 12", "B) 11", "C) 10", "D) 13"],
          answer: "B"
        }
      ];

      let currentQuestionIndex = 0;
      const questionText = document.getElementById('question-text');
      const optionA = document.getElementById('option-A');
      const optionB = document.getElementById('option-B');
      const optionC = document.getElementById('option-C');
      const optionD = document.getElementById('option-D');

      function displayQuestion(questionIndex) {
          const question = questionsDatabase[questionIndex];
          questionText.innerText = question.question;
          optionA.innerText = question.options[0];
          optionB.innerText = question.options[1];
          if(question.options[2]) {
              optionC.style.display = "block";
              optionC.innerText = question.options[2];
          }
          else
            optionC.style.display = "none";

          if(question.options[3]) {
              optionD.style.display = "block";
              optionD.innerText = question.options[3];
          }
          else 
            optionD.style.display = "none";
      }

      function checkAnswer(userAnswer) {
          const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
          if(userAnswer === correctAnswer) {
              alert("Correct answer!");
              currentQuestionIndex++;
              if(currentQuestionIndex < questionsDatabase.length) {
                  displayQuestion(currentQuestionIndex);
              }
              else {
                  alert("Congratulations, you've completed the quiz!");
              }
          }
          else {
              alert("Incorrect answer, try again!");
          }
      }

      displayQuestion(currentQuestionIndex);
    </script>
  </body>
</html>


U2 


<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Numera - Challenge Yourself</title>
    <style>
      body {
        font-family: "Georgia", serif;
        margin: 0;
        padding: 0;
        color: #000033;
        background-color: white;
      }
      .header {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100px;
        background-color: white;
        color: #000033;
        font-size: 2rem;
        border-bottom: 2px solid #000033;
      }
      .header h1 {
        color: #000033;
      }
      .footer {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        background-color: #f9f9f9;
        color: #000033;
        font-size: 1rem;
      }
      .question-container {
        padding: 40px;
        text-align: center;
      }
      .question-box {
        border: 2px solid #000033;
        padding: 20px;
        border-radius: 15px;
        margin: 20px 0;
      }
      .options-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
      }
      .option {
        padding: 10px;
        margin: 10px;
        width: 50%;
        border-radius: 15px;
        border: 2px solid #000033;
        text-align: center;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s ease;
      }
      .option:hover {
        background-color: #000033;
        color: white;
      }
    </style>
  </head>
  <body>
    <div class="header">
      <h1>Numera</h1>
    </div>
    <div class="question-container">
      <div class="question-box">
        <h3 id="question-text">Loading question...</h3>
        <div class="options-container">
          <div class="option" onclick="checkAnswer('A')">
            <p id="option-A"></p>
          </div>
          <div class="option" onclick="checkAnswer('B')">
            <p id="option-B"></p>
          </div>
          <div class="option" onclick="checkAnswer('C')">
            <p id="option-C"></p>
          </div>
          <div class="option" onclick="checkAnswer('D')">
            <p id="option-D"></p>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
      const questionsDatabase = [
        {
          question: "What is 1/3 of 9?",
          options: ["A) 1", "B) 3", "C) 2", "D) 4"],
          answer: "B"
        },
        {
          question: "Lisa bakes a cake and wants to divide it into 8 equal pieces. If she gives 3/4 of the cake to her friends, how many pieces did she give away?",
          options: ["A) 2 pieces", "B) 3 pieces", "C) 6 pieces", "D) 4 pieces"],
          answer: "C"
        },
        {
          question: "If 3/5 of a number is 18, what is the number?",
          options: ["A) 30", "B) 20", "C) 15", "D) 25"],
          answer: "A"
        },
        {
          question: "A tailor uses 4/7 yards of fabric to make a dress. If she makes 5 dresses, how much fabric does she use in total?",
          options: ["A) 20/7 yards", "B) 28/7 yards", "C) 5 yards", "D) 25/7 yards"],
          answer: "A"
        },
        {
          question: "Sam ate 2/6 of a pizza. If the pizza was cut into 12 slices, how many slices did Sam eat?",
          options: ["A) 2 slices", "B) 4 slices", "C) 6 slices", "D) 8 slices"],
          answer: "B"
        },
        {
          question: "What is 5/8 of 48?",
          options: ["A) 30", "B) 35", "C) 25", "D) 40"],
          answer: "A"
        },
        {
          question: "In a garden, 1/4 of the flowers are roses. If there are 20 roses, how many flowers are there in total?",
          options: ["A) 80", "B) 40", "C) 50", "D) 60"],
          answer: "A"
        },
        {
          question: "During a sale, Mike bought shirts that were 2/3 off the regular price. If the original price of a shirt was $30, how much did he pay for each shirt?",
          options: ["A) $10", "B) $20", "C) $15", "D) $25"],
          answer: "A"
        },
        {
          question: "In a classroom, 3/5 of the students are girls. If there are 15 girls, how many students are there in total?",
          options: ["A) 25 students", "B) 30 students", "C) 35 students", "D) 20 students"],
          answer: "A"
        },
        {
          question: "A recipe requires 1/2 cup of sugar for a cake. How much sugar is needed for 4 cakes?",
          options: ["A) 1 cup", "B) 2 cups", "C) 3 cups", "D) 4 cups"],
          answer: "B"
        },
        {
          question: "During a game, Harry scored 2/3 of the team's total points. If he scored 16 points, what were the team's total points?",
          options: ["A) 22 points", "B) 24 points", "C) 26 points", "D) 28 points"],
          answer: "B"
        },
        {
          question: "At a concert, 3/4 of the audience were adults. If 150 people were adults, how many people attended the concert?",
          options: ["A) 190", "B) 200", "C) 210", "D) 220"],
          answer: "B"
        },
        {
          question: "Lily bought 4 bracelets, each for 2/5 of her weekly allowance. If her allowance is $50, how much did she spend in total?",
          options: ["A) $20", "B) $30", "C) $40", "D) $50"],
          answer: "16"
        },
        {
          question: "In a race, John completed 5/6 of the track in 10 minutes. How long would it take him to finish the entire track?",
          options: ["A) 11 minutes", "B) 11.5 minutes", "C) 12 minutes", "D) 12.5 minutes"],
          answer: "12.5"
        },
        {
          question: "If 1/3 of a group of students went on a field trip and the number was 10, how many students are in the group?",
          options: ["A) 20 students", "B) 25 students", "C) 30 students", "D) 35 students"],
          answer: "30"
        }
      ];

      let currentQuestionIndex = 0;
      const questionText = document.getElementById('question-text');
      const optionA = document.getElementById('option-A');
      const optionB = document.getElementById('option-B');
      const optionC = document.getElementById('option-C');
      const optionD = document.getElementById('option-D');

      function displayQuestion(questionIndex) {
          const question = questionsDatabase[questionIndex];
          questionText.innerText = question.question;
          optionA.innerText = question.options[0];
          optionB.innerText = question.options[1];
          if(question.options[2]) {
              optionC.style.display = "block";
              optionC.innerText = question.options[2];
          }
          else
            optionC.style.display = "none";

          if(question.options[3]) {
              optionD.style.display = "block";
              optionD.innerText = question.options[3];
          }
          else 
            optionD.style.display = "none";
      }

      function checkAnswer(userAnswer) {
          const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
          if(userAnswer === correctAnswer) {
              alert("Correct answer!");
              currentQuestionIndex++;
              if(currentQuestionIndex < questionsDatabase.length) {
                  displayQuestion(currentQuestionIndex);
              }
              else {
                  currentQuestionIndex = 0;
                  displayQuestion(currentQuestionIndex);
              }
          }
          else {
              alert("Incorrect answer, try again!");
          }
      }

      displayQuestion(currentQuestionIndex);
    </script>
  </body>
</html>

U3 

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Numera - Challenge Yourself</title>
    <style>
      body {
        font-family: "Georgia", serif;
        margin: 0;
        padding: 0;
        color: #000033;
        background-color: white;
      }
      .header {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100px;
        background-color: white;
        color: #000033;
        font-size: 2rem;
        border-bottom: 2px solid #000033;
      }
      .header h1 {
        color: #000033;
      }
      .footer {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        background-color: #f9f9f9;
        color: #000033;
        font-size: 1rem;
      }
      .question-container {
        padding: 40px;
        text-align: center;
      }
      .question-box {
        border: 2px solid #000033;
        padding: 20px;
        border-radius: 15px;
        margin: 20px 0;
      }
      .options-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
      }
      .option {
        padding: 10px;
        margin: 10px;
        width: 50%;
        border-radius: 15px;
        border: 2px solid #000033;
        text-align: center;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s ease;
      }
      .option:hover {
        background-color: #000033;
        color: white;
      }
    </style>
  </head>
  <body>
    <div class="header">
      <h1>Numera</h1>
    </div>
    <div class="question-container">
      <div class="question-box">
        <h3 id="question-text">Loading question...</h3>
        <div class="options-container">
          <div class="option" onclick="checkAnswer('A')">
            <p id="option-A"></p>
          </div>
          <div class="option" onclick="checkAnswer('B')">
            <p id="option-B"></p>
          </div>
          <div class="option" onclick="checkAnswer('C')">
            <p id="option-C"></p>
          </div>
          <div class="option" onclick="checkAnswer('D')">
            <p id="option-D"></p>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
      const questionsDatabase = [
        {
          question: "What is 1/3 of 9?",
          options: ["A) 1", "B) 3", "C) 2", "D) 4"],
          answer: "C"
        },
        {
          question: "Lisa bakes a cake and wants to divide it into 8 equal pieces. If she gives 3/4 of the cake to her friends, how many pieces did she give away?",
          options: ["A) 2 pieces", "B) 3 pieces", "C) 6 pieces", "D) 4 pieces"],
          answer: "B"
        },
        {
          question: "If 3/5 of a number is 18, what is the number?",
          options: ["A) 30", "B) 20", "C) 15", "D) 25"],
          answer: "A"
        },
        {
          question: "A tailor uses 4/7 yards of fabric to make a dress. If she makes 5 dresses, how much fabric does she use in total?",
          options: ["A) 20/7 yards", "B) 28/7 yards", "C) 5 yards", "D) 25/7 yards"],
          answer: "B"
        },
        {
          question: "Sam ate 2/6 of a pizza. If the pizza was cut into 12 slices, how many slices did Sam eat?",
          options: ["A) 2 slices", "B) 4 slices", "C) 6 slices", "D) 8 slices"],
          answer: "C"
        },
        {
          question: "What is 5/8 of 48?",
          options: ["A) 30", "B) 35", "C) 25", "D) 40"],
          answer: "C"
        },
        {
          question: "In a garden, 1/4 of the flowers are roses. If there are 20 roses, how many flowers are there in total?",
          options: ["A) 80", "B) 40", "C) 50", "D) 60"],
          answer: "D"
        },
        {
          question: "During a sale, Mike bought shirts that were 2/3 off the regular price. If the original price of a shirt was $30, how much did he pay for each shirt?",
          options: ["A) $10", "B) $20", "C) $15", "D) $25"],
          answer: "A"
        },
        {
          question: "In a classroom, 3/5 of the students are girls. If there are 15 girls, how many students are there in total?",
          options: ["A) 25 students", "B) 30 students", "C) 35 students", "D) 20 students"],
          answer: "B"
        },
        {
          question: "A recipe requires 1/2 cup of sugar for a cake. How much sugar is needed for 4 cakes?",
          options: ["A) 1 cup", "B) 2 cups", "C) 3 cups", "D) 4 cups"],
          answer: "B"
        },
        {
          question: "During a game, Harry scored 2/3 of the team's total points. If he scored 16 points, what were the team's total points?",
          options: ["A) 22 points", "B) 24 points", "C) 26 points", "D) 28 points"],
          answer: "B"
        },
        {
          question: "At a concert, 3/4 of the audience were adults. If 150 people were adults, how many people attended the concert?",
          options: ["A) 190", "B) 200", "C) 210", "D) 220"],
          answer: "C"
        },
        {
          question: "Lily bought 4 bracelets, each for 2/5 of her weekly allowance. If her allowance is $50, how much did she spend in total?",
          options: ["A) $20", "B) $30", "C) $40", "D) $50"],
          answer: "C"
        },
        {
          question: "In a race, John completed 5/6 of the track in 10 minutes. How long would it take him to finish the entire track?",
          options: ["A) 11 minutes", "B) 11.5 minutes", "C) 12 minutes", "D) 12.5 minutes"],
          answer: "D"
        },
        {
          question: "If 1/3 of a group of students went on a field trip and the number was 10, how many students are in the group?",
          options: ["A) 20 students", "B) 25 students", "C) 30 students", "D) 35 students"],
          answer: "B"
        },
        {
          question: "A trapezoid has a top base of 6 meters, a bottom base of 10 meters, and a height of 4 meters. What is its area?",
          options: ["A) 32 sq.m", "B) 40 sq.m", "C) 64 sq.m", "D) 24 sq.m"],
          answer: "A"
        },
        {
          question: "A rectangular swimming pool is 25 meters long, 10 meters wide, and 2 meters deep. How many cubic meters of water can it hold?",
          options: ["A) 250 cu.m", "B) 500 cu.m", "C) 50 cu.m", "D) 70 cu.m"],
          answer: "B"
        },
        {
          question: "A triangle has an area of 42 sq.cm and a base of 14 cm. How tall is the triangle?",
          options: ["A) 3 cm", "B) 6 cm", "C) 9 cm", "D) 12 cm"],
          answer: "B"
        },
        {
          question: "A parallelogram has a base of 15 meters and a height of 5 meters. What is its area?",
          options: ["A) 50 sq.m", "B) 75 sq.m", "C) 100 sq.m", "D) 20 sq.m"],
          answer: "B"
        },
        {
          question: "A cube has a volume of 343 cu.cm. What is the length of one of its sides?",
          options: ["A) 7 cm", "B) 49 cm", "C) 14 cm", "D) 21 cm"],
          answer: "A"
        },
        {
          question: "A rectangular garden is twice as long as it is wide. If its area is 288 sq.m, how wide is it?",
          options: ["A) 12 meters", "B) 24 meters", "C) 16 meters", "D) 8 meters"],
          answer: "A"
        },
        {
          question: "A cylindrical can has a radius of 3 cm and a height of 14 cm. What is its volume? (Use π = 3.14)",
          options: ["A) 126 cu.cm", "B) 132 cu.cm", "C) 158 cu.cm", "D) 394 cu.cm"],
          answer: "D"
        },
        {
          question: "A rectangle's length is 4 meters more than its width. If its area is 60 sq.m, what is its width?",
          options: ["A) 6 meters", "B) 10 meters", "C) 8 meters", "D) 15 meters"],
          answer: "C"
        },
        {
          question: "A square's area is 256 sq.cm. What is its perimeter?",
          options: ["A) 64 cm", "B) 32 cm", "C) 16 cm", "D) 128 cm"],
          answer: "A"
        },
        {
          question: "A triangular prism has a base area of 45 sq.cm and a height of 20 cm. What is its volume?",
          options: ["A) 90 cu.cm", "B) 450 cu.cm", "C) 900 cu.cm", "D) 225 cu.cm"],
          answer: "C"
        },
        {
          question: "A circular garden has a diameter of 14 meters. What is its area? (Use π = 3.14)",
          options: ["A) 153.86 sq.m", "B) 307.72 sq.m", "C) 615.44 sq.m", "D) 44 sq.m"],
          answer: "A"
        },
        {
          question: "A bookshelf is in the shape of a rectangular prism and has a length of 1.5 meters, a width of 0.5 meters, and a height of 2 meters. What is its volume?",
          options: ["A) 1.5 cu.m", "B) 2 cu.m", "C) 3 cu.m", "D) 4 cu.m"],
          answer: "C"
        },
        {
          question: "A rhombus has diagonals of lengths 8 cm and 15 cm. What is its area?",
          options: ["A) 60 sq.cm", "B) 120 sq.cm", "C) 64 sq.cm", "D) 30 sq.cm"],
          answer: "A"
        },
        {
          question: "A square field has an area of 625 sq.m. How long is one side?",
          options: ["A) 15 meters", "B) 25 meters", "C) 35 meters", "D) 45 meters"],
          answer: "B"
        },
        {
          question: "A cylindrical tank has a height of 2 meters and a diameter of 3 meters. What is its volume? (Use π = 3.14)",
          options: ["A) 18.84 cu.m", "B) 14.13 cu.m", "C) 28.26 cu.m", "D) 37.68 cu.m"],
          answer: "C"
        }
      ];

      let currentQuestionIndex = 0;
      const questionText = document.getElementById('question-text');
      const optionA = document.getElementById('option-A');
      const optionB = document.getElementById('option-B');
      const optionC = document.getElementById('option-C');
      const optionD = document.getElementById('option-D');

      function displayQuestion(questionIndex) {
          const question = questionsDatabase[questionIndex];
          questionText.innerText = question.question;
          optionA.innerText = question.options[0];
          optionB.innerText = question.options[1];
          if(question.options[2]) {
              optionC.style.display = "block";
              optionC.innerText = question.options[2];
          }
          else
            optionC.style.display = "none";

          if(question.options[3]) {
              optionD.style.display = "block";
              optionD.innerText = question.options[3];
          }
          else 
            optionD.style.display = "none";
      }

      function checkAnswer(userAnswer) {
          const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
          if(userAnswer === correctAnswer) {
              alert("Correct answer!");
              currentQuestionIndex++;
              if(currentQuestionIndex < questionsDatabase.length) {
                  displayQuestion(currentQuestionIndex);
              }
              else {
                  alert("Congratulations, you've completed the quiz!");
              }
          }
          else {
              alert("Incorrect answer, try again!");
          }
      }

      displayQuestion(currentQuestionIndex);
    </script>
  </body>
</html>
``` 

U4 


<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Numera - Challenge Yourself</title>
    <style>
      body {
        font-family: "Georgia", serif;
        margin: 0;
        padding: 0;
        color: #000033;
        background-color: white;
      }
      .header {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100px;
        background-color: white;
        color: #000033;
        font-size: 2rem;
        border-bottom: 2px solid #000033;
      }
      .header h1 {
        color: #000033;
      }
      .footer {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        background-color: #f9f9f9;
        color: #000033;
        font-size: 1rem;
      }
      .question-container {
        padding: 40px;
        text-align: center;
      }
      .question-box {
        border: 2px solid #000033;
        padding: 20px;
        border-radius: 15px;
        margin: 20px 0;
      }
      .options-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
      }
      .option {
        padding: 10px;
        margin: 10px;
        width: 50%;
        border-radius: 15px;
        border: 2px solid #000033;
        text-align: center;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s ease;
      }
      .option:hover {
        background-color: #000033;
        color: white;
      }
    </style>
  </head>
  <body>
    <div class="header">
      <h1>Numera</h1>
    </div>
    <div class="question-container">
      <div class="question-box">
        <h3 id="question-text">Loading question...</h3>
        <div class="options-container">
          <div class="option" onclick="checkAnswer('A')">
            <p id="option-A"></p>
          </div>
          <div class="option" onclick="checkAnswer('B')">
            <p id="option-B"></p>
          </div>
          <div class="option" onclick="checkAnswer('C')">
            <p id="option-C"></p>
          </div>
          <div class="option" onclick="checkAnswer('D')">
            <p id="option-D"></p>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
      const questionsDatabase = [
        {
          question: "What is x in ⅔ + 6 = 10?",
          options: ["A) 2", "B) 3", "C) 4", "D) 16"],
          answer: "C"
        },
        {
          question: "What is y in y - 9 = 3?",
          options: ["A) -6", "B) 6", "C) 12", "D) 15"],
          answer: "C"
        },
        {
          question: "What is x in 3x = 12?",
          options: ["A) 2", "B) 3", "C) 4", "D) 5"],
          answer: "C"
        },
        {
          question: "What is x in x + 7 = 15?",
          options: ["A) 7", "B) 8", "C) 9", "D) 22"],
          answer: "B"
        },
        {
          question: "What is a in 2a = 16?",
          options: ["A) 7", "B) 8", "C) 9", "D) 10"],
          answer: "B"
        },
        {
          question: "What is x in 4x = 24?",
          options: ["A) 4", "B) 5", "C) 6", "D) 7"],
          answer: "C"
        },
        {
          question: "What is z in z / 2 = 10?",
          options: ["A) 5", "B) 20", "C) 15", "D) 25"],
          answer: "B"
        },
        {
          question: "What is y in 5y = 35?",
          options: ["A) 6", "B) 7", "C) 8", "D) 9"],
          answer: "B"
        },
        {
          question: "What is x in x / 3 = 5?",
          options: ["A) 8", "B) 12", "C) 15", "D) 18"],
          answer: "C"
        },
        {
          question: "What is n in 4n = 40?",
          options: ["A) 8", "B) 9", "C) 10", "D) 11"],
          answer: "C"
        },
        {
          question: "What is x in 2x = 14?",
          options: ["A) 5", "B) 6", "C) 7", "D) 8"],
          answer: "C"
        },
        {
          question: "What is m in m / 5 = 4?",
          options: ["A) 10", "B) 15", "C) 20", "D) 25"],
          answer: "C"
        },
        {
          question: "What is x in 6x = 42?",
          options: ["A) 6", "B) 7", "C) 8", "D) 9"],
          answer: "B"
        },
        {
          question: "What is x in 7x = 49?",
          options: ["A) 6", "B) 7", "C) 8", "D) 9"],
          answer: "B"
        },
        {
          question: "What is w in w / 4 = 8?",
          options: ["A) 20", "B) 25", "C) 30", "D) 35"],
          answer: "C"
        }
      ];

      let currentQuestionIndex = 0;
      const questionText = document.getElementById('question-text');
      const optionA = document.getElementById('option-A');
      const optionB = document.getElementById('option-B');
      const optionC = document.getElementById('option-C');
      const optionD = document.getElementById('option-D');

      function displayQuestion(questionIndex) {
          const question = questionsDatabase[questionIndex];
          questionText.innerText = question.question;
          optionA.innerText = question.options[0];
          optionB.innerText = question.options[1];
          if(question.options[2]) {
              optionC.style.display = "block";
              optionC.innerText = question.options[2];
          }
          else
            optionC.style.display = "none";

          if(question.options[3]) {
              optionD.style.display = "block";
              optionD.innerText = question.options[3];
          }
          else 
            optionD.style.display = "none";
      }

      function checkAnswer(userAnswer) {
          const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
          if(userAnswer === correctAnswer) {
              alert("Correct answer!");
              currentQuestionIndex++;
              if(currentQuestionIndex < questionsDatabase.length) {
                  displayQuestion(currentQuestionIndex);
              }
              else {
                  alert("Congratulations, you've completed the quiz!");
              }
          }
          else {
              alert("Incorrect answer, try again!");
          }
      }

      displayQuestion(currentQuestionIndex);
    </script>
  </body>
</html>



U5 


<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Numera - Challenge Yourself</title>
    <style>
      body {
        font-family: "Georgia", serif;
        margin: 0;
        padding: 0;
        color: #000033;
        background-color: white;
      }
      .header {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100px;
        background-color: white;
        color: #000033;
        font-size: 2rem;
        border-bottom: 2px solid #000033;
      }
      .header h1 {
        color: #000033;
      }
      .footer {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        background-color: #f9f9f9;
        color: #000033;
        font-size: 1rem;
      }
      .question-container {
        padding: 40px;
        text-align: center;
      }
      .question-box {
        border: 2px solid #000033;
        padding: 20px;
        border-radius: 15px;
        margin: 20px 0;
      }
      .options-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
      }
      .option {
        padding: 10px;
        margin: 10px;
        width: 50%;
        border-radius: 15px;
        border: 2px solid #000033;
        text-align: center;
        font-size: 1rem;
        cursor: pointer;
        transition: all 0.3s ease;
      }
      .option:hover {
        background-color: #000033;
        color: white;
      }
    </style>
  </head>
  <body>
    <div class="header">
      <h1>Numera</h1>
    </div>
    <div class="question-container">
      <div class="question-box">
        <h3 id="question-text">Loading question...</h3>
        <div class="options-container">
          <div class="option" onclick="checkAnswer('A')">
            <p id="option-A"></p>
          </div>
          <div class="option" onclick="checkAnswer('B')">
            <p id="option-B"></p>
          </div>
          <div class="option" onclick="checkAnswer('C')">
            <p id="option-C"></p>
          </div>
          <div class="option" onclick="checkAnswer('D')">
            <p id="option-D"></p>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <p>Numera Education | &copy; 2023</p>
    </div>
    <script>
      const questionsDatabase = [
        {
          question: "Which axis would represent the number of students in a bar graph?",
          options: ["A) X-axis", "B) Y-axis"],
          answer: "B"
        },
        {
          question: "What is the best graph to represent the data of how many days it rained compared to how many days it was sunny or cloudy in a week-long weather survey?",
          options: ["A) Line graph", "B) Pie chart", "C) Histogram", "D) Scatter plot"],
          answer: "B"
        },
        {
          question: "In a histogram representing the heights of students, what does each bar indicate?",
          options: ["A) Average height", "B) Height range", "C) Total number of students", "D) Shortest and tallest student"],
          answer: "B"
        },
        {
          question: "What is the best graph to show monthly sales of a shop?",
          options: ["A) Scatter plot", "B) Line graph", "C) Pie chart", "D) Bar graph"],
          answer: "B"
        },
        {
          question: "If a pie chart represents the favorite sports of 60 students in a school with soccer as 20, basketball as 25, and tennis as 15, which sport would have the biggest section?",
          options: ["A) Soccer", "B) Basketball", "C) Tennis"],
          answer: "B"
        },
        {
          question: "Which month showed the most variance in rainfall according to a line graph showing monthly rainfall throughout the year?",
          options: ["A) June", "B) July", "C) August"],
          answer: "A"
        },
        {
          question: "If a graph represents the frequency of student grades and shows more students received a grade of 80 than any other score, what is 80 called in the dataset?",
          options: ["A) Mean", "B) Median", "C) Mode"],
          answer: "C"
        },
        {
          question: "Which of these represents a continuous set of data?",
          options: ["A) Types of fruit", "B) Shoe sizes", "C) Ages of students", "D) Favorite colors"],
          answer: "C"
        },
        {
          question: "What could be a reason for sales going up in December and down in January according to a bar graph showing book sales over a year?",
          options: ["A) New books released", "B) Holiday shopping season", "C) Bookstore was closed", "D) Students bought textbooks"],
          answer: "B"
        },
        {
          question: "Which graph would best show the popularity of each genre of book in a class?",
          options: ["A) Line graph", "B) Scatter plot", "C) Histogram", "D) Pie chart"],
          answer: "D"
        },
        {
          question: "Which type of graph shows the relationship between two sets of data, such as time spent studying and test scores?",
          options: ["A) Bar graph", "B) Pie chart", "C) Scatter plot", "D) Histogram"],
          answer: "C"
        },
        {
          question: "What is the median in the dataset {15, 20, 20, 25, 30, 35, 40}?",
          options: ["A) 20", "B) 25", "C) 30", "D) 35"],
          answer: "B"
        },
        {
          question: "What would be a suitable title for a bar graph representing the number of pets that Lisa's friends have?",
          options: ["A) Types of Pets", "B) Pets' Names", "C) Number of Pets", "D) Age of Pets"],
          answer: "C"
        },
        {
          question: "If 60% of the 200 students surveyed preferred apples and 20% preferred cherries, how many students preferred cherries?",
          options: ["A) 10", "B) 20", "C) 40", "D) 60"],
          answer: "D"
        },
        {
          question: "What is the most suitable graph to show the daily height of a plant over a month?",
          options: ["A) Line graph", "B) Pie chart", "C) Bar graph", "D) Scatter plot"],
          answer: "A"
        }
      ];

      let currentQuestionIndex = 0;
      const questionText = document.getElementById('question-text');
      const optionA = document.getElementById('option-A');
      const optionB = document.getElementById('option-B');
      const optionC = document.getElementById('option-C');
      const optionD = document.getElementById('option-D');

      function displayQuestion(questionIndex) {
          const question = questionsDatabase[questionIndex];
          questionText.innerText = question.question;
          optionA.innerText = question.options[0];
          optionB.innerText = question.options[1];
          if(question.options[2]) {
              optionC.style.display = "block";
              optionC.innerText = question.options[2];
          }
          else
            optionC.style.display = "none";

          if(question.options[3]) {
              optionD.style.display = "block";
              optionD.innerText = question.options[3];
          }
          else 
            optionD.style.display = "none";
      }

      function checkAnswer(userAnswer) {
          const correctAnswer = questionsDatabase[currentQuestionIndex].answer;
          if(userAnswer === correctAnswer) {
              alert("Correct answer!");
              currentQuestionIndex++;
              if(currentQuestionIndex < questionsDatabase.length) {
                  displayQuestion(currentQuestionIndex);
              }
              else {
                  alert("Congratulations, you've completed the quiz!");
              }
          }
          else {
              alert("Incorrect answer, try again!");
          }
      }

      displayQuestion(currentQuestionIndex);
    </script>
  </body>
</html>

## Layout 


S1 

<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Numera</title>

    <style>

        :root {

            --primary-color: #000033;

            --header-color: #FAFAFA;

            --deep-blue: #000080;

            --light-grey: #ECF0F1;

            --black: rgba(0, 0, 0, 0.1);

            --border-purple: #800080;

        }



        body {

            font-family: 'Georgia', serif;

            margin: 0;

            padding: 0;

            background-color: var(--header-color);

        }



        .header {

            position: relative;

            background-color: var(--header-color);

            color: var(--primary-color);

            padding: 10px;

            text-align: left;

        }



        .footer {

            text-align: center;

            background-color: var(--header-color);

            color: var(--primary-color);

        }



        .content {

            display: flex;

            justify-content: space-between;

            margin: 30px;

            padding: 20px;

            border-radius: 15px;

            box-shadow: 5px 5px 15px var(--black);

        }



        .content > div {

            flex-basis: 45%;

            padding: 30px;

            border-radius: 15px;

            box-shadow: 5px 5px 15px var(--black);

            color: var(--primary-color);

            background-color: var(--header-color);

            margin: 0 10px;

        }



        .extra {

            display: flex;

            flex-direction: column;

            justify-content: center;

            align-items: center;

        }



        .welcome-statement {

            margin-bottom: 20px;

            text-align: center;

        }



        .google-login {

            padding: 10px 20px;

            border: 2px solid var(--border-purple);

            border-radius: 4px;

            text-align: center;

            transition: background-color 0.3s ease;

            cursor: pointer;

        }



        .google-login a {

            color: black;

            text-decoration: none;

        }



        .google-login:hover {

            background-color: var(--border-purple);

            color: var(--header-color);

        }



        @keyframes slideIn {

            from {

                opacity: 0;

                transform: translateY(-50px);

            }

            to {

                opacity: 1;

                transform: translateY(0);

            }

        }



        .animated {

            animation: slideIn 1s;

        }

    </style>

</head>



<body>

    <header class="header">

        <h1 class="header__title">Numera</h1>

        <div class="header__motto">

            Bridging Numbers and Minds

        </div>

    </header>



    <div class="content">

        <div class="main">

            <section class="section animated">

                <h2 class="section__title">About</h2>

                <p class="section__content">Numera is a revolutionary learning platform that brings together creativity, interaction, and pedagogy to help students from Kindergarten to 6th grade excel in mathematics. Our platform fosters a love for numbers, problem-solving, and critical thinking, empowering students to thrive in a technology-driven world. At Numera, we believe that every child is unique, and we aim to offer personalized, engaging, and enjoyable learning experiences that cater to individual learning styles and paces.</p>

            </section>



            <section class="section animated">

                <h2 class="section__title">Features</h2>

                <ul class="feature-list">

                    <li class="feature-list__item">Personalized Learning Paths: Our adaptive technology tailors math lessons to each student's skill level, optimizing their learning potential.</li>

                    <li class="feature-list__item">Captivating Virtual Lessons: Our platform transforms abstract mathematical concepts into visually appealing, understandable lessons that enhance comprehension and retention.</li>

                    <li class="feature-list__item">Gamified Assessments: We gamify assessments to make learning fun and engaging, which boosts students' motivation and enjoyment of math.</li>

                    <li class="feature-list__item">Real-Time Progress Tracking: Parents and educators can monitor students' progress in real-time, allowing for timely feedback and intervention.</li>

                </ul>

            </section>

        </div>



        <div class="extra animated">

            <h2 class="welcome-statement">Welcome to Numera</h2>

            <div class=“Login">

                <a href="http://google.com" target="_blank">Continue</a>

            </div>

        </div>

    </div>

   
    <footer class="footer">

        <p class="footer__content">Numera, Inc &copy; 2023 | Established in MMXXIII</p>

    </footer>

</body>



</html>



S2 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to Numera</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }

        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }

        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            text-align: center;
            padding: 10px;
            margin-bottom: 30px;
        }
        
        .city-selector {
            text-align: center;
            margin: 20px;
        }

        .city-buttons button {
            padding: 10px 20px;
            margin: 5px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            transition: border 0.3s ease;
        }

        .city-buttons button:hover {
            border: 4px solid var(--primary-color);
        }

        .content {
            margin: auto;
            max-width: 960px;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
        }

        .box:hover {
            border: 4px solid var(--primary-color);
        }

        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
            margin-top: 50px;
            padding: 10px;
        }

    </style>
</head>

<body>
    <div class="header">
        <h1 class="header__title">Numera</h1>
    </div>

    <div class="content">
        <div class="box">
            <h2 class="box__title">Welcome to Numera</h2>
            <p class="box__text">Select your city to continue.</p>
            <div class="city-selector">
                <div class="city-buttons">
                    <button onclick="navigateToCity('New York')">New York</button>
                    <button onclick="navigateToCity('Toronto')">Toronto</button>
                    <button onclick="navigateToCity('Cambridge')">Cambridge</button>
                    <button onclick="navigateToCity('Vancouver')">Vancouver</button>
                    <button onclick="navigateToCity('Calgary')">Calgary</button>
                    <button onclick="navigateToCity('Los Angeles')">Los Angeles</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        function navigateToCity(city) {
            // Replace the URL below with the appropriate URL for each city-specific version of Numera
            window.location.href = "http://" + city.toLowerCase() + ".numera.com";
        }
    </script>

    <footer class="footer">
        <p class="footer__content">Numera, Inc &copy; 2023 | Established in MMXXIII</p>
    </footer>
</body>
</html>



S 3

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }

        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }

        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }

        .grade-selector {
            text-align: center;
            margin: 20px;
        }

        .grade-buttons button {
            padding: 10px 20px;
            margin: 5px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            transition: border 0.3s ease;
        }

        .grade-buttons button:hover {
            border: 4px solid var(--primary-color);
        }

        .content {
            margin: 30px;
            padding: 20px;
        }

        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
        }

        .box:hover {
            border: 4px solid var(--primary-color);
        }

        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>

<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Enriching Minds with Mathematics</h2>
    </header>

    <div class="grade-selector">
        <h3>Select Your Grade:</h3>
        <div class="grade-buttons">
            <button onclick="navigateToGrade('K')">Kindergarten</button>
            <button onclick="navigateToGrade('1')">Grade 1</button>
            <button onclick="navigateToGrade('2')">Grade 2</button>
            <button onclick="navigateToGrade('3')">Grade 3</button>
            <button onclick="navigateToGrade('4')">Grade 4</button>
            <button onclick="navigateToGrade('5')">Grade 5</button>
            <button onclick="navigateToGrade('6')">Grade 6</button>
        </div>
    </div>

    <!-- The rest of the content goes here, similar to the original code for each grade level -->

    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>

    <script>
        function navigateToGrade(grade) {
            // Redirect or load the content for the selected grade
        }
    </script>
</body>

</html>


S 3 



Kindergarten 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Kindergarten Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2> K Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Counting and Cardinality</h2>
            <ul>
                <li>A. Know number names and the counting sequence.</li>
                <li>B. Count to tell the number of objects.</li>
                <li>C. Compare numbers.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('counting')">Launch</button>
        </div>
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Understand addition as putting together and adding to, and understand subtraction as taking apart and taking from.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Work with numbers 11–19 to gain foundations for place value.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Describe and compare measurable attributes.</li>
                <li>B. Classify objects and count the number of objects in each category.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Identify and describe shapes (squares, circles, triangles, rectangles, hexagons, cubes, cones, cylinders, and spheres).</li>
                <li>B. Analyze, compare, create, and compose shapes.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>



Grade 1 

<!DOCTYPE html>

<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }

        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }

        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }

        .content {
            margin: 30px;
            padding: 20px;
        }

        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative; /* Added to position the button */
        }

        .box:hover {
            border: 4px solid var(--primary-color);
        }

        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute; /* Added for positioning */
            bottom: 10px; /* Added for positioning */
            right: 10px; /* Added for positioning */
        }

        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }

        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>

<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Enriching Minds with Mathematics</h2>
    </header>

    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>Represent and solve problems involving addition and subtraction.</li>
                <li>Understand and apply properties of operations and the relationship between addition and subtraction.</li>
                <li>Add and subtract within 20.</li>
                <li>Work with addition and subtraction equations.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
        </div>

        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>Extend the counting sequence.</li>
                <li>Understand place value.</li>
                <li>Use place value understanding and properties of operations to add and subtract.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>

        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>Measure lengths indirectly and by iterating length units.</li>
                <li>Tell and write time.</li>
                <li>Represent and interpret data.</li>
                <li>Work with money.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
        </div>

        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>Reason with shapes and their attributes.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
    </div>

    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>

    <script>
        function launchCurriculum(section) {
            // Handle the launch functionality here, such as redirecting to a specific page or opening a modal
            console.log(`Launching ${section}`);
        }
    </script>
</body>

</html>



Grade 2


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 2 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2> 1 2 Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Represent and solve problems involving addition and subtraction.</li>
                <li>B. Add and subtract within 20.</li>
                <li>C. Work with equal groups of objects to gain foundations for multiplication.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Understand place value.</li>
                <li>B. Use place value understanding and properties of operations to add and subtract.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Measure lengths indirectly and by iterating length units.</li>
                <li>B. Relate addition and subtraction to length.</li>
                <li>C. Work with time and money.</li>
                <li>D. Represent and interpret data.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Reason with shapes and their attributes.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>


Grade 3 




<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 3 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Grade 3: Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Represent and solve problems involving multiplication and division.</li>
                <li>B. Understand properties of multiplication and the relationship between multiplication and division.</li>
                <li>C. Multiply and divide within 100.</li>
                <li>D. Solve problems involving the four operations, and identify and explain patterns in arithmetic.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Use place value understanding and properties of operations to perform multi-digit arithmetic.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations—Fractions</h2>
            <ul>
                <li>A. Develop understanding of fractions as numbers.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('fractions')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Solve problems involving measurement and estimation of intervals of time, liquid volumes, and masses of objects.</li>
                <li>B. Represent and interpret data.</li>
                <li>C. Geometric measurement: understand concepts of area and relate area to multiplication and to addition.</li>
                <li>D. Geometric measurement: recognize perimeter as an attribute of plane figures and distinguish between linear and area measures.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Reason with shapes and their attributes.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>


Grade 4


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 4 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Grade 4: Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Use the four operations with whole numbers to solve problems.</li>
                <li>B. Gain familiarity with factors and multiples.</li>
                <li>C. Generate and analyze patterns.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Generalize place value understanding for multi-digit whole numbers.</li>
                <li>B. Use place value understanding and properties of operations to perform multi-digit arithmetic.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations—Fractions</h2>
            <ul>
                <li>A. Extend understanding of fraction equivalence and ordering.</li>
                <li>B. Build fractions from unit fractions by applying and extending previous understandings of operations on whole numbers.</li>
                <li>C. Understand decimal notation for fractions, and compare decimal fractions.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('fractions')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Solve problems involving measurement and conversion of measurements from a larger unit to a smaller unit.</li>
                <li>B. Represent and interpret data.</li>
                <li>C. Geometric measurement: understand concepts of angle and measure angles.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Draw and identify lines and angles, and classify shapes by properties of their lines and angles.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>




Grade 5 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 5 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Grade 5: Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Write and interpret numerical expressions.</li>
                <li>B. Analyze patterns and relationships.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Understand the place value system.</li>
                <li>B. Perform operations with multi-digit whole numbers and with decimals to hundredths.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations—Fractions</h2>
            <ul>
                <li>A. Use equivalent fractions as a strategy to add and subtract fractions.</li>
                <li>B. Apply and extend previous understandings of multiplication and division to multiply and divide fractions.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('fractions')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Convert like measurement units within a given measurement system.</li>
                <li>B. Represent and interpret data.</li>
                <li>C. Geometric measurement: Understand concepts of volume and relate volume to multiplication and to addition.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Graph points on the coordinate plane to solve real-world and mathematical problems.</li>
                <li>B. Classify two-dimensional figures into categories based on their properties.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>


Grade 6 




<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 6 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Grade 6: Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Ratios and Proportional Relationships</h2>
            <ul>
                <li>A. Understand ratio and rate concepts and use ratio reasoning to solve problems.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('ratios')">Launch</button>
        </div>
        <div class="box">
            <h2>The Number System</h2>
            <ul>
                <li>A. Apply and extend previous understandings of multiplication and division to divide fractions by fractions.</li>
                <li>B. Compute fluently with multi-digit numbers and find common factors and multiples.</li>
                <li>C. Apply and extend previous understandings of numbers to the system of rational numbers.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>
        <div class="box">
            <h2>Expressions and Equations</h2>
            <ul>
                <li>A. Apply and extend previous understandings of arithmetic to algebraic expressions.</li>
                <li>B. Reason about and solve one-variable equations and inequalities.</li>
                <li>C. Represent and analyze quantitative relationships between dependent and independent variables.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('expressions')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Solve real-world and mathematical problems involving area, surface area, and volume.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
        <div class="box">
            <h2>Statistics and Probability</h2>
            <ul>
                <li>A. Develop an understanding of statistical variability.</li>
                <li>B. Summarize and describe distributions.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('statistics')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>


Questions code 

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Challenge Yourself</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }

        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: var(--header-color);
            color: var(--primary-color);
        }

        .header {
            background-color: var(--header-color);
            color: var(--primary-color);
            text-align: center;
            padding: 20px;
        }

        .question-container {
            padding: 40px;
            text-align: center;
        }

        .question-box {
            border: 2px solid var(--primary-color);
            padding: 20px;
            border-radius: 15px;
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
        }

        .question-box:hover {
            border: 4px solid var(--primary-color);
        }

        .answer-input {
            padding: 10px;
            width: 50%;
            border-radius: 15px;
            border: 2px solid var(--primary-color);
            font-size: 1rem;
        }

        .submit-button {
            padding: 10px 20px;
            border-radius: 15px;
            background-color: var(--header-color);
            color: var(--primary-color);
            border: 2px solid var(--primary-color);
            cursor: pointer;
            transition: border 0.3s ease;
        }

        .submit-button:hover {
            border: 4px solid var(--primary-color);
        }

        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>

<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Challenge Yourself with Mathematics</h2>
    </header>
    <div class="question-container">
        <div class="question-box">
            <h3>Question:</h3>
            <p>What is the sum of all natural numbers from 1 to 100?</p>
            <input type="text" class="answer-input" id="answer" placeholder="Your Answer Here">
            <button class="submit-button" onclick="checkAnswer()">Submit</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>

    <script>
        function checkAnswer() {
            const answer = document.getElementById('answer').value;
            if (answer == 5050) {
                alert('Correct! Well done!');
            } else {
                alert('Incorrect. Try again.');
            }
        }
    </script>
</body>

</html>


## New York Schools; Units.


Grade K
* Counting and Cardinality
    * Know number names and the count sequence.
    * Count to tell the number of objects.
    * Compare numbers.
* Operations and Algebraic Thinking
    * Understand addition as putting together and adding to, and understand subtraction as taking apart and taking from.
* Number and Operations in Base Ten
    * Work with numbers 11-19 to gain foundations for place value.
* Measurement and Data
    * Describe and compare measurable attributes.
    * Classify objects and count the number of objects in categories.
* Geometry
    * Identify and describe shapes.
    * Analyze, compare, create, and compose shapes.
Grade 1
* Operations and Algebraic Thinking
    * Represent and solve problems involving addition and subtraction.
    * Understand and apply properties of operations and the relationship between addition and subtraction.
    * Add and subtract within 20.
    * Work with addition and subtraction equations.
* Number and Operations in Base Ten
    * Extend the counting sequence.
    * Understand place value.
    * Use place value understanding and properties of operations to add and subtract.
* Measurement and Data
    * Measure lengths indirectly and by iterating length units.
    * Tell and write time.
    * Represent and interpret data.
* Geometry
    * Reason with shapes and their attributes.
Grade 2
* Operations and Algebraic Thinking
    * Represent and solve problems involving addition and subtraction.
    * Add and subtract within 20.
    * Work with equal groups of objects to gain foundations for multiplication.
* Number and Operations in Base Ten
    * Understand place value.
    * Use place value understanding and properties of operations to add and subtract.
* Measurement and Data
    * Measure and estimate lengths in standard units.
    * Relate addition and subtraction to length.
    * Work with time and money.
    * Represent and interpret data.
* Geometry
    * Reason with shapes and their attributes.
Grade 3
* Operations and Algebraic Thinking
    * Represent and solve problems using multiplication and division.
    * Understand properties of multiplication and the relationship between multiplication and division.
    * Multiply and divide within 100.
    * Solve problems involving the four operations, and identify and explain patterns in arithmetic.
* Number and Operations in Base Ten
    * Use place value understanding and properties of operations to perform multi-digit arithmetic.
* Number and Operations—Fractions
    * Develop understanding of fractions as numbers.
* Measurement and Data
    * Solve problems involving measurement and estimation of intervals of time, liquid volumes, and masses of objects.
    * Represent and interpret data.
    * Geometric measurement: understand concepts of area and relate area to multiplication and to addition.
    * Geometric measurement: recognize perimeter as an attribute of plane figures and distinguish between linear and area measures.
* Geometry
    * Reason with shapes and their attributes.
Grade 4
* Operations and Algebraic Thinking
    * Use the four operations with whole numbers to solve problems.
* Number and Operations in Base Ten
    * Generalize place value understanding for multi-digit whole numbers.
    * Use place value understanding and properties of operations to perform multi-digit arithmetic.
* Number and Operations—Fractions
    * Extend understanding of fraction equivalence and ordering.
    * Build fractions from unit fractions by applying and extending previous understandings of operations on whole numbers.
    * Understand decimal notation for fractions, and compare decimal fractions.
* Measurement and Data
    * Solve problems involving measurement and conversion of measurements from a larger unit to a smaller unit.
    * Represent and interpret data.
    * Geometric measurement: understand concepts of angle and measure angles.
* Geometry
    * Draw and identify lines and angles, and classify shapes by properties of their lines and angles.
Grade 5
* Operations and Algebraic Thinking
    * Write and interpret numerical expressions.
    * Analyze patterns and relationships.
* Number and Operations in Base Ten
    * Understand the place value system.
    * Perform operations with multi-digit whole numbers and with decimals to hundredths.
* Number and Operations—Fractions
    * Use equivalent fractions as a strategy to add and subtract fractions.
    * Apply and extend previous understandings of multiplication and division to multiply and divide fractions.
* Measurement and Data
    * Convert like measurement units within a given measurement system.
    * Represent and interpret data.
    * Geometric measurement: understand concepts of volume and relate volume to multiplication and to addition.
* Geometry
    * Graph points on the coordinate plane to solve real-world and mathematical problems.
    * Classify two-dimensional figures into categories based on their properties.
Grade 6
* Ratios and Proportional Relationships
    * Understand ratio concepts and use ratio reasoning to solve problems.
* The Number System
    * Apply and extend previous understandings of multiplication and division to divide fractions by fractions.
    * Compute fluently with multi-digit numbers and find common factors and multiples.
    * Apply and extend previous understandings of numbers to the system of rational numbers.
* Expressions and Equations
    * Apply and extend previous understandings of arithmetic to algebraic expressions.
    * Reason about and solve one-variable equations and inequalities.
    * Represent and analyze quantitative relationships between dependent and independent variables.
* Geometry
    * Solve real-world and mathematical problems involving area, surface area, and volume.
* Statistics and Probability
    * Develop understanding of statistical variability.
    * Summarize and describe distributions.







Kindergarten (K):

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Kindergarten Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Counting and Cardinality</h2>
            <ul>
                <li>A. Know number names and the counting sequence.</li>
                <li>B. Count to tell the number of objects.</li>
                <li>C. Compare numbers.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('countingK')">Launch</button>
        </div>
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Understand addition as putting together and adding to, and understand subtraction as taking apart and taking from.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operationsK')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Work with numbers 11–19 to gain foundations for place value.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbersK')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Describe and compare measurable attributes.</li>
                <li>B. Classify objects and count the number of objects in each category.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurementK')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Identify and describe shapes (squares, circles, triangles, rectangles, hexagons, cubes, cones, cylinders, and spheres).</li>
                <li>B. Analyze, compare, create, and compose shapes.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometryK')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>

Grade 1 (G1):

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 1 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Represent and solve problems involving addition and subtraction.</li>
                <li>B. Understand and apply properties of operations and the relationship between addition and subtraction.</li>
                <li>C. Add and subtract within 20.</li>
                <li>D. Work with addition and subtraction equations.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operationsG1')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Extend the counting sequence.</li>
                <li>B. Understand place value.</li>
                <li>C. Use place value understanding and properties of operations to add and subtract.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbersG1')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Measure lengths indirectly and by iterating length units.</li>
                <li>B. Tell and write time.</li>
                <li>C. Represent and interpret data.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurementG1')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Reason with shapes and their attributes.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometryG1')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>



Grade 2 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 2 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Represent and solve problems involving addition and subtraction.</li>
                <li>B. Add and subtract within 20.</li>
                <li>C. Work with equal groups of objects to gain foundations for multiplication.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operationsG2')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Understand place value.</li>
                <li>B. Use place value understanding and properties of operations to add and subtract.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbersG2')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Measure and estimate lengths in standard units.</li>
                <li>B. Relate addition and subtraction to length.</li>
                <li>C. Work with time and money.</li>
                <li>D. Represent and interpret data.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurementG2')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Reason with shapes and their attributes.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometryG2')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>

Grade 3

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 3 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Represent and solve problems using multiplication and division.</li>
                <li>B. Understand properties of multiplication and the relationship between multiplication and division.</li>
                <li>C. Multiply and divide within 100.</li>
                <li>D. Solve problems involving the four operations, and identify and explain patterns in arithmetic.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operationsG3')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Use place value understanding and properties of operations to perform multi-digit arithmetic.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbersG3')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations—Fractions</h2>
            <ul>
                <li>A. Develop understanding of fractions as numbers.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('fractionsG3')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Solve problems involving measurement and estimation of intervals of time, liquid volumes, and masses of objects.</li>
                <li>B. Represent and interpret data.</li>
                <li>C. Geometric measurement: understand concepts of area and relate area to multiplication and to addition.</li>
                <li>D. Geometric measurement: recognize perimeter as an attribute of plane figures and distinguish between linear and area measures.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurementG3')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Reason with shapes and their attributes.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometryG3')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>

Grade 4

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 4 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Use the four operations with whole numbers to solve problems.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operationsG4')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Generalize place value understanding for multi-digit whole numbers.</li>
                <li>B. Use place value understanding and properties of operations to perform multi-digit arithmetic.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbersG4')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations—Fractions</h2>
            <ul>
                <li>A. Extend understanding of fraction equivalence and ordering.</li>
                <li>B. Build fractions from unit fractions by applying and extending previous understandings of operations on whole numbers.</li>
                <li>C. Understand decimal notation for fractions, and compare decimal fractions.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('fractionsG4')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Solve problems involving measurement and conversion of measurements from a larger unit to a smaller unit.</li>
                <li>B. Represent and interpret data.</li>
                <li>C. Geometric measurement: understand concepts of angle and measure angles.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurementG4')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Draw and identify lines and angles, and classify shapes by properties of their lines and angles.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometryG4')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>

Grade 5

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 5 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Write and interpret numerical expressions.</li>
                <li>B. Analyze patterns and relationships.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operationsG5')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Understand the place value system.</li>
                <li>B. Perform operations with multi-digit whole numbers and with decimals to hundredths.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbersG5')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations—Fractions</h2>
            <ul>
                <li>A. Use equivalent fractions as a strategy to add and subtract fractions.</li>
                <li>B. Apply and extend previous understandings of multiplication and division to multiply and divide fractions.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('fractionsG5')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Convert like measurement units within a given measurement system.</li>
                <li>B. Represent and interpret data.</li>
                <li>C. Geometric measurement: understand concepts of volume and relate volume to multiplication and to addition.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurementG5')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Graph points on the coordinate plane to solve real-world and mathematical problems.</li>
                <li>B. Classify two-dimensional figures into categories based on their properties.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometryG5')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>

Grade 6

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 5 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2>Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Ratios and Proportional Relationships</h2>
            <ul>       
                <li>A. Understand ratio concepts and use ratio reasoning to solve problems.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('ratiosG6')">Launch</button>
        </div>
        <div class="box">
            <h2>The Number System</h2>
            <ul>
                <li>A. Apply and extend previous understandings of multiplication and division to divide fractions by fractions.</li>
                <li>B. Compute fluently with multi-digit numbers and find common factors and multiples.</li>
                <li>C. Apply and extend previous understandings of numbers to the system of rational numbers.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbersG6')">Launch</button>
        </div>
        <div class="box">
            <h2>Expressions and Equations</h2>
            <ul>
                <li>A. Apply and extend previous understandings of arithmetic to algebraic expressions.</li>
                <li>B. Reason about and solve one-variable equations and inequalities.</li>
                <li>C. Represent and analyze quantitative relationships between dependent and independent variables.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('expressionsG6')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Solve real-world and mathematical problems involving area, surface area, and volume.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometryG6')">Launch</button>
        </div>
        <div class="box">
            <h2>Statistics and Probability</h2>
            <ul>
                <li>A. Develop understanding of statistical variability.</li>
                <li>B. Summarize and describe distributions.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('statisticsG6')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>



## Los Angeles Schools; Units.

Kindergarten:

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Numera - Kindergarten Mathematical Mastery</title>
	<style>
		:root {
			--primary-color: #000033;
			--header-color: white;
		}
		body {
			font-family: 'Georgia', serif;
			margin: 0;
			padding: 0;
			background-color: white;
		}
		.header {
			position: relative;
			background-color: var(--header-color);
			color: var(--primary-color);
			padding: 10px;
			text-align: center;
		}
		.content {
			margin: 30px;
			padding: 20px;
		}
		.box {
			padding: 20px;
			border: 2px solid var(--primary-color);
			border-radius: 15px;
			color: var(--primary-color);
			background-color: var(--header-color);
			margin: 20px 0;
			transition: border 0.3s ease;
			position: relative;
		}
		.box:hover {
			border: 4px solid var(--primary-color);
		}
		.launch-button {
			padding: 10px 20px;
			border: 2px solid var(--primary-color);
			background-color: var(--header-color);
			color: var(--primary-color);
			cursor: pointer;
			font-size: 1rem;
			border-radius: 15px;
			transition: border 0.3s ease;
			position: absolute;
			bottom: 10px;
			right: 10px;
		}
		.launch-button:hover {
			border: 4px solid var(--primary-color);
		}
		.footer {
			text-align: center;
			background-color: var(--header-color);
			color: var(--primary-color);
		}
	</style>
</head>
<body>
	<header class="header">
		<h1>Numera</h1>
		<h2> Enriching Minds with Mathematics</h2>
	</header>
	<div class="content">
		<div class="box">
			<h2>Counting and Cardinality</h2>
			<ul>
				<li>A. Know number names and the counting sequence.</li>
				<li>B. Count to tell the number of objects.</li>
				<li>C. Compare numbers.</li>
			</ul>
			<button class="launch-button" onclick="launchCurriculum('counting')">Launch</button>
		</div>
		<div class="box">
			<h2>Operations and Algebraic Thinking</h2>
			<ul>
				<li>A. Understand addition as putting together and adding to, and understand subtraction as taking apart and taking from.</li>
			</ul>
			<button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
		</div>
		<div class="box">
			<h2>Number and Operations in Base Ten</h2>
			<ul>
				<li>A. Work with numbers 11–19 to gain foundations for place value.</li>
			</ul>
			<button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
		</div>
		<div class="box">
			<h2>Measurement and Data</h2>
			<ul>
				<li>A. Describe and compare measurable attributes.</li>
				<li>B. Classify objects and count the number of objects in each category.</li>
			</ul>
			<button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
		</div>
		<div class="box">
			<h2>Geometry</h2>
			<ul>
				<li>A. Identify and describe shapes (squares, circles, triangles, rectangles, hexagons, cubes, cones, cylinders, and spheres).</li>
				<li>B. Analyze, compare, create, and compose shapes.</li>
			</ul>
			<button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
		</div>
	</div>
	<footer class="footer">
		<p>Numera, Inc &copy; 2023</p>
	</footer>
	<script>
		function launchCurriculum(section) {
			console.log(`Launching ${section}`);
		}
	</script>
</body>
</html>
```

Grade 1:

```html
<!DOCTYPE html>
<html lang="en">
<head> 
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Numera - Grade 1 Mathematical Mastery</title>
	<style>
		:root {
			--primary-color: #000033;
			--header-color: white;
		}
		body {
			font-family: 'Georgia', serif;
			margin: 0;
			padding: 0;
			background-color: white;
		}
		.header {
			position: relative;
			background-color: var(--header-color);
			color: var(--primary-color);
			padding: 10px;
			text-align: center;
		}
		.content {
			margin: 30px;
			padding: 20px;
		}
		.box {
			padding: 20px;
			border: 2px solid var(--primary-color);
			border-radius: 15px;
			color: var(--primary-color);
			background-color: var(--header-color);
			margin: 20px 0;
			transition: border 0.3s ease;
			position: relative;
		}
		.box:hover {
			border: 4px solid var(--primary-color);
		}
		.launch-button {
			padding: 10px 20px;
			border: 2px solid var(--primary-color);
			background-color: var(--header-color);
			color: var(--primary-color);
			cursor: pointer;
			font-size: 1rem;
			border-radius: 15px;
			transition: border 0.3s ease;
			position: absolute;
			bottom: 10px;
			right: 10px;
		}
		.launch-button:hover {
			border: 4px solid var(--primary-color);
		}
		.footer {
			text-align: center;
			background-color: var(--header-color);
			color: var(--primary-color);
		}
	</style>
</head>
<body>
	<header class="header">
		<h1>Numera</h1>
		<h2> Enriching Minds with Mathematics</h2>
	</header>
	<div class="content">
		<div class="box">
			<h2>Operations and Algebraic Thinking</h2>
			<ul>
				<li>A. Solve addition and subtraction problems within 20.</li>
			</ul>
			<button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
		</div>
		<div class="box">
			<h2>Number and Operations in Base Ten</h2>
			<ul>
				<li>A. Develop an understanding of place value.</li>
			</ul>
			<button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
		</div>
		<div class="box">
			<h2>Measurement and Data</h2>
			<ul>
				<li>A. Measure lengths and tell time.</li>
				<li>B. Represent data.</li>
			</ul>
			<button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
		</div>
		<div class="box">
			<h2>Geometry</h2>
			<ul>
				<li>A. Describe and compare 2D and 3D shapes.</li>
			</ul>
			<button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
		</div>
	</div>
	<footer class="footer">
		<p>Numera, Inc &copy; 2023</p>
	</footer>
	<script>
		function launchCurriculum(section) {
			console.log(`Launching ${section}`);
		}
	</script>
</body>
</html>
```

Grade 2:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 2 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2> Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Mastery of addition and subtraction within 100.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Working with numbers up to 1000.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Measuring and estimating lengths, working with time and money.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Investigating shapes and their attributes.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>
```

Grade 3:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 3 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2> Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Multiplication and division within 100.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Rounding, addition, subtraction, multiplication, and division of numbers up to 1000.</li>
                <li>B. Understanding fractions as numbers.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Time, volume, and mass concepts; area and perimeter.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Classifying shapes by properties.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>
```

Grade 4:

```html
```

Grade 5:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 5 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2> Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Operations and Algebraic Thinking</h2>
            <ul>
                <li>A. Analyzing patterns and working with expressions.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('operations')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations in Base Ten</h2>
            <ul>
                <li>A. Multiplication and division of multi-digit whole numbers.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>
        <div class="box">
            <h2>Number and Operations—Fractions</h2>
            <ul>
                <li>A. Arithmetic with fractions and decimals.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('fractions')">Launch</button>
        </div>
        <div class="box">
            <h2>Measurement and Data</h2>
            <ul>
                <li>A. Converting measurements, volume concepts.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('measurement')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Coordinate plane, properties of 2D figures.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>
```

Grade 6:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Numera - Grade 6 Mathematical Mastery</title>
    <style>
        :root {
            --primary-color: #000033;
            --header-color: white;
        }
        body {
            font-family: 'Georgia', serif;
            margin: 0;
            padding: 0;
            background-color: white;
        }
        .header {
            position: relative;
            background-color: var(--header-color);
            color: var(--primary-color);
            padding: 10px;
            text-align: center;
        }
        .content {
            margin: 30px;
            padding: 20px;
        }
        .box {
            padding: 20px;
            border: 2px solid var(--primary-color);
            border-radius: 15px;
            color: var(--primary-color);
            background-color: var(--header-color);
            margin: 20px 0;
            transition: border 0.3s ease;
            position: relative;
        }
        .box:hover {
            border: 4px solid var(--primary-color);
        }
        .launch-button {
            padding: 10px 20px;
            border: 2px solid var(--primary-color);
            background-color: var(--header-color);
            color: var(--primary-color);
            cursor: pointer;
            font-size: 1rem;
            border-radius: 15px;
            transition: border 0.3s ease;
            position: absolute;
            bottom: 10px;
            right: 10px;
        }
        .launch-button:hover {
            border: 4px solid var(--primary-color);
        }
        .footer {
            text-align: center;
            background-color: var(--header-color);
            color: var(--primary-color);
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Numera</h1>
        <h2> Enriching Minds with Mathematics</h2>
    </header>
    <div class="content">
        <div class="box">
            <h2>Ratios and Proportional Relationships</h2>
            <ul>
                <li>A. Understanding ratio concepts, using reasoning with rates and proportions.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('ratios')">Launch</button>
        </div>
        <div class="box">
            <h2>The Number System</h2>
            <ul>
                <li>A. Dividing fractions, understanding integers, and placing them on the number line.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('numbers')">Launch</button>
        </div>
        <div class="box">
            <h2>Expressions and Equations</h2>
            <ul>
                <li>A. Expressions, equations, and inequalities using variables.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('expressions')">Launch</button>
        </div>
        <div class="box">
            <h2>Geometry</h2>
            <ul>
                <li>A. Solving real-world mathematical problems involving area, surface area, and volume.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('geometry')">Launch</button>
        </div>
        <div class="box">
            <h2>Statistics and Probability</h2>
            <ul>
                <li>A. Developing understanding of statistical variability, distribution summaries.</li>
            </ul>
            <button class="launch-button" onclick="launchCurriculum('statistics')">Launch</button>
        </div>
    </div>
    <footer class="footer">
        <p>Numera, Inc &copy; 2023</p>
    </footer>
    <script>
        function launchCurriculum(section) {
            console.log(`Launching ${section}`);
        }
    </script>
</body>
</html>
```
## Ques_K Cambridge

Questions list. 


Unit 1 questions
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Numera - Challenge Yourself</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
  <style>
    body {
      font-family: "Georgia", serif;
      margin: 0;
      padding: 0;
      color: #000033;
      background-color: white;
    }

    .header {
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: white;
      color: #000033;
      padding: 10px;
      text-align: center;
    }

    .games-container {
      display: flex;
      justify-content: flex-end;
      align-items: center;
      flex: 1;
    }

    .games-icon {
      display: flex;
      align-items: center;
      border: 2px solid #000033;
      border-radius: 10px;
      padding: 5px;
      transition: background-color 0.2s ease, border-color 0.2s ease;
    }

    .games-icon i {
      font-size: 18px;
      margin-right: 5px;
    }

    .games-text {
      font-weight: bold;
      font-size: 14px;
      text-transform: uppercase;
      transition: color 0.2s ease;
    }

    .fa-lock {
      font-size: 18px;
      margin-right: 5px;
    }

    .header h1 {
      margin: 0;
    }

    .question-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      margin: 40px 0;
    }

    .question-box {
      border: 2px solid #000033;
      padding: 20px;
      border-radius: 15px;
      margin: 0 20px;
      width: 80%;
      max-width: 800px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .question-label {
      font-size: 24px;
    }

    .question-content {
      font-size: 20px;
      margin-top: 10px;
    }

    .answer-option-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 20px;
    }

    .answer-option-container.round {
      flex-wrap: nowrap;
    }

    .answer-option {
      padding: 10px;
      border-radius: 50%;
      margin: 5px;
      width: 50px;
      height: 50px;
      color: #ffffff;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .answer-option.purple {
      background-color: #a300f0;
    }

    .answer-option.purple:hover {
      background-color: #8d00d0;
    }

    .answer-option.blue {
      background-color: #0099ff;
    }

    .answer-option.blue:hover {
      background-color: #0080ff;
    }

    .true-false-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      margin-top: 20px;
    }

    .true-false-option-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 0 10px;
    }

    .true-false-option {
      padding: 10px;
      border-radius: 15px;
      margin: 5px auto;
      width: 200px;
      height: 50px;
      background-color: #eeeeee;
      color: #000033;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
    }

    .true-false-option:hover {
      background-color: #cccccc;
    }

    .answer-option-container:after {
      content: '';
      flex: 1 0 50px;
    }

    .true-false-label {
      margin-top: 5px;
    }

    .footer {
      background-color: white;
      color: #000033;
      padding: 10px;
      text-align: center;
      position: absolute;
      bottom: 0;
      width: 100%;
    }

    .footer__content {
      margin: 0;
    }

    .answer-option.finished {
      border-radius: 15px;
      margin: 0 auto;
      width: 80%;
      max-width: 800px;
      background-color: #000033;
      color: #ffffff;
    }

    .score {
      display: none;
      font-size: 20px;
      font-weight: bold;
      margin-top: 10px;
      color: #000033;
      padding: 10px;
      text-align: center;
    }

    /* Modal styling */
    .modal {
      position: fixed;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      background: white;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
      z-index: 999;
    }

    /* Hide background when modal opens */
    .modal-background {
      position: fixed;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 998;
    }

    /* Games link styling */
    .games-icon a {
      text-decoration: none;
      color: #000033;
      font-weight: bold;
      font-size: 18px;
      margin-left: 5px;
      padding: 10px;
    }
    
    .games-icon:hover {
      background-color: #000033;
      color: #ffffff;
      border-color: #000033;
    }

    .games-icon:hover a {
      color: #ffffff;
    }

    /* Locked games link styling */
    .games-icon.locked {
      background-color: #cccccc;
      cursor: not-allowed;
    }

    .games-icon.locked:hover {
      background-color: #cccccc;
    }
  </style>
</head>

<body>
  <header class="header">
    <h1>Numera</h1>
    <div class="games-container">
      <div class="games-icon locked">
        <i class="fas fa-lock"></i>
        <i class="fas fa-gamepad"></i>
        <a href="#">Games</a>
      </div>
    </div>
  </header>
  <div class="question-container">
    <div class="question-box">
      <h3 id="question-heading"><span class="question-number">1. </span></h3>
      <p id="question-text">Loading question...</p>
      <div id="answer-input"></div>
    </div>
  </div>
  <div class="score">Score:</div>
  <footer class="footer">
    <p class="footer__content">Numera, Inc &copy; 2023 | Established in MMXXIII</p>
  </footer>
  <script>
    const questionsDatabase = [
      {
        question: "What number comes after 7?",
        answer: 8,
        options: ["9", "6", "8"],
        type: "MC",
      },
      {
        question: "What number comes after 4?",
        answer: 5,
        options: ["8", "5", "7"],
        type: "MC",
      },
      {
        question: "Count by 2's: 1, 3, 5. What comes next?",
        answer: 7,
        options: ["0", "7", "10"],
        type: "MC",
      },
      {
        question: "Add 3 and 3 together. What is the answer?",
        answer: 6,
        options: ["5", "6", "7"],
        type: "MC",
      },
      {
        question: "Add 1 and 2 together. What is the answer?",
        answer: 3,
        options: ["2", "3", "4"],
        type: "MC",
      }
    ];

    let currentQuestionIndex = 0;
    let correctAnswers = 0;
    let hasScored100 = false;
    
    const gamesLink = document.querySelector('.games-icon');

    gamesLink.addEventListener('mouseenter', () => {
      if (!hasScored100) {
        gamesLink.classList.add('locked');
      }
    });
    
    gamesLink.addEventListener('mouseleave', () => {
      if (!hasScored100) {
        gamesLink.classList.remove('locked');
      }
    });

    function shuffleArray(array) {
      for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
      }

      return array;
    }

    function displayNextQuestion() {
      const questionObject = questionsDatabase[currentQuestionIndex];

      document.getElementById("question-heading").innerHTML = `<h3 class="question-number">${currentQuestionIndex + 1}. </h3>`;
      document.getElementById("question-text").innerHTML = questionObject.question;

      if (questionObject.type === "MC") {
        const shuffledOptions = shuffleArray([...questionObject.options]);
        let options = "";

        for (let option of shuffledOptions) {
          let className = "";
          if (option % 2 === 0) {
            className = "blue";
          } else {
            className = "purple";
          }

          options += `<button class="answer-option ${className}" type="button" value="${option}">${option}</button>`;
        }

        if (shuffledOptions.length === 2) {
          document.getElementById("answer-input").classList.add('round');
        }

        document.getElementById("answer-input").innerHTML = `<div class="answer-option-container">${options}</div>`;
        const answerOptions = document.querySelectorAll('.answer-option');

        answerOptions.forEach((option) => {
          option.addEventListener('click', () => {
            checkAnswer(option.value);
          });
        });
      } else if (questionObject.type === "TF") {
        document.getElementById("answer-input").innerHTML = `
          <div class="true-false-container">
            <div class="true-false-option-container">
              <button class="true-false-option" type="button" value="true">True</button>
              <label for="true" class="true-false-label">True</label>
            </div>
            <div class="true-false-option-container">
              <button class="true-false-option" type="button" value="false">False</button>
              <label for="false" class="true-false-label">False</label>
            </div>
          </div>
        `;

        const trueFalseOptions = document.querySelectorAll('.true-false-option');

        trueFalseOptions.forEach((option) => {
          option.addEventListener('click', () => {
            checkAnswer(option.value);
          });
        });
      }
    }

    function checkAnswer(userAnswer) {
      const questionObject = questionsDatabase[currentQuestionIndex];
      
      if (userAnswer == questionObject.answer) {
        correctAnswers++;
      } else {
        // Create modal
        const modal = document.createElement('div');
        modal.classList.add('modal');
        modal.innerHTML = `
          <p style="margin: 0 0 10px 0; font-weight: bold;">Sorry, that's the wrong answer.</p>
          <p>Correct answer: ${questionObject.answer}</p>
        `;
        document.body.appendChild(modal);

        // Create modal background and remove modal after 5 seconds
        const modalBackground = document.createElement('div');
        modalBackground.classList.add('modal-background');
        document.body.appendChild(modalBackground);

        setTimeout(() => {
          modal.remove();
          modalBackground.remove();
        }, 8000);
      }

      currentQuestionIndex++;

      if (currentQuestionIndex < questionsDatabase.length) {
        displayNextQuestion();
      } else {
        document.getElementById("answer-input").innerHTML = `<button class="answer-option finished" onclick="location.reload()">Congratulations! You completed all the questions! Click here to restart...</button>`;
        document.getElementById("answer-input").parentNode.style.height = "inherit";
        document.querySelector('.score').style.display = 'block';
        document.querySelector('.score').textContent = `Score: ${correctAnswers} of ${questionsDatabase.length}`;
        checkScore();
      }
    }

    function checkScore() {
      if (correctAnswers == questionsDatabase.length) {
        hasScored100 = true;
        gamesLink.addEventListener('click', (event) => {
          event.preventDefault();
        });
        gamesLink.classList.remove('locked');
      }
    }

    shuffleArray(questionsDatabase);
    displayNextQuestion();
  </script>
</body>
</html>





Unit 2 

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Numera - Challenge Yourself</title>
  <style>
    body {
      font-family: "Georgia", serif;
      margin: 0;
      padding: 0;
      color: #000033;
      background-color: white;
    }

    .header {
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: white;
      color: #000033;
      padding: 10px;
    }

    .header h1 {
      margin: 0;
    }

    .question-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      margin: 40px 0;
    }

    .question-box {
      border: 2px solid #000033;
      padding: 20px;
      border-radius: 15px;
      margin: 0 20px;
      width: 80%;
      max-width: 800px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .question-label {
      font-size: 24px;
    }

    .question-content {
      font-size: 20px;
      margin-top: 10px;
    }

    .answer-option-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 20px;
    }

    .answer-option-container.round {
      flex-wrap: nowrap;
    }

    .answer-option {
      padding: 10px;
      border-radius: 50%;
      margin: 5px;
      width: 50px;
      height: 50px;
      color: #ffffff;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .answer-option.purple {
      background-color: #a300f0;
    }

    .answer-option.purple:hover {
      background-color: #8d00d0;
    }

    .answer-option.blue {
      background-color: #0099ff;
    }

    .answer-option.blue:hover {
      background-color: #0080ff;
    }

    .true-false-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      margin-top: 20px;
    }

    .true-false-option-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 0 10px;
    }

    .true-false-option {
      padding: 10px;
      border-radius: 15px;
      margin: 5px auto;
      width: 200px;
      height: 50px;
      background-color: #eeeeee;
      color: #000033;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
    }

    .true-false-option:hover {
      background-color: #cccccc;
    }

    .answer-option-container:after {
      content: '';
      flex: 1 0 50px;
    }

    .true-false-label {
      margin-top: 5px;
    }

    .footer {
      background-color: white;
      color: #000033;
      padding: 10px;
      text-align: center;
      position: absolute;
      bottom: 0;
      width: 100%;
    }

    .footer__content {
      margin: 0;
    }

    .answer-option.finished {
      border-radius: 15px;
      margin: 0 auto;
      width: 80%;
      max-width: 800px;
      background-color: #000033;
      color: #ffffff;
    }

    .score {
      display: none;
      font-size: 20px;
      font-weight: bold;
      margin-top: 10px;
      color: #000033;
      padding: 10px;
      text-align: center;
    }
    
    /* Modal styling */
    .modal {
      position: fixed;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      background: white;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
      z-index: 999;
    }
    
    /* Hide background when modal opens */
    .modal-background {
      position: fixed;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 998;
    }
  </style>
</head>

<body>
  <header class="header">
    <h1>Numera</h1>
  </header>
  <div class="question-container">
    <div class="question-box">
      <h3 id="question-heading"><span class="question-number">1. </span></h3>
      <p id="question-text">Loading question...</p>
      <div id="answer-input"></div>
    </div>
  </div>
  <div class="score">Score:</div>
  <footer class="footer">
    <p class="footer__content">Numera, Inc &copy; 2023 | Established in MMXXIII</p>
  </footer>
  <script>
    const questionsDatabase = [
      {
        question: "2 + 2 = ?",
        answer: "4",
        options: ["2", "3", "4"],
        type: "MC",
      },
      {
        question: "6 + 7 = ?",
        answer: "13",
        options: ["12", "13", "11"],
        type: "MC",
      },
      {
        question: "10 - 2 = ?",
        answer: "8",
        options: ["8", "6", "4"],
        type: "MC",
      },
      {
        question: "5 + 13 = ?",
        answer: "18",
        options: ["17", "18", "19"],
        type: "MC",
      },
      {
        question: "4 + 4 = ?",
        answer: "8",
        options: ["4", "8", "36"],
        type: "MC",
      }
    ];

    let currentQuestionIndex = 0;
    let correctAnswers = 0;

    function shuffleArray(array) {
      for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
      }
      return array;
    }

    function displayNextQuestion() {
      const questionObject = questionsDatabase[currentQuestionIndex];
      document.getElementById("question-heading").innerHTML = `<h3 class="question-number">${currentQuestionIndex + 1}. </h3>`;
      document.getElementById("question-text").innerHTML = questionObject.question;
      if (questionObject.type === "MC") {
        const shuffledOptions = shuffleArray([...questionObject.options]);
        let options = "";
        for (let option of shuffledOptions) {
          let className = "";
          if (parseInt(option) % 2 === 0) {
            className = "blue";
          } else {
            className = "purple";
          }
          options += `<button class="answer-option ${className}" type="button" value="${option}">${option}</button>`;
        }
        if (shuffledOptions.length === 2) {
          document.getElementById("answer-input").classList.add('round');
        }
        document.getElementById("answer-input").innerHTML = `<div class="answer-option-container">${options}</div>`;
        const answerOptions = document.querySelectorAll('.answer-option');
        answerOptions.forEach((option) => {
          option.addEventListener('click', () => {
            checkAnswer(option.value);
          });
        });
      }
    }

    function checkAnswer(userAnswer) {
      const questionObject = questionsDatabase[currentQuestionIndex];
      
      if (userAnswer === questionObject.answer) {
        correctAnswers++;
      } else {
        // Create modal
        const modal = document.createElement('div');
        modal.classList.add('modal');
        modal.innerHTML = `
          <p style="margin: 0 0 10px 0; font-weight: bold;">Sorry, that's the wrong answer.</p>
          <p>Correct answer: ${questionObject.answer}</p>
        `;
        document.body.appendChild(modal);

        // Create modal background and remove modal after 5 seconds
        const modalBackground = document.createElement('div');
        modalBackground.classList.add('modal-background');
        document.body.appendChild(modalBackground);

        setTimeout(() => {
          modal.remove();
          modalBackground.remove();
        }, 5000);
      }

      currentQuestionIndex++;

      if (currentQuestionIndex < questionsDatabase.length) {
        displayNextQuestion();
      } else {
        document.getElementById("answer-input").innerHTML = `<button class="answer-option finished" onclick="location.reload()">Congratulations! You completed all the questions! Click here to restart...</button>`;
        document.getElementById("answer-input").parentNode.style.height = "inherit";
        document.querySelector('.score').style.display = 'block';
        document.querySelector('.score').textContent = `Score: ${correctAnswers} of ${questionsDatabase.length}`;
      }
    }

    shuffleArray(questionsDatabase);
    displayNextQuestion();
  </script>
</body>

</html>

U3


<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Numera - Challenge Yourself</title>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <style>
      body {
        font-family: "Georgia", serif;
        margin: 0;
        padding: 0;
        color: #000033;
        background-color: white;
      }

      .header {
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: white;
        color: #000033;
        padding: 10px;
      }

      .header h1 {
        margin: 0;
      }

      .question-label {
        font-size: 24px;
      }

      .question-content {
        font-size: 20px;
        margin-top: 10px;
      }

      .center {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        margin-top: 40px;
        margin-bottom: 40px;
      }

      .question-box {
        border: 2px solid #000033;
        padding: 20px;
        border-radius: 15px;
        width: 80%;
        max-width: 800px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
      }

      .answer-option-container {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        margin-top: 20px;
      }

      .answer-option-container.round {
        flex-wrap: nowrap;
      }

      .answer-option {
        padding: 10px;
        border-radius: 50%;
        margin: 5px;
        width: 50px;
        height: 50px;
        color: #ffffff;
        text-align: center;
        cursor: pointer;
        transition: background-color 0.2s ease;
        border: none;
        font-size: 16px;
        display: flex;
        justify-content: center;
        align-items: center;
      }

      .answer-option.purple {
        background-color: #a300f0;
      }

      .answer-option.purple:hover {
        background-color: #8d00d0;
      }

      .answer-option.blue {
        background-color: #0099ff;
      }

      .answer-option.blue:hover {
        background-color: #0080ff;
      }

      .true-false-container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        margin-top: 20px;
      }

      .true-false-option-container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        margin: 0 10px;
      }

      .true-false-option {
        padding: 10px;
        border-radius: 15px;
        margin: 5px auto;
        width: 200px;
        height: 50px;
        background-color: #eeeeee;
        color: #000033;
        text-align: center;
        cursor: pointer;
        transition: background-color 0.2s ease;
        border: none;
        font-size: 16px;
      }

      .true-false-option:hover {
        background-color: #cccccc;
      }

      .rectangle-button {
        background-color: #000033;
        color: white;
        padding: 10px 20px;
        border-radius: 15px;
        font-size: 16px;
        font-weight: bold;
        cursor: pointer;
        border: none;
      }

      .footer {
        background-color: white;
        color: #000033;
        padding: 10px;
        text-align: center;
        position: absolute;
        bottom: 0;
        width: 100%;
      }

      .footer__content {
        margin: 0;
      }

      .score {
        font-size: 20px;
        font-weight: bold;
        margin-top: 10px;
        color: #000033;
        padding: 10px;
        text-align: center;
      }

      .modal {
        position: fixed;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        background: white;
        border-radius: 10px;
        padding: 20px;
        box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
        z-index: 999;
      }

      .modal-background {
        position: fixed;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.5);
        z-index: 998;
      }
    </style>
  </head>
  <body>
    <header class="header" style="background-color: white;">
      <h1 style="color: #000033;">Numera</h1>
    </header>

    <div class="center">
      <div class="question-box">
        <h3 class="question-label" id="question-heading">Question 1</h3>
        <p class="question-content" id="question-text">Please wait while we load the first question...</p>
        <div id="answer-input"></div>
      </div>
      <div class="score" style="display:none;"></div>
      <div id="modal-container"></div>
    </div>

    <footer class="footer" style="background-color: white;">
      <p class="footer__content" style="color: #000033;">Numera, Inc &copy; 2023 | Established in MMXXIII</p>
    </footer>

    <script>
      const questionsDatabase = [
        {
          question: "How many ones are in the number 15?",
          answer: "15",
          options: ["1", "15", "10"],
          type: "MC",
        },
        {
          question: "7 Cakes plus 10 cakes?",
          answer: "17 Cakes",
          options: ["17 Cakes", "71 Cakes", "107 Cakes"],
          type: "MC",
        },
        {
          question: "Ten apples + 3 apples?",
          answer: "13 apples",
          options: ["30 apples", "13 apples", "23 apples"],
          type: "MC",
        },
        {
          question: "How many ones are in the number 14?",
          answer: "14",
          options: ["4", "1", "14"],
          type: "MC",
        },
        {
          question: "10 + 1 = 11?",
          answer: "true",
          options: ["true", "false"],
          type: "TF",
        },
       
      ];

      let currentQuestionIndex = 0;
      let correctAnswers = 0;

      function shuffleArray(array) {
        for (let i = array.length - 1; i > 0; i--) {
          const j = Math.floor(Math.random() * (i + 1));
          [array[i], array[j]] = [array[j], array[i]];
        }
        return array;
      }

      function displayQuestion() {
        const questionObject = questionsDatabase[currentQuestionIndex];
        document.getElementById("question-heading").innerText = `Question ${currentQuestionIndex + 1}`;
        document.getElementById("question-text").innerText = questionObject.question;

        if (questionObject.type === "MC") {
          const shuffledOptions = shuffleArray([...questionObject.options]);
          let options = "";
          shuffledOptions.forEach((option) => {
            let className = "";
            if (option % 2 == 0) {
              className = "blue";
            } else {
              className = "purple";
            }
            options += `<button class="answer-option ${className}" type="button" value="${option}">${option}</button>`;
          });
          if (shuffledOptions.length === 2) {
            document.getElementById("answer-input").classList.add('round');
          }
          document.getElementById("answer-input").innerHTML = `<div class="answer-option-container">${options}</div>`;
          const answerOptions = document.querySelectorAll('.answer-option');
          answerOptions.forEach((option) => {
            option.addEventListener('click', () => {
              checkAnswer(option.value);
            });
          });
        } else if (questionObject.type === "TF") {
          document.getElementById("answer-input").innerHTML = `
          <div class="true-false-container">
            <div class="true-false-option-container">
              <button class="true-false-option" type="button" value="true">True</button>
            </div>
            <div class="true-false-option-container">
              <button class="true-false-option" type="button" value="false">False</button>
            </div>
          </div>
        `;
          const trueFalseOptions = document.querySelectorAll('.true-false-option');
          trueFalseOptions.forEach((option) => {
            option.addEventListener('click', () => {
              checkAnswer(option.value);
            });
          });
        }
      }

      function checkAnswer(userAnswer) {
        if (userAnswer === questionsDatabase[currentQuestionIndex].answer) {
          correctAnswers++;
          currentQuestionIndex++;
          if (currentQuestionIndex < questionsDatabase.length) {
            displayQuestion();
          } else {
            document.getElementById("answer-input").innerHTML = `<button class="rectangle-button" onclick="location.reload()" style="background-color: #000033; color: white;">Congratulations! You completed all the questions! Click here to restart...</button>`;
            document.getElementById("answer-input").parentNode.style.height = "inherit";
            document.querySelector('.score').style.display = 'block';
            document.querySelector('.score').textContent = `Score: ${correctAnswers} of ${questionsDatabase.length}`;
          }
        } else {
          // Create modal
          const modal = document.createElement('div');
          modal.classList.add('modal');
          modal.innerHTML = `
            <p style="margin: 0 0 10px 0; font-weight: bold;">Oops! That's incorrect.</p>
            <p>Correct answer: ${questionsDatabase[currentQuestionIndex].answer}</p>
          `;
          document.getElementById("modal-container").appendChild(modal);

          // Create modal background and remove modal after 5 seconds
          const modalBackground = document.createElement('div');
          modalBackground.classList.add('modal-background');
          document.getElementById("modal-container").appendChild(modalBackground);

          setTimeout(() => {
            modal.remove();
            modalBackground.remove();
          }, 5000);
        }
      }

      shuffleArray(questionsDatabase);
      displayQuestion();
    </script>
  </body>
</html>

U4

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Numera - Challenge Yourself</title>
  <style>
    body {
      font-family: "Georgia", serif;
      margin: 0;
      padding: 0;
      color: #000033;
      background-color: white;
    }

    .header {
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: white;
      color: #000033;
      padding: 10px;
    }

    .header h1 {
      margin: 0;
    }

    .question-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      margin: 40px 0;
    }

    .question-box {
      border: 2px solid #000033;
      padding: 20px;
      border-radius: 15px;
      margin: 0 20px;
      width: 80%;
      max-width: 800px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .question-label {
      font-size: 24px;
    }

    .question-content {
      font-size: 20px;
      margin-top: 10px;
    }

    .answer-option-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      margin-top: 20px;
    }

    .answer-option-container.round {
      flex-wrap: nowrap;
    }

    .answer-option {
      padding: 10px;
      border-radius: 50%;
      margin: 5px;
      width: 50px;
      height: 50px;
      color: #ffffff;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .answer-option.purple {
      background-color: #a300f0;
    }

    .answer-option.purple:hover {
      background-color: #8d00d0;
    }

    .answer-option.blue {
      background-color: #0099ff;
    }

    .answer-option.blue:hover {
      background-color: #0080ff;
    }

    .true-false-container {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      margin-top: 20px;
    }

    .true-false-option-container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 0 10px;
    }

    .true-false-option {
      padding: 10px;
      border-radius: 15px;
      margin: 5px auto;
      width: 200px;
      height: 50px;
      background-color: #eeeeee;
      color: #000033;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.2s ease;
      border: none;
      font-size: 16px;
    }

    .true-false-option:hover {
      background-color: #cccccc;
    }

    .rectangle-button {
      background-color: #000033;
      color: white;
      padding: 10px 20px;
      border-radius: 15px;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      border: none;
    }

    .footer {
      background-color: white;
      color: #000033;
      padding: 10px;
      text-align: center;
      position: absolute;
      bottom: 0;
      width: 100%;
    }

    .footer__content {
      margin: 0;
    }

    .score {
      font-size: 20px;
      font-weight: bold;
      margin-top: 10px;
      color: #000033;
      padding: 10px;
      text-align: center;
    }

    .modal {
      position: fixed;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      background: white;
      border-radius: 10px;
      padding: 20px;
      box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
      z-index: 999;
    }

    .modal-background {
      position: fixed;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 998;
    }
  </style>
</head>

<body>
  <header class="header">
    <h1>Numera</h1>
  </header>
  <div class="question-container">
    <div class="question-box">
      <h3 id="question-heading"><span class="question-number">1. </span></h3>
      <p id="question-text">Loading question...</p>
      <div id="answer-input"></div>
    </div>
  </div>
  <div class="score">Score:</div>
  <footer class="footer">
    <p class="footer__content">Numera, Inc &copy; 2023 | Established in MMXXIII</p>
  </footer>
  <script>
    const questionsDatabase = [
      {
        question: "After 7 = ?",
        answer: 8,
        options: ["9", "6", "8"],
        type: "MC",
      },
      {
        question: "What comes next? 1, 2, 3, 4, = ?",
        answer: 5,
        options: ["8", "5", "7"],
        type: "MC",
      },
      {
        question: "What is after 5.   1,3,5 = ?",
        answer: 7,
        options: ["0", "7", "10"],
        type: "MC",
      },
      {
        question: "3 + 3 = ?",
        answer: 6,
        options: ["5", "6", "7"],
        type: "MC",
      },
      {
        question: "1 + 2= ?",
        answer: 3,
        options: ["2", "3", "4"],
        type: "MC",
      },
      {
        question: "How many ones are in the number 15?",
        answer: "15",
        options: ["1", "15", "10"],
        type: "MC",
      },
      {
        question: "7 Cakes plus 10 cakes?",
        answer: "17 Cakes",
        options: ["17 Cakes", "71 Cakes", "107 Cakes"],
        type: "MC",
      },
      {
        question: "Ten apples + 3 apples?",
        answer: "13 apples",
        options: ["30 apples", "13 apples", "23 apples"],
        type: "MC",
      },
      {
        question: "How many ones are in the number 14?",
        answer: "14",
        options: ["4", "1", "14"],
        type: "MC",
      },
      {
        question: "10 + 1 = 11?",
        answer: "true",
        options: ["true", "false"],
        type: "TF",
      }
    ];

    let currentQuestionIndex = 0;
    let correctAnswers = 0;

    function shuffleArray(array) {
      for (let i = array.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [array[i], array[j]] = [array[j], array[i]];
      }
      return array;
    }

    function displayNextQuestion() {
      const questionObject = questionsDatabase[currentQuestionIndex];
      document.getElementById("question-heading").innerHTML = `<h3 class="question-number">${currentQuestionIndex + 1}. </h3>`;
      document.getElementById("question-text").innerHTML = questionObject.question;
      if (questionObject.type === "MC") {
        const shuffledOptions = shuffleArray([...questionObject.options]);
        let options = "";
        for (let option of shuffledOptions) {
          let className = "";
          if (option % 2 === 0) {
            className = "blue";
          } else {
            className = "purple";
          }
          options += `<button class="answer-option ${className}" type="button" value="${option}">${option}</button>`;
        }
        if (shuffledOptions.length === 2) {
          document.getElementById("answer-input").classList.add('round');
        }
        document.getElementById("answer-input").innerHTML = `<div class="answer-option-container">${options}</div>`;
        const answerOptions = document.querySelectorAll('.answer-option');
        answerOptions.forEach((option) => {
          option.addEventListener('click', () => {
            checkAnswer(option.value);
          });
        });
      } else if (questionObject.type === "TF") {
        document.getElementById("answer-input").innerHTML = `
          <div class="true-false-container">
            <div class="true-false-option-container">
              <button class="true-false-option" type="button" value="true">True</button>
            </div>
            <div class="true-false-option-container">
              <button class="true-false-option" type="button" value="false">False</button>
            </div>
          </div>
        `;
        const trueFalseOptions = document.querySelectorAll('.true-false-option');
        trueFalseOptions.forEach((option) => {
          option.addEventListener('click', () => {
            checkAnswer(option.value);
          });
        });
      }
    }

    function checkAnswer(userAnswer) {
      const questionObject = questionsDatabase[currentQuestionIndex];
      
      if (userAnswer == questionObject.answer) {
        correctAnswers++;
      } else {
        // Create modal
        const modal = document.createElement('div');
        modal.classList.add('modal');
        modal.innerHTML = `
          <p style="margin: 0 0 10px 0; font-weight: bold;">Sorry, that's the wrong answer.</p>
          <p>Correct answer: ${questionObject.answer}</p>
        `;
        document.body.appendChild(modal);

        // Create modal background and remove modal after 2 seconds
        const modalBackground = document.createElement('div');
        modalBackground.classList.add('modal-background');
        document.body.appendChild(modalBackground);

        setTimeout(() => {
          modal.remove();
          modalBackground.remove();
        }, 5000);
      }

      currentQuestionIndex++;

      if (currentQuestionIndex < questionsDatabase.length) {
        displayNextQuestion();
      } else {
        document.getElementById("answer-input").innerHTML = `<button class="answer-option finished" onclick="location.reload()">Congratulations! You completed all the questions! Click here to restart...</button>`;
        document.getElementById("answer-input").parentNode.style.height = "inherit";
        document.querySelector('.score').style.display = 'block';
        document.querySelector('.score').textContent = `Final Score: ${correctAnswers} of ${questionsDatabase.length}`;
      }
    }

    shuffleArray(questionsDatabase);
    displayNextQuestion();
  </script>
</body>

</html>




