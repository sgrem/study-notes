# Developing Android Apps

## Lesson 4: RecyclerView

### More Research

* [API Guide Layout/RecyclerView](https://developer.android.com/guide/topics/ui/layout/recyclerview.html)
* [android.support.v7.widget.RecyclerView](https://developer.android.com/reference/android/support/v7/widget/RecyclerView.html)
* [RecyclerView.java](https://android.googlesource.com/platform/frameworks/support/+/refs/heads/master/v7/recyclerview/src/android/support/v7/widget/RecyclerView.java)
* [Using the RecyclerView](https://guides.codepath.com/android/using-the-recyclerview)

### Notes

* An adapter provides the RV with new views as needed.
* The adapter binds data from a data souce to these views.
* The adapter sends the views to the RV in an object called a ViewHolder.
* A Layout Manager tells the RV how to lay out those views.
* Opened T03.01-Exercise-RecyclerViewLayout

	Added android:id="@+id/rv_numbers" to activity_main.xml but MainActivity still couldn't resolve it.
	
		Tried rebuilding project but no luck.
		
		Closed the project and reopened it and the id resolved ok.


### Reflections Q + A

**What are the pros and cons of RecyclerView vs ListView?**

* Weeeeell, that's a good question.