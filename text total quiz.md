<!--
author:  Your Name
email:   your.email@example.com
version: 0.1.0
language: en
comment: MCQ Quiz with Score Calculation

@hidden
<script>
// Initialize score
let quiz_score = 0;

// Track answers
let answers = {
  q1: "",
  q2: "",
  q3: "",
  q4: "",
  q5: ""
};

// Correct answers
const correct_answers = {
  q1: "a",
  q2: "d",
  q3: "e",
  q4: "d",
  q5: "e"
};

// Calculate score
function calculateScore() {
  quiz_score = 0;
  if(answers.q1 === correct_answers.q1) quiz_score++;
  if(answers.q2 === correct_answers.q2) quiz_score++;
  if(answers.q3 === correct_answers.q3) quiz_score++;
  if(answers.q4 === correct_answers.q4) quiz_score++;
  if(answers.q5 === correct_answers.q5) quiz_score++;
  
  return quiz_score;
}

// Save answer
function saveAnswer(question, answer) {
  answers[question] = answer;
}
</script>

@saveQ1: @input
<script>
saveAnswer("q1", "@input");
</script>

@saveQ2: @input
<script>
saveAnswer("q2", "@input");
</script>

@saveQ3: @input
<script>
saveAnswer("q3", "@input");
</script>

@saveQ4: @input
<script>
saveAnswer("q4", "@input");
</script>

@saveQ5: @input
<script>
saveAnswer("q5", "@input");
</script>

@results
<script>
let score = calculateScore();
let message = "";

if(score === 5) {
  message = "Excellent! You got all answers correct!";
} else if(score >= 3) {
  message = "Good job! You did well on this quiz.";
} else {
  message = "Keep practicing! You can do better.";
}

send.liascript(`
### Final Score
**Your final score is: ${score}/5**

${message}
`);
</script>

# Quiz: Question Type Examples

**Instructions:**
- Answer each question by selecting one option.
- Submit your answer for each question.
- You will get 1 point for each correct answer.
- Your final score will be displayed at the end.

## Question 1
**"Do you use public transport regularly?"**

[(a)] a. Yes
[(b)] b. No

@saveQ1  

## Question 2
**"Which of the following devices do you own?"**

[(a)] a. Smartphone
[(b)] b. Tablet
[(c)] c. Laptop
[(d)] d. Desktop

@saveQ2  

## Question 3
**"What is your age group?"**

[(a)] a. Under 18
[(b)] b. 18-24
[(c)] c. 25-34
[(d)] d. 35-44
[(e)] e. 45+

@saveQ3  

## Question 4
**"What is your favourite social media platform?"**

[(a)] a. Facebook
[(b)] b. Instagram
[(c)] c. Twitter
[(d)] d. LinkedIn

@saveQ4  

## Question 5
**"How satisfied are you with our customer service?"**

[(a)] a. Very Satisfied
[(b)] b. Satisfied
[(c)] c. Neutral
[(d)] d. Dissatisfied
[(e)] e. Very Dissatisfied

@saveQ5  

## Submit Quiz
Click the button below to see your results:

<button onclick="eval(`@results`)">Submit Quiz</button>