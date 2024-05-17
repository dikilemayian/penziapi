Penzi Dating App

Penzi is a mobile dating application designed to connect users with potential matches based on their preferences. The app enables users to register, update their profiles, describe themselves, and find matches by sending structured text messages. Penzi leverages Django, Django REST Framework, and MySQL to handle user data and matchmaking processes efficiently.

Table of Contents
Features
Technology Stack
Setup
Usage
API Endpoints
Classes and Methods
Logging
Features

User Registration
Users can easily register by sending a text message in a specific format. This information is stored in the database, creating a new user profile.

Profile Update
Users can update their profile details at any time by sending a message in a specified format. This allows users to keep their profiles current with their latest information.

Self-Description
Users can add a personal description by sending a message starting with a specific keyword. This description helps potential matches learn more about the user.

Matchmaking
To find potential matches, users can send a message in a specified format. The app will then search the database for users that match the specified criteria and return a list of potential matches.

Match Navigation
Users can navigate through their matches by sending specific commands to view the next or previous set of matches. This ensures users can explore multiple potential matches.



Technology Stack

Backend: Django and Django REST Framework
Database: MySQL
Messaging: Text messages (SMS) to interact with the app

Setup
Prerequisites
Python 3.x
Django
Django REST Framework
MySQL

Installation
Clone the repository and navigate to the project directory.
Install the required dependencies.
Configure your database settings in the Django settings file.
Run the database migrations.
Start the Django development server.

Usage
Registration
Users can register by sending a text message in a specific format with their basic information.

Updating User Details
Users can update their additional details by sending a text message in a specified format.

Describing Yourself
Users can add a brief personal description by sending a message starting with a specific keyword.

Finding Matches
Users can find matches by sending a text message in a specified format.

Navigating Matches
Users can view the next or previous set of matches by sending specific commands.

API Endpoints
PenziMessageView
POST /api/message/: Handles incoming messages and returns appropriate responses.
GET /api/message/: Fetches matches based on user preferences.
UserProfileDetail
GET /api/user-profile/{id}: Retrieves user profile details based on the provided user ID.
Classes and Methods
MatchProcessor
Handles match processing based on user preferences.

Methods:
Processes match requests.
Retrieves the next set of matches.
Retrieves the previous set of matches.
Formats the match results into a string.
PenziMessageView
Handles incoming messages and routes them to the appropriate processor.

Methods:
Handles POST requests for incoming messages.
Handles GET requests to fetch matches.
Generates response messages based on content.
Saves incoming messages to the database.
Saves response messages to the database.
Saves new user information.
Updates existing user information.
Processes start messages.
Processes detail update messages.
Processes self-description messages.
Logging
The application uses Python's built-in logging module to log errors and important events.

