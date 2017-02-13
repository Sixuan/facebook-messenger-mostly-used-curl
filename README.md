# facebook-messenger-mostly-used-curl
Mostly used curl command while building a bot on facebook messenger platform

1. To add persistent menu
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
