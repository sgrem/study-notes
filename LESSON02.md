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



### Reflections Q + A

#### Why not set minimum SDK for 2.3 Gingerbread API 10 and run on 99% of devices?

* **Pro:** Reaching a larger audience.

* **Pro:** Older devices are cheaper.

* **Con:** Android security patches are currently only backported to KitKat API 19.
Those fixes are provided by Google but there is no guarantee that the device
manufacturers will patch their old phones.

* **Con:** Older devices may not have the features and functionality provided by new
devices and api's. You may have to write code to manage what api's and features
will be supported and run for a given phone and SDK level.

**Quote From Lesson 2 step 9:**

Here are some examples of hardware support and features, tied to releases.
* Home screen widgets (Cupcake)
* Multiple finger tracking (Froyo)
* Tablet (Honeycomb)
* Android Beam (Jellybean)
* Android TV, Auto, Wear (Lollipop)
* Pro Audio (Marshmallow)


#### The recommendation is to always set the targetSDK to the latest Android version.
#### Can you think of any reasons not to do that?

* Yes. If you have an existing app and upgrading to the new version would break
existing code. Fixing the code may take substantial time and effort so it would
be prudent to target the older version until a migration plan can be implemented.

* **Example:** The permissions model changed drastically from Lollipop to
Marshmallow. Getting up to speed on the new model and fixing the code will
take time so keep pointing to Lollipop until the code is fixed and tested.


#### Where can you set the App Version Name and Code? Why can't you safely downgrade
#### to an old App version?

* The app version name and code can be set in the Project Structure Dialog in
Android Studio. The app store won't accept older app versions than what they already
have.


#### For Android 8.0 SDK what is the difference between the Google API system
image and the Google Play system image?

* [Stack Overflow answer:](https://stackoverflow.com/questions/45664516/difference-between-google-api-intel-x86-atom-and-google-play-intel-x86-atom-syte)

* To paraphrase Stack Overflow answer:
> Google Play will run the play store and allow download/install
apps but doesn't allow root access for debugging.
 