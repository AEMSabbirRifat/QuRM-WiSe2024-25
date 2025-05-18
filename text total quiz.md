<!--
author:  Your Name
email:   your.email@example.com
version: 0.1.0
language: en
comment: MCQ Quiz with Score Calculation

@hidden
<script>
// Initialize score
window.quiz_score = 0;

// Define correct answers
window.correct_answers = {
  q1: "a",
  q2: "d", 
  q3: "e",
  q4: "d",
  q5: "e"
};
</script>

# Quiz: Question Type Examples

**Instructions:**
- Answer each question by selecting one option.
- After answering all questions, click the "Submit Quiz" button.
- You will get 1 point for each correct answer.
- Your final score will be displayed at the end.

## Question 1
**"Do you use public transport regularly?"**

[(a)] a. Yes
[(b)] b. No

## Question 2
**"Which of the following devices do you own?"**

[(a)] a. Smartphone
[(b)] b. Tablet
[(c)] c. Laptop
[(d)] d. Desktop

## Question 3
**"What is your age group?"**

[(a)] a. Under 18
[(b)] b. 18-24
[(c)] c. 25-34
[(d)] d. 35-44
[(e)] e. 45+

## Question 4
**"What is your favourite social media platform?"**

[(a)] a. Facebook
[(b)] b. Instagram
[(c)] c. Twitter
[(d)] d. LinkedIn

## Question 5
**"How satisfied are you with our customer service?"**

[(a)] a. Very Satisfied
[(b)] b. Satisfied
[(c)] c. Neutral
[(d)] d. Dissatisfied
[(e)] e. Very Dissatisfied

## Submit Quiz

<div>
<lia-btn text="Submit Quiz" click="eval('calculateScore()')"></lia-btn>
</div>

<script>
function calculateScore() {
  window.quiz_score = 0;
  
  // Check answers
  if(document.getElementsByName("q1")[0].checked && "a" === window.correct_answers.q1) window.quiz_score++;
  if(document.getElementsByName("q2")[3].checked && "d" === window.correct_answers.q2) window.quiz_score++;
  if(document.getElementsByName("q3")[4].checked && "e" === window.correct_answers.q3) window.quiz_score++;
  if(document.getElementsByName("q4")[3].checked && "d" === window.correct_answers.q4) window.quiz_score++;
  if(document.getElementsByName("q5")[4].checked && "e" === window.correct_answers.q5) window.quiz_score++;
  
  // Display result
  let message = "";
  if(window.quiz_score === 5) {
    message = "Excellent! You got all answers correct!";
  } else if(window.quiz_score >= 3) {
    message = "Good job! You did well on this quiz.";
  } else {
    message = "Keep practicing! You can do better.";
  }
  
  // Show results
  send.liascript(`
  ### Final Score
  **Your final score is: ${window.quiz_score}/5**

  ${message}
  `);
}
</script>
