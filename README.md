# \[ 🚧 Work in progress 👷‍♀️⛏👷🔧️👷🔧 🚧 \] Plaid 2.0 

Rewriting Plaid using [Android Architecture Components](https://developer.android.com/topic/libraries/architecture/), in Kotlin. 

👀 "[Up for grabs](https://github.com/nickbutcher/plaid/issues?q=is%3Aissue+is%3Aopen+label%3A%22Up+for+grabs+%F0%9F%A4%9A%22)" issues – We're happy to [get your contributions](https://github.com/nickbutcher/plaid/blob/master/CONTRIBUTING.md#contributing-a-patch) on those!

👍 Comments and new issues created are welcomed.

🛑 We're currently not accepting external PRs that touch on the app's architecture.

[![CircleCI](https://circleci.com/gh/android/plaid/tree/master.svg?style=shield)](https://circleci.com/gh/android/plaid/tree/master)

## The project is stuck, All api seems dead so not any content is loaded
Notes: Just wait until Plaid 2.0 is arrived so you are not wasting any time config this legacy code. Don't be like me

Config Build
- Android Studio Ladybug (2024)
- Android Gradle Version (8.1)
- Gradle Version (8.1)
- JVM Target and Compile Java 17

For those of you who wants to build this from the owner's repo
Just upgrade the `spotless` version to the latest (it will change the name of the plugin and the dependencies), remove the plugin `kotlin-android-extension` (deprecated) parts from build gradle for each `module` and adding `kotlin-parcelize` in some module (you will know will one will require some Parcelize). And lastly try to update the AGP and Gradle using AGP Upgrade Assistance to the 8.1, because this is the sweet spot as I'm certain.

At the end, just don't fork and try to build the plaid project, just wait until the 2.0 is done. So you don't have to suffer just like me


### Background

Plaid was written with one big goal: showcase material design in Android in a real application. While Plaid successfully achieved its goal, from an architecture point of view, it lacks all features that would make it a modular, scalable, testable and maintainable app: with UI logic in Android classes, no tests and only one module. 
Plaid represents a great real world app example: it provides a fairly complex set of functionalities, it has technical debt, it has features that have to be dealt with as APIs are being removed.
All of these problems are encountered by many projects in the Android community and therefore, make Plaid a suitable showcase for all the advantages that architecture components bring. 

#### More information

* Read more:

	* [Restitching Plaid - Updating Plaid to modern app standards](https://medium.com/@crafty/restitching-plaid-9ca5588d3b0a)
	* [A patchwork Plaid - Monolith to modularized app](https://medium.com/androiddevelopers/a-patchwork-plaid-monolith-to-modularized-app-60235d9f212e)
	* [Cross-stitching Plaid and AndroidX](https://medium.com/androiddevelopers/cross-stitching-plaid-and-androidx-7603a192348e)
	* [Dependency injection in a multi module project](https://medium.com/androiddevelopers/dependency-injection-in-a-multi-module-project-1a09511c14b7)

* Video Presentations:

	* [Shaping Your App's Architecture with Kotlin and Architecture Components by Florina](https://youtu.be/Sy6ZdgqrQp0) (Florina Muntenescu at KotlinConf 2018)
	* [Re-stitching Plaid with Kotlin](https://youtu.be/NNWejxBORgc) (Florina Muntenescu at Android Dev Summit '18)

### Goals
* Migrate Plaid to Architecture Components. The refactoring will follow the architecture described in [Guide to App Architecture](https://developer.android.com/jetpack/docs/guide).  
* Convert to Kotlin, while migrating to Architecture Components.
* Modularize the app using [dynamic feature modules](https://developer.android.com/guide/app-bundle/).
* Showcase the extensibility of the architecture by adding an extra data source, once the migration is finished.

### Non-Goals
Changes to the styles, themes, icons, animations, transitions or any other UI elements that were the initial focus of Plaid, are outside the scope of this refactoring. 

### Android Studio IDE setup

Plaid requires Android Studio version 3.6 or higher.

Plaid uses [ktlint](https://ktlint.github.io/) to enforce Kotlin coding styles.
Here's how to configure it for use with Android Studio (instructions adapted
from the ktlint [README](https://github.com/shyiko/ktlint/blob/master/README.md)):

- Close Android Studio if it's open
- Download ktlint using these [installation instructions](https://github.com/shyiko/ktlint/blob/master/README.md#installation)

- Inside the project root directory run:

  `./ktlint --apply-to-idea-project --android`

- Remove ktlint if desired:

  `rm ktlint`

- Start Android Studio

---

# Plaid 1.0

<img src="screenshots/plaid_demo.gif" width="300" align="right" hspace="20">

*Design news and inspiration.*

Plaid is a showcase of [material design](https://www.google.com/design/spec/) that we hope you will
keep installed. It pulls in news & inspiration from [Designer News](https://www.designernews.co/),
[Dribbble](https://dribbble.com/) & [Product Hunt](https://www.producthunt.com/). It demonstrates
the use of
[material principles](https://www.google.com/design/spec/material-design/introduction.html#introduction-principles)
to create tactile, bold, understandable UIs.

**[Install on Google Play (Beta Testing)](https://play.google.com/apps/testing/io.plaidapp)**


### Screenshots


<img src="screenshots/home_grid_framed.png" width="25%" />
<img src="screenshots/post_story_framed.png" width="25%" />
<img src="screenshots/dn_story_framed.png" width="25%" />
<img src="screenshots/dribbble_shot_framed.png" width="25%" />


##### Non-Goals
Plaid is a UI sample and seeks to demonstrate how to implement material design. To make this as clear as possible it explicitly does not attempt to:
* Provide opinionated **architecture/testing** advice; it utilizes vanilla Android components. For advice on this, I'd recommend [Blueprints](https://github.com/googlesamples/android-architecture).
* Support **pre-Lollipop** devices. Doing so is entirely possible, but complicates things. For advice on doing this, see [this fork](https://github.com/hzsweers/plaid/tree/z/moarbackport).


### License


```
Copyright 2015 Google LLC.

Licensed to the Apache Software Foundation (ASF) under one or more contributor
license agreements. See the NOTICE file distributed with this work for
additional information regarding copyright ownership. The ASF licenses this
file to you under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License. You may obtain a copy of
the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
License for the specific language governing permissions and limitations under
the License.
```
