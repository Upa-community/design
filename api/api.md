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
4.地点登録機能  
POST:[http://localhost:8000/api/spots_register/{usersId}](http://localhost:8000/api/spots_register/{usersId})
```
リクエスト
{
    "spots_name" : "京都駅八条口タクシー乗り場",
    "spots_address" : "京都府京都市下京区東塩小路釜殿町",
    "spots_url" : "https://www.youtube.com/watch?v=CO_ZjH6N7RE"
}
```
```
レスポンス
{
    "message": "Spot registration success!"
}
```
4.カメラ登録機能  
POST:[http://localhost:8000/api/cameras_register/{spotsId}](http://localhost:8000/api/cameras_register/{spotsId})
```
リクエスト
{
    "cameras_name" : "京都駅八条口タクシー乗り場-カメラA",
    "cameras_url" : "https://www.youtube.com/watch?v=CO_ZjH6N7RE"
}
```
```
レスポンス
{
    "message": "Camera registration success!"
}
```
5.情報取得  
GET:[http://localhost:8000/api/home_data/{userId}](http://localhost:8000/api/home_data/{usersId})
```
レスポンス
[
    {
        "id" : 1,
        "spots_name" : "京都駅八条口タクシー乗り場",
        "spots_address" : "京都府京都市下京区東塩小路釜殿町",
        "spots_latitude" : "None",
        "spots_longitude" : "None",
        "spots_url" : "Nhttps://www.youtube.com/watch?v=CO_ZjH6N7RE",
        "spots_status" : "None",
        "spots_count" : 15,
        "spots_day_count" : [15, 12, 0, 6, 15, 15, 4, 6, 9, 14, 3, 7, 0, 13, 1, 3, 14, 9, 5, 11, 5, 0, 5, 5],
        "spots_months_count" : [6, 4, 14, 13, 4, 12, 9, 5, 12, 12, 13, 6, 3, 8, 3, 10, 13, 13, 8, 0, 0, 3, 4, 6, 14, 9, 8, 12, 8, 4]
    },
        {
        "id" : 2,
        "spots_name" : "渋谷駅タクシー乗り場",
        "spots_address" : "渋谷駅",
        "spots_latitude" : "None",
        "spots_longitude" : "None",
        "spots_url" : "Nhttps://www.youtube.com/watch?v=CO_ZjH6N7RE",
        "spots_status" : "None",
        "spots_count" : 15,
        "spots_day_count" : [14, 14, 5, 8, 11, 13, 14, 10, 10, 7, 4, 10, 8, 10, 7, 10, 4, 15, 2, 11, 10, 4, 10, 7],
        "spots_months_count" : [8, 6, 3, 4, 13, 5, 2, 2, 8, 13, 0, 10, 4, 5, 2, 10, 10, 9, 6, 15, 4, 6, 0, 4, 8, 2, 15, 14, 5, 3]
    }
]
```
