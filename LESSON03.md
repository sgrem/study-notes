# Developing Android Apps

## Lesson 3: Connect to the Internet

### More Research
* Gradle
* Android Gradle plugin API and targets
* aapt
* Android Studio Gradle and Gradle Console tabs
* [app namespace](https://stackoverflow.com/questions/36044383/whats-the-use-of-app-namespace-in-android-xml)
* [Menu Resource](https://developer.android.com/guide/topics/resources/menu-resource.html)
* [Menu API Guide](https://developer.android.com/guide/topics/ui/menus.html)
* [Uri.Builder](https://developer.android.com/reference/android/net/Uri.Builder.html)


### Notes

* Opened T02.02-Exercise-AddMenu project.

	gradle build failed at aapt step complaining about C:/tmp.
	
		Changed to use D:/tmp, synced, build finished ok.
		
		However, MainActivity.java has errors. It can't find the R class to resolve

		resources. Figured it was because the previous build had been interrupted.
		
		Ran Build/Rebuild Project and that fixed it.
		
	When creating the menu resource the TODO for menu.xml are listed in MainActivity.java.
	
		Kind of inconvenient so I cut and pasted them into menu.xml but the TODO

		tool doesn't pick them up.
		
		Changed the comment syntax from // to <!-- --> and it worked.
		
	Create options menu in Activity.
	
		override onCreateOptionsMenu.
		
		attach our menu to the system menu that's passed into onCreateOptionsMenu.
		
			MenuInflater.inflate(R.menu."menu xml resource file", menu).
	
	Create options menu listener in Activity.
	
		override onMenuItemSelected(item).
		
		get integer item id using getItemId(item).
		
		If or switch on itemId to select the action.
		
		
* Opened T02.03-Exercise-DisplayUrl.

	can't find R class in Activity.
	
		Changed C:/tmp to D:/tmp in project build.gradle file and synced.
		
		Ran build/rebuild but R still not resolved.
		
		Closed and opened project and it was ok.
		
	Uri.parse(String uriString): Uri.
	
		Static method that parses the given encoded Uri string and creates a Uri.


* Opened T02.04-Exercise-ConnectingToTheInternet

	Anything beyond gingerbread will give following exception:
	
	com.example.android.datafrominternet E/AndroidRuntime: FATAL EXCEPTION: main
	
	Process: com.example.android.datafrominternet, PID: 6245
	
	android.os.NetworkOnMainThreadException


* Opened T02.05-Exercise-CreateAsyncTask

	Commented out the internet permission from the manisfest.
	
		java.lang.RuntimeException: An error occurred while executing doInBackground()
		
		Caused by: java.lang.SecurityException: Permission denied (missing INTERNET permission?)
		
	Entered empty query ""
	
		W/System.err: java.io.FileNotFoundException: https://api.github.com/search/repositories?q=&sort=stars


* Opened T02.06-Exercise-AddPolish

	Does the android:id="@+id/id_name" have to be the first xml attribute of a widget? 


* Opened S02.01-Exercise-Networking


* Opened S02.02-Exercise-Menus

	If you leave out app:showAsAction="ifroom" it only shows the overflow elipsis on the action bar.
	
	I selected the dynamic url in NetworkUtils so I could see the forecast change when I click Refresh.


* Opened S02.03-Exercise-Polish

	App crashed

		E/AndroidRuntime: FATAL EXCEPTION: main
	
		MainActivity: android.view.InflateException: Binary XML file line #0: ScrollView can host only one direct child
	
		Moved ProgressBar and error TextView out of ScrollView and directly into the FrameLayout then it ran ok
	
	Refresh Bad
	
		background tasks and ability of server to send messages there is no reason to hit refresh.
		
		Like a good butler, data should be there before you even know you want it.
		
		AsyncTask also bad because we shouldn't couple a background task with a foreground activity.


### Reflections Q + A

**What does "Sync Project with Gradle Files" actually do?**
**Is it different than doing a project rebuild?**

* 


Uri.Builder framework class allows us to create a well-formed Uri without

having to worry about the particulars of Uri components.

**What are these Uri components and give examples of some of these particulars?**




**What is an Android Uri?**

* [Uri RFC 2396](http://www.faqs.org/rfcs/rfc2396.html)

* [Android Uri class](https://developer.android.com/reference/android/net/Uri.html)

	In the interest of performance, this class performs little to no validation.

	Behavior is undefined for invalid input.

	This class is very forgiving--in the face of invalid input, it will return garbage

	rather than throw an exception unless otherwise specified.


**What is a Java URL? Do you need to use both an Android Uri and a Java URL?**

* [A Beginners Guide to URLs](http://web.archive.org/web/20051219043731/http://archive.ncsa.uiuc.edu/SDG/Software/Mosaic/Demo/url-primer.html)

* [Java URL class](https://developer.android.com/reference/java/net/URL.html)



**What are tradeoffs between Uri.Builder vs Uri.parse(URL_STRING).buildUpon()?**

* [Uri builder in Android StackOverflow discussion](https://stackoverflow.com/questions/19167954/use-uri-builder-in-android-or-create-url-with-variables)

**Uri.parse parses a given encoded Uri string. What is an encoded Uri string?**
