# Develop an Android Application Using ListView with ArrayAdapter and Implement Item Click Handling

## Project Name: `ListViewDemo`

## Aim

To develop an Android application using ListView and ArrayAdapter to display a list of programming languages and implement item click handling to show the selected language using a Toast message.

## Technologies Used

- **Programming Language:** Java
- **IDE:** Android Studio
- **UI Design:** XML
- **UI Component:** ListView
- **Adapter:** ArrayAdapter
- **Event Handling:** OnItemClickListener

## Project Structure

```text
ListViewDemo/
├── app/
│   └── src/
│       └── main/
│           ├── java/
│           │   └── com/
│           │       └── example/
│           │           └── listviewdemo/
│           │               └── MainActivity.java
│           ├── res/
│           │   └── layout/
│           │       └── activity_main.xml
│           └── AndroidManifest.xml
└── README.md
```

---

## 1. `activity_main.xml`

**Location:** `app/src/main/res/layout/activity_main.xml`

This XML file defines a vertical LinearLayout containing a heading and a ListView to display programming languages.

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="10dp">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Programming Languages"
        android:textSize="24sp"
        android:textStyle="bold"
        android:paddingBottom="10dp" />

    <ListView
        android:id="@+id/listView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</LinearLayout>
```

---

## 2. `MainActivity.java`

**Location:** `app/src/main/java/com/example/listviewdemo/MainActivity.java`

This Java class initializes the ListView, creates an ArrayAdapter, displays the programming languages, and handles item clicks using `setOnItemClickListener()`.

```java
package com.example.listviewdemo;

import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.ArrayAdapter;
import android.widget.ListView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    ListView listView;

    String[] languages = {
        "Java",
        "Python",
        "C",
        "C++",
        "Kotlin",
        "PHP",
        "JavaScript",
        "Swift"
    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        listView = findViewById(R.id.listView);

        ArrayAdapter<String> adapter = new ArrayAdapter<>(
            this,
            android.R.layout.simple_list_item_1,
            languages
        );

        listView.setAdapter(adapter);

        listView.setOnItemClickListener(
            new AdapterView.OnItemClickListener() {
                @Override
                public void onItemClick(
                    AdapterView<?> parent,
                    View view,
                    int position,
                    long id
                ) {
                    String item = languages[position];

                    Toast.makeText(
                        MainActivity.this,
                        "Selected: " + item,
                        Toast.LENGTH_SHORT
                    ).show();
                }
            }
        );
    }
}
```

---

## 3. `AndroidManifest.xml`

**Location:** `app/src/main/AndroidManifest.xml`

Ensure that `MainActivity` is registered as the launcher activity.

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android">

    <application
        android:allowBackup="true"
        android:label="ListViewDemo"
        android:supportsRtl="true"
        android:theme="@style/Theme.ListViewDemo">

        <activity
            android:name=".MainActivity"
            android:exported="true">

            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>

        </activity>

    </application>

</manifest>
```

**Note:** The theme name must match your Android Studio project's theme. Keep the existing theme reference if its name differs.

---

## 4. How to Run the Application

1. Open Android Studio.
2. Create a new Android project named `ListViewDemo`.
3. Select **Java** as the programming language.
4. Set the package name to `com.example.listviewdemo`.
5. Replace the code in `activity_main.xml` with the provided XML code.
6. Replace the code in `MainActivity.java` with the provided Java code.
7. Check that `MainActivity` is declared correctly in `AndroidManifest.xml`.
8. Run the application on an emulator or Android device.
9. Observe the list of programming languages.
10. Click any language to display the selected item in a Toast message.

---

## 5. Expected Output

### Application Screen

```text
+----------------------------------+
| Programming Languages            |
|----------------------------------|
| Java                             |
|----------------------------------|
| Python                           |
|----------------------------------|
| C                                |
|----------------------------------|
| C++                              |
|----------------------------------|
| Kotlin                           |
|----------------------------------|
| PHP                              |
|----------------------------------|
| JavaScript                       |
|----------------------------------|
| Swift                            |
+----------------------------------+
```

### Item Click Output

When the user clicks **Python**, a Toast message appears:

```text
Selected: Python
```

When the user clicks **Java**, the message changes to:

```text
Selected: Java
```

The message depends on the selected programming language.

---

## 6. Working of the Application

1. The application starts and displays the heading and ListView.
2. An array stores the names of eight programming languages.
3. An ArrayAdapter connects the array data to the ListView.
4. `setAdapter()` displays the programming languages on the screen.
5. `setOnItemClickListener()` detects when the user clicks an item.
6. The `position` parameter identifies the selected item's position in the array.
7. A Toast message displays the selected programming language.

### Flowchart

```text
       Start Application
               |
               v
       Load activity_main.xml
               |
               v
        Initialize ListView
               |
               v
      Create Array of Languages
               |
               v
        Create ArrayAdapter
               |
               v
       Display Programming List
               |
               v
         User Clicks Item
               |
               v
       Identify Selected Item
               |
               v
        Display Toast Message
               |
               v
              End
```

---

## 7. Key Concepts

- **ListView:** Displays a vertically scrollable list of items.
- **ArrayAdapter:** Connects an array of data to a ListView.
- **`setAdapter()`:** Attaches the adapter to the ListView.
- **`setOnItemClickListener()`:** Handles clicks on individual list items.
- **`position`:** Indicates the index of the selected item.
- **Toast:** Displays a short message on the screen.
- **`android.R.layout.simple_list_item_1`:** Provides a built-in layout for displaying a single text item.

---

## 8. Result

Thus, an Android application using ListView and ArrayAdapter was developed successfully. The application displays a list of programming languages and implements item click handling to show the selected language through a Toast message.

