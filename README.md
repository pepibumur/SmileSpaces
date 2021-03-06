SmileSpaces Platform
===========
![image](http://img198.imageshack.us/img198/5672/lzht.png)

SmileSpaces is a interesting platform to find the best happy areas in your city according to many factors, curltural, healthy, users... Thanks to our advanced algorith "Felix" and exhaustive data analysis. Moreover you'll have a full API REST for implementing your own solution with our data. In our repo you'll find iOS and Android applications to have an idea of what you can do :)

:smile: Share happiness! :smile:

Take a look to our VideoLean promo video: https://videolean.com/shares/4eb1f2f3-5ed3-4ce0-9057-edbec56d9a5b

# Web Server Backend
We've developed our platform using a python based micro-framework, **Flask**. The reason why we did chose it is that it's very fast, easy to implement and powerful.
Although Flask has a Web Server for testing it's not recommended using it out of developing, that's the reason why we've deployed our server using NGINX+GUNICORN. SQLite database is the chosen solution for our initial project.

If you want to test it you don't need this configuration. Only download the serverSmile project and execute:
```python
python runSmile.py
```
#### Requiremens
- Python 2.7
- Flask
- Flask-SQLAlchemy
- Flask-Admin

( You can install all of them using PIP command )

### API Requests
File views.py includes all web paths that our API is able to process. Here you have a list of them:
- **/api/1/City**: [GET] To get a list of all the cities
- **/api/1/City/"cityID"**: [GET] To get the information of a given city (by ID)
- **/api/1/City/"cityID"**: [PUT] Update the information of a given city (by ID)
- **/api/1/City**: [POST] Create a new City
- **/api/1/City/"cityID"**: [DELETE] Delete an existing City
- **/api/1/Cell/City/"cityID"**: [GET] Get a list of all the zones of a City
- **/api/1/Cell/"cellID"**: [GET] Get detailed info for given cell (by ID)
- **/api/1/Cell/"cellID"**: [PUT] Update the information of a given Cell (By ID)
- **/api/1/Cell**: [POST] Create a new zone
- **/api/1/Cell/"cellID"**: [DELETE] Delete a given zone
- **/api/1/Data/"cellID"**: [GET] Get detailed parameters info of a Cell
- **/api/1/Data**: [POST] Create a new data object
- **/api/1/Data/"dataID"**: [PUT] Update an existing data object
- **/api/1/Data/"dataID"**: [DELETE] Delete an existing data object

*Note: Some REST request may not be implemented. We're working on these features. Some of them may not be working correctly, sorry for the inconvenience, we are on Alpha :)*

### Admin view
Thanks to Flask-Admin you'll have access to an Admin panel and take control over the backend data. The URL to access it is: http://127.0.0.1:5000/admin


# iOS Application
iOS application as a location mobile service has a main View with the map of the city ( depending on the version of the App ). In this view you'll be able to have a global sightseing of every zone with a smile/color indicating the happiness of zone. From this view you'll be able to open more details of the zone ( touching in the zone pin ) or share your feeling in the place where you are.

