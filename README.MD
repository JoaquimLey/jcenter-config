#jcenter-Configs


Painlessly publish your library/project to jcenter() with these simple scripts.

###Read more on the blog post: < WIP-Soon >

##How to use

- Copy the `deploy.properties` file to the **root** of your project, and change to your own settings (this is a _config_ file) [COPY HERE]()

- Add the following lines to your `.gitignore` to **prevent** exposing sensitive data to your repository

		# Local configuration file (sdk path, etc)
		deploy.properties

- On your **project** (root) `build.gradle` add the following lines:

		buildscript {
		    repositories {
		        jcenter()
		    }
		    dependencies {
		        classpath 'com.android.tools.build:gradle:2.2.2'
		        classpath 'com.github.dcendents:android-maven-gradle-plugin:1.4.1'
		    }
		}
		plugins {
		    id "com.jfrog.bintray" version "1.7"
		}
		allprojects {
		    repositories {
		        jcenter()
		    }
		}


- On your **library module** (you wish to publish) `build.gradle` add the following lines **before** the `android{}` closure:

		apply plugin: 'com.android.library'
		apply plugin: 'com.github.dcendents.android-maven'
		apply plugin: 'com.jfrog.bintray'
		
		android {
		    compileSdkVersion 25
		    buildToolsVersion "25.0.0"
		    ...
		}

- Still in the same library module `gradle.build` add **at the end** of your file.




## Contributing

**Issues:**
Fell free and it's encoraged to open a new issues follow the [ISSUE_TEMPLATE.MD](../development/ISSUE_TEMPLATE.MD)

Contributions are always welcome!
Follow the "fork-and-pull" Git workflow.

 1. **Fork** the repo on GitHub
 2. **Clone** the project to your own machine
 3. **Commit** changes to your own branch
 4. **Merge** with current *development* branch
 5. **Push** your work back up to your fork
 7. Submit a **Pull request** your changes can be reviewed (please refere the issue if reported)

**Prevent** code-style related changes (at least run Ctrl+⌥+O, ⌥+⌘+L) before commiting.

##Questions

I'm writing a blog post about this process, incldugin a step-by-step guide. In the meantimefor some reason still unable to publish you can or if you have any questions or always find me on [twitter](https://twitter.com/JoaquimLey).


### License

	Copyright © 2016 Joaquim Ley

	Licensed under the Apache License, Version 2.0 (the "License");
	you may not use this file except in compliance with the License.
	You may obtain a copy of the License at

	http://www.apache.org/licenses/LICENSE-2.0

	Unless required by applicable law or agreed to in writing, software
	distributed under the License is distributed on an "AS IS" BASIS,
	WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or 
	implied.
	See the License for the specific language governing permissions and
	limitations under the License.
