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


### Notes

* Opened T02.02-Exercise-AddMenu project

	gradle build failed at aapt step complaining about C:/tmp
	
		Changed to use D:/tmp, synced, build finished ok
		
		However, MainActivity.java has errors. It can't find the R class to resolve resources. Figured it was because the previous build had been interrupted.
		
		Ran Build/Rebuild Project and that fixed it.
		
	When creating the menu resource the TODO for menu.xml are listed in MainActivity.java.
	
		Kind of inconvenient so I cut and pasted them into menu.xml but the TODO tool doesn't pick them up.
		
		Changed the comment syntax from // to <!-- --> and it worked.



### Reflections Q + A

**What does "Sync Project with Gradle Files" actually do?**
**Is it different than doing a project rebuild?**