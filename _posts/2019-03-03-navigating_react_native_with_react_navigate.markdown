---
layout: post
title:      "Navigating React Native with React Navigate"
date:       2019-03-03 17:42:04 +0000
permalink:  navigating_react_native_with_react_navigate
---


Navigaitng an App always seems like it going to be easy - you just click and go there...  

I have found that even with the best navigation packages there has to be a lot of planning.  the plan can change but if you don't have a plan you and your users are going to get lost.

I find that drawing out a chart helps - first I list all the pages/screens:

Chart 1

* Welcome Screen
* Login
* Signup
* Recover Password
* Map
* Add Location
* List Locations
* Details
* Additional Photos
* View/Edit additional photos
* Add additional photos
* Select photos to add
* Delete photos
* Edit Location
* Delete
* Profile

Then I group them into sets and subsets:

Chart 2

- Welcome Screen
- Signup
- Login
 - Recover Password
 - Map
 - Add Location
 - List Locations
  - Details
   - Additional Photos
    - View additional photos
   - Edit Location
    - View/Edit additional photos
     - Add additional photos
      - Select photos to add
    - Delete photos
   - Delete Location
 - Profile
    

Finally I group then by navigator:


Chart 3

- LOGIN SWITCH NAVIGATOR* (This navigator decides where to go based on user input)*  - Welcome Screen
  - Loading Screen
    - Signup
    - Login
      - Recover Password
      - Map
 
 
 
APP SWITCH NAVIGATOR *(This navigator sends you into the app after login)*
  - Welcome Screen
  - Loading Screen
  - APP DRAWER NAVIGATOR 



APP DRAWER NAVIGATOR *(This navigator is offered through a "hamburger" icon and slides in from the side)*
  - DASHBOARD STACK NAVIGATOR
  - Log Out Screen (sometimes you realise you missed a screen while you are organizing) 



DASHBOARD STACK NAVIGATOR *(This navigator is used to hold all of the screens/pages in the navigation stack - it also allows them to have headers that match - all remaining screens a nested under here.)*
  - DASHBOARD TAB NAVIGATOR 



DASHBOARD TAB NAVIGATOR *(This creates a bottom tab bar that will be a direct link to the screens listed there.)*
  - MAP STACK
  - ADD LOCATION STACK
  - LIST LOCATIONS STACK
  - PROFILE STACK



MAP STACK *(By building the stack like this, it keeps the stacks isolated and avoids cross navigation.)*
  - Home Screen



ADD LOCATION STACK *(There is no need to navigate to and from single screen stacks other than through the tab bar.)*
  - Add Location Screen
	
	
	
LIST LOCATIONS STACK *(This contains all of the screens and nested stacks that have to do with individual locations.)*
  - List Locations Screen
      - Details Screen
        - Additional Photos
        - EDIT LOCATION STACK



EDIT LOCATION STACK* (This contains the screens and nested stacks that have to do with editing individual locations.)*
  - ADDITIONAL PHOTOS STACK
  - Delete Location



ADDITIONAL PHOTOS STACK* (This contains the screens relating to viewing, adding, and deleting photos of locations.)*
          - View additional photos
            - Select photos to add
          - Delete photos



PROFILE STACK (another single screen stack)
  - Profile


Once you have laid out your navigation chart **then** you can start writing your navigation elements!
