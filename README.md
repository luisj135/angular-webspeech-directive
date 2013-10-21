# HTML5 Web Speech AngularJS Directive
AngularJS is one of the hottest JavaScript frameworks on the internet providing a full stack for creating single page applications (SPAs).

Angular Directives are a way to teach HTML new tricks. During DOM compilation directives are matched against the HTML and executed. This allows directives to register behavior, or transform the DOM. 
 
The Web Speech API provides an alternative input method for web applications *(without using a keyboard)*. Developers can give web applications the ability to transcribe voice to text, from the computer's microphone. 

 
![image](https://dl.dropboxusercontent.com/u/26906414/cdn/img/ng-webspeech-banner.png)

## * Tutorial 
To quickly get started creating a custom component for AngularJS, install the [AngularJS Component Generator](https://github.com/mgcrea/generator-angular-component), execute the following command:

	$ sudo npm install -g generator-angular-component
	
Now you'll be able to scaffold a angular component project.


### Step 1 - Create the project
Proceed to create your project folder and then cd into that directory.

	$ mkdir angular-webspeech-directive && cd angular-webspeech-directive
	
Now use [Yeoman](http://yeoman.io/) to create your project files, execute the following command:

	$ yo angular-component
	
Then proceed to answer a few questions about your project.

	[?] Would you mind telling me your username on Github? jonniespratley
	[?] What's the base name of your project? angular-webspeech-directive
	[?] Under which lincense your project shall be released? MIT
	[?] Do you need the unstable branch of AngularJS? Yes
	[?] Does your module requires CSS styles? Yes


For distribution, register the new project with Bower (a web library package manager), execute the following command:

	$ bower register [name] [endpoint]

Now your component is available to the world via the `bower` package manager.




### Step 2 - Create the Directive
To create a directive with AngularJS it is best to create a module for your directive, then attach your directive definition to your module instance. 

This allows users of the component to easily include the required `scripts` and declare the component in the existing applications dependencies array.


#### 2.1 - Module Definition
To define the module, use the `angular.module()` method to create a module instance, in this case the variable `_app` is the components module.

	# Module instance
	_app = angular.module('jonniespratley.angularWebSpeechDirective', [])

The `angular.module` is a global method for creating, registering and retrieving Angular modules. 

1. When passed two or more arguments, a new module is created. 

		angular.module('jonniespratley.angularWebSpeechDirective', [])

2. If passed only one argument, an existing module (the name passed as the first argument to module) is retrieved.

		angular.module('jonniespratley.angularWebSpeechDirective')

All modules that should be available to an application must be registered using this method.

#### 2.2 - Factory Definition
To define a

	# Factory definition
	_app.service 'jsSpeechFactory', (['$rootScope', ($rootScope) -> 
		jsSpeechFactory = 
			icons :
				start: 'http://goo.gl/dBS39a'
				recording: 'http://goo.gl/7JLqdm'
				blocked: 'http://goo.gl/j8MZhD'
			messages :
				 info_speak_now: 'Speak for as long as you wish.'
					info_stop: 'Processing your voice...'
					info_no_speech: 'No Speech was detected. You may need to adjust your microphone settings.'
					info_no_mic: 'No microphone was found. Ensure that a microphone is installed and that'
					info_blocked: 'Permission to use microphone is blocked.'
					info_denied: 'Permission to use microphone was denied.'
					info_setup: 'Click on the microphone icon to enable Web Speech.'
					info_upgrade: 'Web Speech API is not supported. Upgrade to Chrome version 25 or later.'
					info_allow: 'Click the "Allow" button above to enable your microphone.'
			
	])
	


## * Usage 

Download the [production version][min] or the [development version][max].

[min]: https://raw.github.com/jonniespratley/jquery-angular-webspeech-directive/master/dist/angular-angular-webspeech-directive.min.js
[max]: https://raw.github.com/jonniespratley/jquery-angular-webspeech-directive/master/dist/angular-angular-webspeech-directive.js

In your web page:

	<script src="angular.js"></script>
	<script src="dist/angular-webspeech-directive.min.js"></script>

In your view:
	
	<js-speech ng-model="debug"></js-speech>




## * Documentation
For detailed information about the W3C Web Speech API visit the [website](https://dvcs.w3.org/hg/speech-api/raw-file/tip/speechapi.html).




## * Examples
For an example visit the [Plunkr](http://embed.plnkr.co/8xz2dUFKMZQIfFvSu0zA/preview).

![image](https://dl.dropboxusercontent.com/u/26906414/cdn/img/ng-webspeech-screenshot-1.png)