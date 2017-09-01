# T06.04-Exercise-UseResources
This example coming from udacity [udacity](https://github.com/udacity/ud851-Exercises/tree/student/Lesson06-Visualizer-Preferences/T06.08-Solution-PreferenceSummary)

I just use this to show a better [solution](https://stackoverflow.com/questions/531427/how-do-i-display-the-current-value-of-an-android-preference-in-the-preference-su) for ListPreference summary

Just need to 2 steps:
```
Add android:summary="%s" into ListPreference
```
```
Implement onSharedPreferenceChanged
    @Override
    public void onSharedPreferenceChanged(SharedPreferences sharedPreferences, String key) {
        Preference pref = findPreference(key);

        if (pref instanceof ListPreference) {
            ListPreference listPref = (ListPreference) pref;
            pref.setSummary(listPref.getEntry());
        }
    } 
```
Please check code for details