![image](http://img22.imageshack.us/img22/6086/j2so.png)

#### Implemented features
- **Hapiness MapView**: Browse happniness around you in your city thanks to this mapView. You'll be able to center it in your location and zoom thanks to pinch gesture. Markers wi'll be expanded like cells!. If you need more details push over one of this.
- **Add feeling to your city database**: Choose your feeling in your current place selecting a color in the gradient selector. We'll calculate your feeling from your color selection. More over ( implemented in the future ) if you connect your social accounts we'll do a semantic analysis to get more information about your current context feeling . Amazing, isn't it? Felix cat we'll do magic with all this data. Photos will be able to be attached in a next release.
- **Zone detail view**: Get more detailed information about any area. Using our chart you'll take a global idea of it according to five parameters Felix has calculated. If you are looking more information, don't worry, scroll down and discover each detailed one in a percentage way.

### Custom controls
Controls that we've created to get better UX in the app:
- **gradientProgress**: Animated gradient progress to add in tableviewCells. It includes a method to reset the progress and to animate it from 0 to a given percentage. 

![image](http://img27.imageshack.us/img27/9710/7zlw.png)

### External Controls
We would like to thanks all these control that have helped us to get faster in our development and add interesting features to improve our app. And thanks to CocoaPods too for its 3rd party libraries installation helper. 
Here they are:
```
pod 'AFNetworking', '~> 1.3.2'
pod 'SVProgressHUD'
pod 'QuickDialog'
pod 'ADClusterMapView'
pod 'NullSafe'
pod 'UIKitCategoryAdditions', :git => 'https://github.com/pepibumur/UIKitCategoryAddi$
pod 'RPRadarChart', :git => 'https://github.com/pepibumur/RPRadarChart.git'
pod 'PPiAwesomeButton', :git => 'https://github.com/pepibumur/PPiAwesomeButton.git'
pod 'PPiFlatSegmentedControl', :git => 'https://github.com/pepibumur/PPiFlatSegmented$
pod 'FlatUIKit'
pod 'XMLDictionary'
pod 'DKLiveBlur', :git => 'https://github.com/pepibumur/DKLiveBlur.git'
pod 'APParallaxHeader'
```

### Test on your own
1. Clone the repository and open iOS Folder
2. Once in this directory install CocoaPods ( you'll find more information [here](http://cocoapods.org/) about how to do it )
3. After, execute from terminal `pod install` ( be sure you are in the iOS project folder in terminal )
4. If everything goes well you should open the project **from .xcworkspace** file. 

### Some Screenshots
![image](http://imageshack.us/a/img546/4770/txlu.png)
![image](http://imageshack.us/a/img841/6818/0lso.png)
![image](http://imageshack.us/a/img7/3721/cfyh.png)
![image](http://ppinera.es/iOSData/SmileSpaces/smile.gif)

### Future guidelines
- Introduce polygon layouts in mapview to bound more detailed areas
- Add feeling connection with Server ( including add photo feature in maps )
- Information Screen with some settings.
- Active notifications
- Gamification in users profiles 

## Android
In the same way as iOS App, the Android app has a similar structure in Controllers ( Including the design ). The project works in Android version from  2.3 Gingerbread until the last version.

## Test on your own
- Download the project folder
- Open Eclipse ( If you hadn't it installed remember Android Development Kit is required too )
- Once installed, import the project into your Workspace and import Google Play Services Library
- If everything goes right, you should be able to load the project into a physical device or the simulator

## Screenshots
![image](http://imageshack.us/a/img856/4658/1a9d.png)
 ![image](http://img43.imageshack.us/img43/1778/5r6c.png)

## External controls
- **Asynchronous Http Client for Android**: An asynchronous callback-based HTTP client for Android used by Instagram, Heyzap, Trello and many other large apps. https://github.com/loopj/android-async-http

## Source
We've found all these London Feeds to our dababase Backend. The solution is global so in the future is required to adapt this platform to another city we only have to link our system with the new city sources.
Sources from London:
- Transport for London: http://www.tfl.gov.uk
- LondonAir API


## Team
![image](http://imageshack.us/a/img22/4400/69bw.png)
![image](http://img707.imageshack.us/img707/5892/0m6i.png)
![image](http://img545.imageshack.us/img545/4845/7ifz.png)
![image](http://imageshack.us/a/img546/7083/adv1.png)


- **Isaac Roldán**: Web/Backend developer and Felix's father
- **Fran Díaz**: GodFather of Felix and Social Developer
- **LLorens Delgado**: Android Developer and UI/UX designer
- **Pedro Piñera**: iOS Developer and UI/UX designer


## License

(The MIT License)

Copyright (c) 2013 SmileSpaces

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
IN THE SOFTWARE.

