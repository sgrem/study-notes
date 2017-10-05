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
		
	



### Reflections Q + A

**What does "Sync Project with Gradle Files" actually do?**
**Is it different than doing a project rebuild?**

* 


Uri.Builder framework class allows us to create a well-formed Uri without

having to worry about the particulars of Uri components.

**What are these Uri components and give examples of some of these particulars?**

* [Uri class](https://developer.android.com/reference/android/net/Uri.html)


**If you have an Android Uri why do you need a Java URL?**

**What are tradeoffs between Uri.Builder vs Uri.parse(URL_STRING).buildUpon()?**

* [Uri builder in Android StackOverflow discussion](https://stackoverflow.com/questions/19167954/use-uri-builder-in-android-or-create-url-with-variables)
