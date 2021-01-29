# README

# COVID BOREDOM BUSTER Technical Documentation
Created by: Raz Al-Jaf and Kat Leight

COVID BOREDOM BUSTER is a full stack application that allows a user to login with their name, get a random activity suggestion by activity type, and save that activity to a list of favorites.
 

## SUMMARY
The COVID vaccine is rolling out, but in the mean time, we're all SOOOO BORED. Mix up your routine and get new activity suggestions to try out. 

This app allows a user to login with a name.  
A new user will automatically be created if their name doesn't exist.
The user can get a random activity suggestion based the type of activity selected.   
The user can save the activity to a favorites list and view their favorites.  
The user can delete a favorite from their favorites list.   
The user can view their favorite activities and filter by activity type(select options) or activity name (dynamic text input).    
User can log out when they are finished with the session.
User's name, and favorite activities are stored in a SQLite3 database, so the information is stored from session to session.   

## API
The API used for this app is https://www.boredapi.com/
Random activities are GET request by type to 
https://www.boredapi.com/activity?type=:type

If an activity is saved to a user's favorites, the activity is also saved to the SQLite3 database. 

## BACKGROUND INFORMATION

ACTIVITY TYPES

Activity types include: "Education", "Recreational", "Social", "Diy", "Charity", "Cooking", "Relaxation", "Music", and "Busywork."

PRICE
Price is returned from the API and stored in the database as a float between 0 and 1, describing the cost of the event with zero being free. The app serializes this data to display price as follows:  
    price = 0 : dispalyed as "Free"  
    0.0 < price < 0.3 : displayed as "Cheap"  
    0.3 < price < 0.6 : displayed as "Moderate  
    0.61 < price = "Moderate"  

ACCESSIBILITY  
Acessibility is returned from the API and stored in the database as a float between 0 and 1, describing how possible an event is to do with zero being the most accessible. The app serializes this data to display accessibility as follows:  
    accessibility = 0 : displayed as "Accessible to Most"  
    0.0 < accessibility < 0.6 : displayed as "Somewhat Accessible"  
    0.61 < accessibility = displayed as "Limited Accessibility"  

Future iterations could include an option for a user to add their own activities and include these user activities in the random suggestions. Full login could be implemented with a username and password. Users could rate activities or check off ones they've tried. 

## TECHNOLOGY
This app was created using Ruby on Rails, ActiveRecord, Javascript, and SQLite3. 

## DEPLOYMENT
To use this app, download the files, cd into the backend folder, and run bundle install, then rails db:migrate.  
Run your rails server on port 9000 with rails s -p 9000.  
Cd into your frontend and run lite-server. 
# COVID-Boredom-Buster
