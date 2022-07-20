# <h1 align = "center"> **FastLane**
<p align = "center"> <img src="https://docs.fastlane.tools/img/fastlane_text.png">
</p>

You can distribute builds to testers using fastlane, an open source platform that automates building and releasing iOS and Android apps. It follows simple instructions defined in a Fastfile. After you set up fastlane and your Fastfile, you can integrate App Distribution with your fastlane configuration.



Step 1. Set up fastlane
Install and set up fastlane.

To add App Distribution to your fastlane configuration, run the following command from the root of your iOS project:

fastlane add_plugin firebase_app_distribution



Step 2. Authenticate with Firebase
Before you can use the Fastlane plugin, you must first authenticate with your Firebase project. 


Step 3. Set up your Fastfile and distribute your app
In a ./fastlane/Fastfile lane, add a firebase_app_distribution block. 


Finally, to make the build available to testers, run your lane:

Once you distribute your build, it becomes available in the App Distribution dashboard of the Firebase console for 150 days (five months). When the build is 30 days from expiring, an expiration notice appears in both the console and your tester's list of builds on their test device.

Testers who haven't been invited to test the app receive email invitations to get started, and existing testers receive email notifications that a new build is ready to test (read the tester set up guide for instructions on how to install the test app). You can monitor the status of each tester-whether they accepted the invitation and whether they downloaded the app-in the Firebase console.

Testers have 30 days to accept an invitation to test the app before it expires. When an invitation is 5 days from expiring, an expiration notice appears in the Firebase console next to the tester on a release. An invitation can be renewed by resending it using the drop-down menu on the tester row.

Step 4 (Optional). Managing testers for the distribution
You can add or remove testers from your app release by using your Fastfile file or by directly running fastlane actions. Running actions directly will override the values set in your Fastfile.

Once a tester has been added to your Firebase project, you can add them to individual releases. Testers who are removed will no longer have access to releases in your project, but may still retain access to your releases for a window of time.