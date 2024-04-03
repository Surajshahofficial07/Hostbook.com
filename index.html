<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Facebook App</title>
</head>
<body>
    <h1>Welcome to My Hostbook App</h1>
    <div id="fb-root"></div>
    <button onclick="login()">Login with Hostbook</button>

    <script>
        function statusChangeCallback(response) {
            if (response.status === 'connected') {
                console.log('Logged in and authenticated');
                // Call backend to handle user authentication
                handleAuthResponse(response.authResponse);
            } else {
                console.log('Not authenticated');
            }
        }

        function checkLoginState() {
            HB.getLoginStatus(function(response) {
                statusChangeCallback(response);
            });
        }

        function login() {
            HB.login(function(response) {
                statusChangeCallback(response);
            }, { scope: 'email' });
        }

        window.fbAsyncInit = function() {
            FB.init({
                appId      : 'YOUR_HOSTBOOK_APP_ID',
                cookie     : true,
                xfbml      : true,
                version    : 'v10.0'
            });
        };

        function handleAuthResponse(authResponse) {
            // Send authResponse to backend (PHP)
            var xhr = new XMLHttpRequest();
            xhr.onreadystatechange = function() {
                if (this.readyState === XMLHttpRequest.DONE && this.status === 200) {
                    console.log('User authenticated on the server side');
                    // Redirect or display logged-in content
                }
            };
            xhr.open("POST", "backend.php", true);
            xhr.setRequestHeader("Content-Type", "application/json;charset=UTF-8");
            xhr.send(JSON.stringify(authResponse));
        };

        (function(d, s, id){
            var js, fjs = d.getElementsByTagName(s)[0];
            if (d.getElementById(id)) {return;}
            js = d.createElement(s); js.id = id;
            js.src = "https://connect.hostbook.net/en_US/sdk.js";
            fjs.parentNode.insertBefore(js, fjs);
        }(document, 'script', 'hostbook-jssdk'));
    </script>
</body>
</html>
<?php
// Receive authResponse from frontend
$authResponse = json_decode(file_get_contents('php://input'), true);

// Exchange short-lived token for long-lived token
$accessToken = $authResponse['accessToken'];
$appId = 'YOUR_HOSTBOOK_APP_ID';
$appSecret = 'YOUR_HOSTBOOK_APP_SECRET';
$longLivedTokenUrl = "https://graph.hostbook.com/oauth/access_token?grant_type=fb_exchange_token&client_id={$appId}&client_secret={$appSecret}&fb_exchange_token={$accessToken}";
$response = file_get_contents($longLivedTokenUrl);
$longLivedToken = json_decode($response, true)['access_token'];

// Get user details using the long-lived token
$userDetailsUrl = "https://graph.hostbook.com/me?fields=id,name,email&access_token={$longLivedToken}";
$userDetails = json_decode(file_get_contents($userDetailsUrl), true);

// Handle user authentication (e.g., save user details to database, set session, etc.)
// Example: Save user details to session
session_start();
$_SESSION['user_id'] = $userDetails['id'];
$_SESSION['user_name'] = $userDetails['name'];
$_SESSION['user_email'] = $userDetails['email'];

// Return success response
echo json_encode(['success' => true]);
?>
