Design a ruby class, an object of which has the behaviour of accept the following hash and constructs an ruby object like following mapping

Atributes                   data from the input hash
====================        =============================
user_id                     user_id
message                     allert_message/allert_message + “batch_count” if silent is true/false
message_type                notification_type
pop_up                      silent
publish_at                  effective_date
target                      ‘gcm’/’apn’ if device is android/ios
device_ids                  tokens_from_the_ios_or_android_key



Sample data hash 1
=======================================
{
  "properties": {
    "user_id":43,
    "managing_user_id":43,
    "description":"Push Notification",
    "effective_date":"2015-07-20T06:28:36-05:00",
    "system_date":"2015-07-20T06:28:36-05:00"},
    "payload":{
      "id": 49,
      "options": {
        "devices": "ios => e25454608b6097bc412be42ad9bf39797a698925d947b9d136cbb992f649cc96",
        "Alert_message": " You have following notifications ",
        "badge_count":10,
        "created_at":"2015-07-20T06:28:36-05:00",
        "id":48,
        "member_id":25,
        "notification_type": "secure_message",
        "silent":true,
        "updated_at":"2015-07-20T06:28:36-05:00"
      }
    }
  }
}

Sample data hash 2
=======================================================
{
  "properties": {
    "user_id": 43,
    "managing_user_id": 43,
    "description": "Push Notification",
    "effective_date": "2015-07-21T06:28:36-05:00",
    "system_date": "2015-07-21T06:28:36-05:00"
  },
  "payload":
  {
    "id": 48,
    "options": {
      "devices": "android => e25454608b6097bc412be42ad9bf39797a698925d947b9d136cbb992f649cc96",
      "alert_message": "This is a sample push notification message",
      "badge_count": 0,
      "created_at": "2015-07-21T06:28:36-05:00",
      "id":48,
      "member_id": 25,
      "notification_type": "Reminder",
      "silent": false,
      "updated_at": "2015-07-21T06:28:36-05:00"
    }
  }
}

Sample out puts
=====================
payload 1:
  user_id: 49,
  message: "You have 10 notifications ",
  message_type: 'Reminder',
  pop_up: false,
  publish_at: '2015-07-21T06:28:36-05:00',
  target: 'ios',
  device_id: 'e25454608b6097bc412be42ad9bf39797a698925d947b9d136cbb992f649cc96'

payload 2:
  user_id: 48,
  message: "This is a sample push notification message",
  message_type: 'secure_message',
  pop_up: true,
  publish_at: '2015-07-21T06:28:36-05:00',
  target: 'gcm',
  device_id: 'e25454608b6097bc412be42ad9bf39797a698925d947b9d136cbb992f649cc96'
