## APIの仕様  
1.ユーザー登録  
POST:[http://localhost:8000/api/register](http://localhost:8000/api/register)
```
リクエスト
{
    "name" : "testuser",
    "email" : "testuser@gmail.com",
    "password" : "testuser"
}
```
```
レスポンス
{
    "data": {
        "name": "testuser",
        "email": "testuser@gmail.com",
        "updated_at": "2023-03-05T13:42:04.000000Z",
        "created_at": "2023-03-05T13:42:04.000000Z",
        "id": 1
    },
    "message": "User registration success!",
    "error": ""
}
```
2.ログイン  
POST:[http://localhost:8000/api/login](http://localhost:8000/api/login)
```
リクエスト
{
    "email" : "testuser@gmail.com",
    "password" : "testuser"
}
```
```
レスポンス
{
    "token": "4|Gnh3XCCIQuKI0FxixMsKfh21RrH0J0QhYUtCWkIE",
    "user": {
        "id": 1,
        "name": "testuser",
        "email": "testuser@gmail.com",
        "email_verified_at": null,
        "created_at": "2023-03-05T13:40:57.000000Z",
        "updated_at": "2023-03-05T13:40:57.000000Z"
    }
}
```
2.地点登録機能  
POST:[http://localhost:8000/api/spots_register/{usersId}](http://localhost:8000/api/spots_register/{usersId})
```
リクエスト
{
    "spots_name" : "京都駅八条口タクシー乗り場",
    "spots_address" : "京都府京都市下京区東塩小路釜殿町",
    "spots_url" : "https://www.youtube.com/watch?v=CO_ZjH6N7RE",
}
```
```
レスポンス
{
    "message": "Spot registration success!"
}
```
3.カメラ登録機能  
POST:[http://localhost:8000/api/cameras_register/{spotsId}](http://localhost:8000/api/cameras_register/{spotsId})
```
リクエスト
{
    "cameras_name" : "京都駅八条口タクシー乗り場-カメラA",
    "cameras_url" : "https://www.youtube.com/watch?v=CO_ZjH6N7RE",
}
```
```
レスポンス
{
    "message": "Camera registration success!"
}
```
