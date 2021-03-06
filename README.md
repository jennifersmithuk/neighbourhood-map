# Neighbourhood Map

Udacity Google Scholarship Phase 2 Project 8 - React app using APIs. This was the final project of the Nanodegree. The site has been deployed to [Heroku](https://london-sushi-neighbourhood-map.herokuapp.com/), is live and is using config vars to hold API keys.

## Table of Contents

* [Project Background](#projectbackground)
* [Instructions](#instructions)
* [Dependencies](#dependencies)
* [API Keys](#apikeys)
* [Create React App](#createreactapp)

## Project Background

This was project 8, the final project, in phase 2 of the Google Udacity Scholarship studying for a Udacity Nanodegree in Front End Web Development.

In this project we were given no starter code and asked to create a React app featuring a map of our chosen area and places of interest. We were to use a Map API such as Google and another third party API to fetch data about the places. This project uses Google Maps API and Foursquare to fetch data about venues in the map area.

New JS files were created for each component and import/require statements were used when needed. React-Google-Maps was used for handling the xMap.

## Instructions

Download all files locally.
In your terminal:
* install all project dependencies with `npm install`
* start the development server with `npm start`
React app will start automatically on its own server and open in your browser.

PLease note that the package used to build the site: `create-react-app` means that the site comes with a pre-installed service worker to enable offline use. However this only works in production mode.

You can run the site in production mode by using the following commands in your terminal: `npm run build` then `serve -s build`. You can then use your browser and visit `localhost:5000`.

## Dependencies

* [NodeJs](https://nodejs.org/en/)
* [NPM](https://www.npmjs.com/)

## API Keys

For the app to work on your local machine you will need two sets of API keys for Google Maps and Foursquare. Details below.

*Google:* Google recently changed their pricing structure and all new projects must be associated with a billing account which means you need to provide a credit card number in order to get API keys. If you only need to make a low level of API calls you are unlikely to be charged for the service. [Google's guide to creating an API key](https://cloud.google.com/docs/authentication/api-keys?hl=en-GB&visit_id=636767026743844950-1464672799&rd=1). Once you have an API key you need to replace "MYAPIKEY" in the URL with your own API key. The URL is needed for the Map component to call the Google Maps API and you will need to add this to your environmental variables (explained below):

`googleMapURL="https://maps.googleapis.com/maps/api/js?key=MYAPIKEY&v=3.exp&libraries=geometry,drawing,places"`

Make sure when when you have your API key that you set the [application restrictions](https://developers.google.com/maps/api-key-best-practices) so that the key only works for your site.

*Foursquare:* This app uses the Places API to fetch venue information. The search parameters are "sushi" and a Lat Long for central London (App.js: lines 22 & 23). These parameters can be changed. In order to get the API keys to run this app you need to set up a [Developer account](https://developer.foursquare.com/docs/api) and follow the steps to get your clientID and clientSecret keys.

Once you have all the API keys you will need to create a .env file in the root directory of your app. In this file it will need to look like this:

```
REACT_APP_clientID=YOUR_CLIENTID
REACT_APP_clientSecret=YOUR_CLIENT_SECRET
REACT_APP_Google_API_URL=YOUR_URL
```

The code in App.js will pull these environmental variables from the .env file and you will be able to run the app on your local machine. Please note that if you publish the code with your API keys, anyone using React will still be able to see these API keys as they run at build time and are visible within the code.

## Create React App

This project was bootstrapped with [Create React App](https://github.com/facebookincubator/create-react-app). You can find more information on how to perform common tasks. [here](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md).

## Project Rubric

Interface Design:
- Responsiveness: All application components render on-screen in a responsive manner.
- Usability: All application components are usable across modern desktop, tablet, and phone browsers.

Application Functionality:
- Location Filter:
Includes a text input field or dropdown menu that filters the map markers and list items to locations matching the text input or selection. Filter function runs error-free.

List View:
- A list-view of location names is provided which displays all locations by default, and displays the filtered subset of locations when a filter is applied.
- Clicking a location on the list displays unique information about the location, and animates its associated map marker (e.g. bouncing, color change.)
- List functionality is responsive and runs error free.

Map and Markers:
- Map displays all location markers by default, and displays the filtered subset of location markers when a filter is applied.
- Clicking a marker displays unique information about a location somewhere on the page (modal, separate div, inside an infoWindow).
- Any additional custom functionality provided in the app functions error-free.

Asynchronous Data Usage:
- Asynchronous API Requests: Application utilizes the Google Maps API or another mapping system and at least one non-Google third-party API.
- All data requests are retrieved in an asynchronous manner using either the Fetch API or XMLHttpRequest.

Error Handling:
- Data requests that fail are handled gracefully using common fallback techniques (i.e. AJAX error or fail methods). 'Gracefully' means the user isn’t left wondering why a component isn’t working. If an API doesn’t load there should be some visible indication on the page that it didn’t load.

Documentation:
- README: A README file is included detailing all steps required to successfully run the application.

Comments:
- Comments are present and effectively explain longer code procedures.

Location Details Functionality:
- Additional Location Data
- Functionality providing additional data about a location is provided and sourced from a 3rd party API. Information can be provided either in the marker’s infoWindow, or in an HTML element in the DOM (a sidebar, the list view, a modal, etc.)
- Provide attribution for the source of additional data. For example, if using Foursquare, indicate somewhere in your UI and in your README that you are using Foursquare data.

Error Free:
- Application runs without console errors.
- Usability
- Functionality is presented in a usable and responsive manner.

Accessibility:
- Focus: Focus is appropriately managed allowing users to noticeably tab through each of the important elements of the page. Modal or interstitial windows appropriately lock focus.

Site elements are defined semantically:
- Elements on the page use the appropriate semantic elements. For those elements in which a semantic element is not available, appropriate ARIA roles are defined.

Accessible Images:
-All content-related images include appropriate alternate text that clearly describes the content of the image.

Offline Use:
- Service Worker: When available in the browser, the site uses a service worker to cache responses to requests for site assets. Visited pages are rendered when there is no network access.

Application Architecture:
- Proper Use of React
- React code follows a reasonable component structure.
- State control is managed appropriately: event handlers are passed as props to child components, and state is managed by parent component functions when appropriate.
- There are at least 5 locations in the model. These may be hard-coded or retrieved from a data API.
