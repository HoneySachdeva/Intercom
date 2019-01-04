# Intercom

Intercom : Customer Messaging Platform


Intercom allows software businesses to chat with prospective and existing customers within their app, on their website, through
social media, or via email. It is kind of customer care service. 

Steps to Integrate : 

1. Install pods in your project. Write below line in the podfile.

  # Pods for Intercom
  pod 'Intercom', '5.1.9'
  
2. Initialize Intercom

you need to get your Intercom app ID and Android API key. To find these, just select the 'Intercom for iOS' option in your app 
settings at
https://app.intercom.io/a/apps/iqsm455a/settings/ios

3. Import Intercom in Appdelegate class

import Intercom

4. Mention API keys and use keys in didFinishLaunchingWithOptions method in Appdelegate class. 

 static var INTERCOM_API_KEY:String = ""
 static var INTERCOM_APP_ID:String = ""
 
func application(_ application: UIApplication, didFinishLaunchingWithOptions 
launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool 
{
    // Override point for customization after application launch.

    Intercom.setApiKey(AppDelegate.INTERCOM_API_KEY, forAppId: AppDelegate.INTERCOM_APP_ID)
    Intercom.setLauncherVisible(false)

    return true
}
    
5. Write below methods in AppDelegate Class

func showIntercomLauncherButton(email : String)
{
    Intercom.registerUser(withEmail: email)
    Intercom.setLauncherVisible(true)
}

func hideIntercomLauncherButton()
{
    Intercom.setLauncherVisible(false)
}

func logoutIntercom()
{
    Intercom.logout()
}

6. Make Intercom button in View Controller Class in viewDidLoad

override func viewDidLoad() {
super.viewDidLoad()
// Do any additional setup after loading the view, typically from a nib.

kappdelegate.showIntercomLauncherButton(email: "abc@gmail.com")

}


7. To hide Intercom Button

kappdelegate.hideIntercomLauncherButton()

8. To Logout User

kappdelegate.logoutIntercom()
