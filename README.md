# :alarm_clock: Dialoger
A simple library to help developers create beautiful alert dialogs

# :camera: Preview
![preview image](https://github.com/Ido-Barnea/Dialoger/blob/master/images/loading%20dialog.png)
![preview image](https://github.com/Ido-Barnea/Dialoger/blob/master/images/message%20dialog.png)

# :question: How can I add this to my project?
> Step 1: Add the JitPack repository to your build file
  ```gradle
  allprojects {
		repositories {
			maven { url 'https://jitpack.io' }
		}
	}
  ```
> Step 2: Add the dependency
  ```gradle
  dependencies {
	        implementation 'com.github.Ido-Barnea:Dialoger:1.1.3'
	}
  ```
  That's it!

# :fast_forward: Quick use
  ```kotlin
	val dialog = Dialoger(this, Dialoger.TYPE_LOADING)
		.setTitle("This is a loading dialog...")
		.setDescription("This might take a while...")
		.setProgressBarColor(R.color.purple_200)
		.show()

	// dismiss the dialog after 3 seconds
	Handler().postDelayed({
		dialog.dismiss()

		Dialoger(this, Dialoger.TYPE_MESSAGE)
			.setDialogColorTheme(R.color.green)
			.setTitle("New Dialog!")
			.setDescription("This was an amazing success!")
			.setButtonText("ALLONS-Y!")
			.setButtonOnClickListener {
				Toast.makeText(this, "dialog button clicked", Toast.LENGTH_SHORT).show()
			}
			.show()
	}, 3000)
  ```

# :book: Dialog Types:
- Message
- Loading

# :computer: What can I edit in each dialog?
- Title & description text
- Title & description text color
- Image drawable
- Button text ```(Not visible in loading dialog)```
- Button color ```(Not visible in loading dialog)```
- Progress bar color ```(Only visible in loading dialog)```
- Progress bar indeterminate drawable ```(Only visible in loading dialog)```
- Dialog background color
- Whether the dialog will be dismissed on touch outside of it or not

# :briefcase: License
```
Copyright 2022 Ido Barnea

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
