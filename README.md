Penzi Dating App

Penzi is a dating app that connects users based on their preferences. This README file will guide you through the setup, usage, and features of the Penzi Dating App.

Table of Contents
Features
Setup
Usage
API Endpoints
Classes and Methods
Logging

Features
User Registration
Register a New User: Users can register by sending a message in the format:
less
Copy code
start#name#age#gender#county#town
Profile Update
Update User Details: Users can update their profile details by sending:
less
Copy code
details#levelOfEducation#profession#maritalStatus#religion#ethnicity
Self-Description
Add a Description: Users can add a personal description by sending:
Copy code
MYSELF description
Matchmaking
Find Matches: Users can find potential matches by sending:
less
Copy code
match#age-range#town#gender
Match Navigation
View Next Matches: To view the next set of matches, users can send:

vbnet
Copy code
NEXT
View Previous Matches: To view the previous set of matches, users can send:

Copy code
PREV
Setup
Prerequisites
Python 3.x
Django
Django REST Framework
MySQL
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/penzi-dating-app.git
cd penzi-dating-app
Install dependencies:

bash
Copy code
pip install -r requirements.txt
Configure your database settings in settings.py:

bash
Copy code
python manage.py migrate
Start the Django development server:

bash
Copy code
python manage.py runserver
Usage
Registration
To register, send a message in the format:
less
Copy code
start#name#age#gender#county#town
Updating User Details
To update user details, send a message in the format:
less
Copy code
details#levelOfEducation#profession#maritalStatus#religion#ethnicity
Describing Yourself
To add a description, send a message starting with:
Copy code
MYSELF description
Finding Matches
To find matches, send a message in the format:
less
Copy code
match#age-range#town#gender
Navigating Matches
To view the next set of matches, send:

vbnet
Copy code
NEXT
To view the previous set of matches, send:

Copy code
PREV
API Endpoints
PenziMessageView
POST /api/message/: Handles incoming messages and returns appropriate responses.
Example request:
json
Copy code
{
  "message_content": "start#John Doe#26#Male#Nakuru#Naivasha",
  "msisdn": "254700000001"
}
UserProfileDetail
GET /api/user-profile/{id}: Retrieves user profile details based on the provided user ID.
Classes and Methods
MatchProcessor
Handles match processing based on user preferences.

Methods:
process_match_message(message_content, msisdn): Processes match requests.
get_next_matches(msisdn): Retrieves the next set of matches.
get_prev_matches(msisdn): Retrieves the previous set of matches.
format_matches_response(potential_matches): Formats the match results into a string.
PenziMessageView
Handles incoming messages and routes them to the appropriate processor.

Methods:
post(request): Handles POST requests for incoming messages.
get(request): Handles GET requests to fetch matches.
generate_response_message(message_content, msisdn): Generates response messages based on content.
save_message_from(message_content, msisdn): Saves incoming messages to the database.
save_message_to(response_message, short_code): Saves response messages to the database.
save_user_info(message_content, msisdn): Saves new user information.
update_user_info(msisdn, message_content): Updates existing user information.
process_start_message(message_content): Processes start messages.
process_details_message(message_content): Processes detail update messages.
process_myself_message(message_content): Processes self-description messages.
Logging
The application uses Python's built-in logging module to log errors and exceptions.
Logs can be found in the configured log file or console output based on the logger configuration.
