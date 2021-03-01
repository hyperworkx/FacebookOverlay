# facebookOverlay
BeTheDev.com (be the Developer) 

Facebook profile overlay app. It downloads current user's profile picture and paste an overlay image on it and presents an option to post to Facebook. Here i have used Facebook SDK v5 PHP for authentication and upload.
For complete guide visit --> http://www.bethedev.com/

Installation

Please modify facebook_start.php to add "app_id" "app_secret" the following lines in them:

$fb = new Facebook\Facebook(array(
    'app_id'                => 'YOUR_APP_ID',
    'app_secret'            => 'YOUR_APP_SECRET',
    'default_graph_version' => 'v2.3',
 'persistent_data_handler'=>'session',
    ));


Visit Facebook developers, Create a developer account and create new app. Facebook dashboard provides you App_Id and App_Secret.

Install Curl on Server


sudo apt-get install curl

Facebook Developer Dashboard Setup

After successful creation of new app.

1. Into the app Setting -> Basic.  fill 'Display Name', 'Namespace', 'App Domains' accordingly your app.

2. Click to Add Platform -> Website. Fill Site URL <<Place your APP URL>>

3. Facebook Login -> Setup 'Valid OAuth redirect URIs' , 'Deauthorize Callback URL' accordingly your app

Note :- You should apply for App review to publish app on public.


Call Back URL Setup

Please modify index.php to add 'callback_url' the following lines in them:

require( __DIR__.'/facebook_start.php' );
  $helper = $fb-&gt;getRedirectLoginHelper();
  $permissions = ['email', 'user_posts','publish_actions']; // optional
  $callback_url    = 'https://www.YOUR_DOMAIN.com/login.php';
  $loginUrl    = $helper-&gt;getLoginUrl($callback_url, $permissions);
  $bg_path = 'IMG_PATH';

https://www.bethedev.com/2016/11/create-facebook-profile-picture-overlay.html
https://developers.facebook.com/products/frame-studio/
