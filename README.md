# facebook-messenger-mostly-used-curl
Mostly used curl command while building a bot on facebook messenger platform
#### To add persistent menu
```
curl -X POST -H "Content-Type: application/json" -d '{
  "setting_type" : "call_to_actions",
  "thread_state" : "existing_thread",
  "call_to_actions":[
    {
      "type":"postback",
      "title":"Super Bowl 2017",
      "payload":"#super bowl"
    },
    {
      "type":"postback",
      "title":"Trump news",
      "payload":"#trump"
    }
 ]
}' "https://graph.facebook.com/v2.6/me/thread_settings?access_token={access_token}"    
```
#### To add greeting
```
curl -X POST -H "Content-Type: application/json" -d '{
  "setting_type":"greeting",
  "greeting":{
    "text":"Hey {{user_first_name}}, myNews at your service! I can dig up the news of your interests. Type 'GO' to get started!"
  }
}' "https://graph.facebook.com/v2.6/me/thread_settings?access_token={access_token}"
```
#### To add "get started" to initiate the thread
```
curl -X POST -H "Content-Type: application/json" -d '{
  "setting_type":"call_to_actions",
  "thread_state":"new_thread",
  "call_to_actions":[
    {
      "payload":"get_started"
    }
  ]
}' "https://graph.facebook.com/v2.6/me/thread_settings?access_token={access_token}"
```
