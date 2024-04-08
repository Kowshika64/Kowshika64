

class Quiz:
    def __init__(self, questions):
        self.questions = questions
        self.score = 0

    def display_question(self, question, choices):
        print(question)
        for i, choice in enumerate(choices, start=1):
            print(f"{i}. {choice}")
        user_answer = input("Enter the number of your answer: ")
        return int(user_answer)

    def check_answer(self, user_answer, correct_answer):
        if user_answer == correct_answer:
            print("Correct!")
            self.score += 1
        else:
            print("Incorrect!")
            print(f"The correct answer is: {correct_answer}")
        print(f"Score: {self.score}/{len(self.questions)}\n")

    def run_quiz(self):
        for question, choices_and_answer in self.questions.items():
            choices, answer = choices_and_answer[:-1], choices_and_answer[-1]
            user_answer = self.display_question(question, choices)
            self.check_answer(user_answer, answer)
        print(f"Final Score: {self.score}/{len(self.questions)}")
        if self.score == len(self.questions):
            print("Congratulations! You got a perfect score!")
        elif self.score >= len(self.questions) / 2:
            print("Well done! You passed the quiz.")
        else:
            print("Sorry, you didn't pass the quiz. Better luck next time.")


# Define your questions and answers here
questions = {
    "What is the capital of France?": ["London", "Paris", "Berlin", "Rome", 2],
    "What is the largest planet in our solar system?": ["Venus", "Mars", "Jupiter", "Saturn", 3],
    "Who wrote 'Romeo and Juliet'?": ["Mark Twain", "Jane Austen", "William Shakespeare", "Charles Dickens", 3],
    "What is the chemical symbol for water?": ["H2O", "CO2", "O2", "N2", 1],
    "How many continents are there?": ["5", "6", "7", "8", 3]
}

# Create an instance of the Quiz class with your questions
my_quiz = Quiz(questions)

# Run the quiz
my_quiz.run_quiz()
