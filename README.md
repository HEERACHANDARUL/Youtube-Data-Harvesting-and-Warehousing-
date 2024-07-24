YouTube Data Harvesting and Warehousing
Project Overview
This project is designed to harvest data from YouTube channels using the YouTube Data API. It then stores the collected data in a MongoDB database and allows migration to a PostgreSQL database. The project also includes a Streamlit app for easy data interaction and visualization.

Features
YouTube Data API Integration: Fetches detailed information about channels, videos, playlists, and comments.
Data Storage: Uses MongoDB for storing raw data and PostgreSQL for structured data storage.
Streamlit Interface: Provides a user-friendly interface to interact with the data.
SQL Queries: Enables users to run predefined queries on the PostgreSQL database for data analysis.
Requirements
Python 3.x
Google API Client
pymongo
psycopg2
pandas
streamlit
Setup Instructions
Clone the Repository:

sh
Copy code
git clone https://github.com/yourusername/youtube-data-harvesting.git
cd youtube-data-harvesting
Install Dependencies:

sh
Copy code
pip install google-api-python-client pymongo psycopg2 pandas streamlit
API Key Configuration:
Replace YOUR_API_KEY in the script with your actual YouTube Data API key:

python
Copy code
api_key = "YOUR_API_KEY"
MongoDB Configuration:
Replace the MongoDB connection string with your own:

python
Copy code
client = pymongo.MongoClient("your_mongodb_connection_string")
PostgreSQL Configuration:
Ensure your PostgreSQL database is set up and update the connection details:

python
Copy code
mydb = psycopg2.connect(
    host="localhost",
    user="postgres",
    password="your_password",
    database="youtube_data",
    port="5432"
)
How to Run
Run the Streamlit App:

sh
Copy code
streamlit run app.py
Using the App:

Enter the YouTube channel ID to collect and store data.
Migrate collected data to PostgreSQL.
Use the provided SQL queries to analyze the data.
Project Structure
app.py: Main script for the Streamlit app.
api.py: Contains functions for interacting with the YouTube Data API.
database.py: Functions for MongoDB and PostgreSQL interactions.
queries.py: Predefined SQL queries for data analysis.
Functions Overview
API Functions
Api_connect(): Connects to the YouTube Data API.
get_channel_info(channel_id): Retrieves channel information.
get_videos_ids(channel_id): Retrieves video IDs from a channel.
get_vedio_info(video_ids): Retrieves video information.
get_comment_info(video_ids): Retrieves comment information.
get_playlist_details(channel_id): Retrieves playlist details.
Database Functions
channel_details(channel_id): Collects and stores channel data in MongoDB.
channels_table(channel_name_s): Creates and populates the channels table in PostgreSQL.
playlists_table(channel_name_s): Creates and populates the playlists table in PostgreSQL.
vedios_table(channel_name_s): Creates and populates the videos table in PostgreSQL.
comments_table(channel_name_s): Creates and populates the comments table in PostgreSQL.
tables(single_channel): Orchestrates the creation and population of all tables.
Streamlit Functions
show_channels_table(): Displays the channels table.
show_playlists_table(): Displays the playlists table.
show_videos_table(): Displays the videos table.
show_comments_table(): Displays the comments table.
SQL Queries
The app includes predefined SQL queries for various analytical purposes, such as:

All videos and their channel names.
Channels with the most number of videos.
The 10 most viewed videos.
Number of comments on each video.
Videos with the highest likes.
Likes of all videos.
Views of each channel.
Videos published in 2022.
Average duration of all videos in each channel.
Videos with the highest number of comments.
License
This project is licensed under the MIT License.

Acknowledgements
Google YouTube Data API
Streamlit
MongoDB
PostgreSQL
