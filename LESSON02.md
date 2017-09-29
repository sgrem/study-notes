# Developing Android Apps

## Lesson 2: Create Project Sunshine

### More Research
* New Project Activity Templates
* Differences between Android versions
* Project Structure Dialog in Android Studio
* Runing adb



### Notes

* Created FavoriteToys project
	Used minimum SDK 5.1 Lollipop (API 22)
	
		Covers 69% of devices
		
		[Dashboard](https://developer.android.com/about/dashboards/index.html)
		
	Used Empty Activity Template
	
	target SDK version set to API 26: Android 8.0 (Oreo)
	
		Set in Project Structure/Modules: app/Flavors
		
	AVD has Nexus 4 API 25 Android 7.1.1 (Google APIs) x86_64
	
		Booted up ok
		
		Ran FavoriteToys App ok
		
	Created AVD: Nexus 5x API 26 Android 8.0 (Google APIs) x86
	
		Booted up ok
		
		Ran FavoriteToys App ok
		
	Physical device: Google Pixel XL API 26 Android 8.0
	
		Ran FavoriteToys App ok
		
* Android 1 launched in 2008. In the 9 years since then there have been 14 new major
platform releases.

* Exercise: Framing Favorite Toys
	Checkout T01.01-Exercise-CreateLayout branch
	
	Import ud851-Exercises project
	
		Sync fails, Messages suggests to install Build Tools 25.0.2
		
			Project Structure is missing the app module and other entries.
			
			Installed Build Tools 25.0.2 and synced.
			
			Now Project Structure looks good.
			
		Failed to resolve constraint-layout in app/build.gradle so I deleted the
		
		corresponding compile entry.
		
		Updated to Android Gradle plugin 3.0.0-beta6 and Gradle to 4.1
		
			Project build.gradle classpath 'com.android.tools.build:gradle:3.0.0-beta6'
			
			gradle-wrapper.properties distributionUrl=https\://services.gradle.org/distributions/gradle-4.1-all.zip
			
			This was needed because I'm running Android Studio 3.0 Beta 6
		
		Sync fails: unable to clean C:/tmp/ud851-Exercises
		
			I created D:/tmp and made corresponding change in project build.gradle file 
			
			Synced ok
			
			NOTE: activity_main.xml Design tab wouldn't work until project build was successful.
			
		Closed project
		
		Using git for windows bash shell to run git
		
			Added .gitignore file.
			
			`git reset HEAD` on a bunch of .idea/libraries/*.xml that I had inadvertantly added to git.
			
			Opened project back up and ran on AVD Nexus 5x API 26 and ran ok.
		
		Closed project, committed, and pushed to github.

* Exercise: Toying with Favorite Toys
	`git checkout T01.02-Exercise-DisplayToyList` and copied in .gitignore from another Android Studio project
	
	Import ud851-Exercises project
	
		To take advantage of Instant Run, improvements, and security fixes:

			updated Android Gradle plugin to 3.0.0-beta6 and Gradle to 4.1
			
		Used a StringBuilder in a foreach loop to build the list of toy names
		
		Ran successfully. Closed project, committed, and pushed to github.
		
* Exercise: See More Favorite Toys
	`git checkout T01.03-Exercise-AddScrolling` and copied in .gitignore from another Android Studio project
		
		They used a TextView append convenience function rather than StringBuilder.
		
		Completed TODOs, ran ok, closed, committed, and pushed.

### Reflections Q + A

**Why not set minimum SDK for 2.3 Gingerbread API 10 and run on 99% of devices?**

* **Pro:** Reaching a larger audience.

* **Pro:** Older devices are cheaper.

* **Con:** Android security patches are currently only backported to KitKat API 19.
Those fixes are provided by Google but there is no guarantee that the device
manufacturers will patch their old phones.

* **Con:** Older devices may not have the features and functionality provided by new
devices and api's. You may have to write code to manage what api's and features
will be supported and run for a given phone and SDK level.

**Quote From Lesson 2 step 9:**

> Here are some examples of hardware support and features, tied to releases.
* Home screen widgets (Cupcake)
* Multiple finger tracking (Froyo)
* Tablet (Honeycomb)
* Android Beam (Jellybean)
* Android TV, Auto, Wear (Lollipop)
* Pro Audio (Marshmallow)


**The recommendation is to always set the targetSDK to the latest Android version.**
**Can you think of any reasons not to do that?**

* Yes. If you have an existing app and upgrading to the new version would break
existing code. Fixing the code may take substantial time and effort so it would
be prudent to target the older version until a migration plan can be implemented.

* **Example:** The permissions model changed drastically from Lollipop to
Marshmallow. Getting up to speed on the new model and fixing the code will
take time so keep pointing to Lollipop until the code is fixed and tested.


**Where can you set the App Version Name and Code? Why can't you safely downgrade**
**to an old App version?**

* The app version name and code can be set in the Project Structure Dialog in
Android Studio. The app store won't accept older app versions than what they already
have.


**For Android 8.0 SDK what is the difference between the Google API system
image and the Google Play system image?**

* [Stack Overflow answer](https://stackoverflow.com/questions/45664516/difference-between-google-api-intel-x86-atom-and-google-play-intel-x86-atom-syte)

* To paraphrase Stack Overflow answer:
> Google Play will run the play store and allow download/install
apps but doesn't allow root access for debugging.
 