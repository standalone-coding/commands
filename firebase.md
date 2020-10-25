curl -X POST \
  https://fcm.googleapis.com/fcm/send \
  -H 'Authorization: key=<KEY>' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: c8af5355-dbf2-4762-9b37-a6b89484cf07' \
  -H 'cache-control: no-cache' \
  -d '{
    "to": "<ID>",
    "data":{
        "body":"Test Notification !!!",
        "title":"Test Title !!!"
    }

}'