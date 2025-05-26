This is a simple Python project using Flask that connects to number-generating APIs (like Prime, Fibonacci, Even, Random) and keeps track of the last 10 unique numbers it receives. It also shows you the average of those numbers

**What This Project Does**
You send a request to the app for a type of number (prime, even, etc.).

It talks to an external API and gets a list of numbers.

It keeps only the latest 10 unique numbers in memory (like a sliding window).

It then returns:
The previous list of numbers before the new ones were added.
The current list of numbers after updating.
The list of new numbers fetched.
The average of numbers in the current list.


**How to Use It**
API Endpoint
GET /numbers/<numberid>

Replace <numberid> with:
p → for Prime numbers
f → for Fibonacci numbers
e → for Even numbers
r → for Random numbers

Example

GET http://localhost:9876/numbers/p
This will fetch prime numbers from the external API and update the number window.



Example Response
{
  "windowPrevState": [2, 3, 5],
  "windowCurrState": [2, 3, 5, 7],
  "numbers": [5, 7],
  "avg": 4.25
}
windowPrevState: What was in the window before
windowCurrState: What's in the window now
numbers: New numbers that were fetched
avg: Average of all numbers in the current window

**How to Run This Project**
Step 1: Install Python Libraries
Open your terminal and run:
pip install flask requests
Step 2: Run the App
python app.py
Step 3: Use the API
Open your browser or use Postman to try:

http://localhost:9876/numbers/p
You can replace p with f, e, or r as explained above.

**Customize**
In the app.py file, you can change:

The number of items stored in the window:

WINDOW_SIZE = 10
