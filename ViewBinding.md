# View Binding
## What is view binding?
View binding, is a feature that makes views easier to access. With this it is not necessary to define for each view, all views can be accessed with a keyword.

## How to include in a project?
1. Open **Gradle Scripts > build.gradle (Module: HelloWorld.app)** and add **buildFeatures** block in **android** scope.
``` gradle
android {
  ...
  buildFeatures {
    viewBinding true
  }
}
```

2. Click **Sync Now** and wait until it finishes.
<p align="center">
  <img src="https://user-images.githubusercontent.com/67027784/196947941-a3e6e471-112d-415a-903b-4ecb9f24a649.png" alt="build.gradle">
</p>

3. Go to **MainActivity.java** and import the related modules.
``` java
import android.view.View;
import com.example.helloworld.databinding.ActivityMainBinding;
``` 

4. Add a new field named **binding** to the **MainActivity** class.
``` java
public class MainActivity extends AppCombatActivity {
  private ActivityMainBinding binding;
  ...
```

5. Delete **setContentView** line and write these 3 lines in **onCreate** method.

<p>Before:</p>

``` java
@Override
protected void onCreate(Bundle savedInstanceState) {
  super.onCreate(savedInstanceState);
  setContentView(R.layout.activity_main);
  ...

``` 

<p>After:</p>

``` java
@Override
protected void onCreate(Bundle savedInstanceState) {
  super.onCreate(savedInstanceState);
  /* 1 */ binding = ActivityMainBinding.inflate(getLayoutInflater());
  /* 2 */ View view = binding.getRoot();
  /* 3 */ setContentView(view);
  ...
``` 

## How to use?
All views can be accessed by **binding** keyword. (It should be applied from step 3 for each avtivity to be used)

<p align="center">
  <img src="https://user-images.githubusercontent.com/67027784/196961878-f29fc7fd-2b30-4ab4-8881-a93d3f449aa5.png" alt="Binding Usage">
</p>