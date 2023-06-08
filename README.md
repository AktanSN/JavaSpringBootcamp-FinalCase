
# JavaSpringBootcamp-FinalCase

## Gereklilikler
````
Proje Konusu:
Bir hava durumu uygulaması yazmak istenmektedir. Bu uygulama RESTful bir web servisi kullanarak hava durumu tahminleri sağlayacaktır. Kullanıcılara, bir şehirdeki hava durumu tahminlerini sorgulama imkanı sunulacaktır. Tahminler, 5 günlük süreyi kapsayan 3 saatlik aralıklarla sağlanacaktır. Uygulama, OpenWeatherMap API'sini kullanarak hava durumu tahminleri alacaktır.
Backend 
Restful web servisi: Şehir ve diğer parametreleri alıp hava durumu tahmini sağlayacak.
Veritabanı: Kullanıcıların aradığı şehirleri ve tahminleri kaydedebilmek için bir veritabanı sistemi kullanılacak.
Günlük tahminler: Hava durumu tahminleri, 5 günlük süreyi kapsayan 3 saatlik aralıklarla sağlanacak.
Kullanıcı kaydı: Kullanıcılar, bir hesap oluşturarak şehirlerini kaydedebilir ve kaydedilen şehirler için hava durumu tahminlerini görüntüleyebilir.
API kullanımı: OpenWeatherMap API'si, hava durumu tahminleri sağlamak için kullanılacak.
Testler: Kod kalitesini ve performansı sağlamak için otomatik testler yazılacak.
Dokümantasyon: Swagger veya OpenApi gibi araçlar kullanılarak RESTful servisin dokümantasyonu sağlanacak.
Günlükler: Uygulamanın hata ayıklanmasına yardımcı olmak için loglama mekanizması kurulacak.
Frontend (opsiyonel): 
Kullanıcı arayüzü: Kullanıcılara şehir arama ve hava durumu tahmini gösterimi sağlanacak.
Arayüz tasarımı: JavaScript, HTML, CSS gibi teknolojiler kullanılarak basit bir arayüz tasarlanacak. 
Bootstrap veya ReactJS gibi frameworkler kullanılabilir.
Projeden Beklenenler:
Backend projesinin belirtilen kurallara göre doğru çalışır olması.
Kodun kalitesine (Clean Code), yapılandırılmasına (structure) dikkat edilmesi, yeni özellikler için geliştirmeye açık olması ve anlaşılabilir olması. (SOLID principles)
Test yazılması.
Dokümantasyon(Swagger, OpenApi vb).
Loglama mekanizmasının kurulması.
Frontend projesinin çalışır olması.
````

## Kullanılan Teknolojiler

Front-End: 
* ReactJs
* Redux
* Axios

Back-End:
* Maven
* Spring Boot
* Spring Data JPA
* Spring Security
* Lombok
* MapStruct
* Docker
* Kafka
* Swagger
* OpenFeign 
* H2 Database

## Uygulama İçi Görseller

![Photo](https://user-images.githubusercontent.com/58556840/244498162-5f632d61-edd1-45cb-8e77-a345bd5e3fe0.png)
![Photo](https://user-images.githubusercontent.com/58556840/244498152-50addbe1-1a1c-4ee9-9deb-d1e878e33e5c.png)
![Photo](https://user-images.githubusercontent.com/58556840/244498156-886377ad-8222-4244-bd09-d85047adb7e0.png)
![Photo](https://user-images.githubusercontent.com/58556840/244498159-6a85e249-28f5-43a7-8502-a33fad007877.png)
![Photo](https://user-images.githubusercontent.com/58556840/244498166-17cfcb25-ed6a-4715-bc7a-66ac89888457.png)
![Photo](https://user-images.githubusercontent.com/58556840/244498148-cb002a7d-76ef-4cb5-b95d-ab3b2ac805aa.png)

# API Tanımlamaları


## User
1. Post User

```text
POST : http://localhost:8080/api/1.0/users
```

```json

Request:
{
  "username": "aktansn",
  "password": "password123"
}
```

```json
{
Response:
  "message": "Kayıt Başarılı",
  "data": {
    "id": 1,
    "username": "aktansn",
    "cities": null,
    "baseAdditionalFields": {
      "createdDate": "2023-06-08T22:29:21.4297492",
      "updatedDate": "2023-06-08T22:29:21.4297492",
      "createdBy": "aktansn",
      "updatedBy": "aktansn"
    }
  },
  "success": true
}
```

2. Get All Users
  
```text
GET : http://localhost:8080/api/1.0/users
```

```json
{
  "message": "Listelendi",
  "data": [
    {
      "id": 1,
      "username": "aktansn",
      "cities": [
        {
          "id": 1,
          "cityName": "Ankara",
          "temp": "20",
          "infoDate": "8-6-2023 22:32",
          "icon": "01n",
          "baseAdditionalFields": {
            "createdDate": "2023-06-08T22:32:17.951295",
            "updatedDate": "2023-06-08T22:32:17.951295",
            "createdBy": "aktansn",
            "updatedBy": "aktansn"
          }
        }
      ],
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:29:21.429749",
        "updatedDate": "2023-06-08T22:29:21.429749",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    }
  ],
  "success": true
}
```

3. Get User By Id
  
```text
GET : http://localhost:8080/api/1.0/users/1
```

```json
{
  "message": "Listelendi",
  "data": {
    "id": 1,
    "username": "aktansn",
    "cities": [
      {
        "id": 1,
        "cityName": "Ankara",
        "temp": "20",
        "infoDate": "8-6-2023 22:32",
        "icon": "01n",
        "baseAdditionalFields": {
          "createdDate": "2023-06-08T22:32:17.951295",
          "updatedDate": "2023-06-08T22:32:17.951295",
          "createdBy": "aktansn",
          "updatedBy": "aktansn"
        }
      }
    ],
    "baseAdditionalFields": {
      "createdDate": "2023-06-08T22:29:21.429749",
      "updatedDate": "2023-06-08T22:29:21.429749",
      "createdBy": "aktansn",
      "updatedBy": "aktansn"
    }
  },
  "success": true
}
```

4. Get Users Starts With
  
```text
GET : http://localhost:8080/api/1.0/users/search/startswith?username=a
```

```json
{
  "message": "Listelendi",
  "data": [
    {
      "id": 1,
      "username": "aktansn",
      "cities": [
        {
          "id": 1,
          "cityName": "Ankara",
          "temp": "20",
          "infoDate": "8-6-2023 22:32",
          "icon": "01n",
          "baseAdditionalFields": {
            "createdDate": "2023-06-08T22:32:17.951295",
            "updatedDate": "2023-06-08T22:32:17.951295",
            "createdBy": "aktansn",
            "updatedBy": "aktansn"
          }
        }
      ],
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:29:21.429749",
        "updatedDate": "2023-06-08T22:29:21.429749",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    }
  ],
  "success": true
}
```
5. Get Users Contains
  
```text
GET : http://localhost:8080/api/1.0/users/search/contains?username=s
```

```json
{
  "message": "Listelendi",
  "data": [
    {
      "id": 1,
      "username": "aktansn",
      "cities": [
        {
          "id": 1,
          "cityName": "Ankara",
          "temp": "20",
          "infoDate": "8-6-2023 22:32",
          "icon": "01n",
          "baseAdditionalFields": {
            "createdDate": "2023-06-08T22:32:17.951295",
            "updatedDate": "2023-06-08T22:32:17.951295",
            "createdBy": "aktansn",
            "updatedBy": "aktansn"
          }
        }
      ],
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:29:21.429749",
        "updatedDate": "2023-06-08T22:29:21.429749",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    }
  ],
  "success": true
}
```
6. Get Users By Page
  
```text
GET : http://localhost:8080/api/1.0/users/page?pageNumber=1&pageSize=1
```

```json
{
  "message": "Listelendi",
  "data": [
    {
      "id": 1,
      "username": "aktansn",
      "cities": [
        {
          "id": 1,
          "cityName": "Ankara",
          "temp": "20",
          "infoDate": "8-6-2023 22:32",
          "icon": "01n",
          "baseAdditionalFields": {
            "createdDate": "2023-06-08T22:32:17.951295",
            "updatedDate": "2023-06-08T22:32:17.951295",
            "createdBy": "aktansn",
            "updatedBy": "aktansn"
          }
        }
      ],
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:29:21.429749",
        "updatedDate": "2023-06-08T22:29:21.429749",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    }
  ],
  "success": true
}
```

7. Get Users Order By
  
```text
GET : http://localhost:8080/api/1.0/users/orderbyname
```

```json
{
  "message": "Listelendi",
  "data": [
    {
      "id": 1,
      "username": "aktansn",
      "cities": [
        {
          "id": 1,
          "cityName": "Ankara",
          "temp": "20",
          "infoDate": "8-6-2023 22:32",
          "icon": "01n",
          "baseAdditionalFields": {
            "createdDate": "2023-06-08T22:32:17.951295",
            "updatedDate": "2023-06-08T22:32:17.951295",
            "createdBy": "aktansn",
            "updatedBy": "aktansn"
          }
        }
      ],
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:29:21.429749",
        "updatedDate": "2023-06-08T22:29:21.429749",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    }
  ],
  "success": true
}
```
8. Update User By Id
  
```text
PUT : http://localhost:8080/api/1.0/users/1
```

```json
Request:
{
  "username": "ahmet123",
  "password": "password1234"
}
```
```json
Response:
{
  "message": "Güncellendi",
  "data": {
    "id": 1,
    "username": "ahmet123",
    "cities": [
      {
        "id": 1,
        "cityName": "Ankara",
        "temp": "21",
        "infoDate": "8-6-2023 23:4",
        "icon": "04n",
        "baseAdditionalFields": {
          "createdDate": "2023-06-08T23:04:30.233433",
          "updatedDate": "2023-06-08T23:04:30.233433",
          "createdBy": "aktansn",
          "updatedBy": "aktansn"
        }
      }
    ],
    "baseAdditionalFields": {
      "createdDate": "2023-06-08T23:03:36.714933",
      "updatedDate": "2023-06-08T23:05:28.1289878",
      "createdBy": "aktansn",
      "updatedBy": "ahmet123"
    }
  },
  "success": true
}
```
9. Delete User By Id
  
```text
DELETE : http://localhost:8080/api/1.0/users/1
```

```json
{
  "message": "Silindi",
  "success": true
}
```

## City

1. Post City With User Id
  
```text
POST : http://localhost:8080/api/1.0/cities
```
  
```json
Request:
{
  "cityName": "Berlin",
  "userId": 2,
  "temp": "25",
  "infoDate": "8-6-2023 22:47",
  "icon": "01n"
}
```

```json
Response:
{
  "message": "Kayıt Başarılı",
  "data": {
    "id": 3,
    "cityName": "Berlin",
    "temp": "25",
    "infoDate": "8-6-2023 22:47",
    "icon": "01n",
    "baseAdditionalFields": {
      "createdDate": "2023-06-08T22:48:26.157918",
      "updatedDate": "2023-06-08T22:48:26.157918",
      "createdBy": "aktansn",
      "updatedBy": "aktansn"
    }
  },
  "success": true
}
```
2. Get All Cities
  
```text
GET : http://localhost:8080/api/1.0/cities
```

```json
{
  "message": "Listelendi",
  "data": [
    {
      "id": 2,
      "cityName": "Ankara",
      "temp": "20",
      "infoDate": "8-6-2023 22:47",
      "icon": "01n",
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:47:46.553766",
        "updatedDate": "2023-06-08T22:47:46.553766",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    },
    {
      "id": 3,
      "cityName": "Berlin",
      "temp": "25",
      "infoDate": "8-6-2023 22:47",
      "icon": "01n",
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:48:26.157918",
        "updatedDate": "2023-06-08T22:48:26.157918",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    }
  ],
  "success": true
}
```
3. Get Cities By Id
  
```text
GET : http://localhost:8080/api/1.0/cities/2
```

```json
{
  "message": "Listelendi",
  "data": {
    "id": 2,
    "cityName": "Ankara",
    "temp": "20",
    "infoDate": "8-6-2023 22:47",
    "icon": "01n",
    "baseAdditionalFields": {
      "createdDate": "2023-06-08T22:47:46.553766",
      "updatedDate": "2023-06-08T22:47:46.553766",
      "createdBy": "aktansn",
      "updatedBy": "aktansn"
    }
  },
  "success": true
}
```
4. Get Cities By User Id
  
```text
GET : http://localhost:8080/api/1.0/cities/user/2
```

```json
{
  "message": "Listelendi",
  "data": [
    {
      "id": 2,
      "cityName": "Ankara",
      "temp": "20",
      "infoDate": "8-6-2023 22:47",
      "icon": "01n",
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:47:46.553766",
        "updatedDate": "2023-06-08T22:47:46.553766",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    },
    {
      "id": 3,
      "cityName": "Berlin",
      "temp": "25",
      "infoDate": "8-6-2023 22:47",
      "icon": "01n",
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:48:26.157918",
        "updatedDate": "2023-06-08T22:48:26.157918",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    }
  ],
  "success": true
}
```
5. Get Cities Starts With
  
```text
GET : http://localhost:8080/api/1.0/cities/search/startswith?cityName=A
```

```json
{
  "message": "Listelendi",
  "data": [
    {
      "id": 2,
      "cityName": "Ankara",
      "temp": "20",
      "infoDate": "8-6-2023 22:47",
      "icon": "01n",
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:47:46.553766",
        "updatedDate": "2023-06-08T22:47:46.553766",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    }
  ],
  "success": true
}
```
6. Get Cities Contains 
  
```text
GET : http://localhost:8080/api/1.0/cities/search/contains?cityName=k
```

```json
{
  "message": "Listelendi",
  "data": [
    {
      "id": 2,
      "cityName": "Ankara",
      "temp": "20",
      "infoDate": "8-6-2023 22:47",
      "icon": "01n",
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:47:46.553766",
        "updatedDate": "2023-06-08T22:47:46.553766",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    }
  ],
  "success": true
}
```
7. Get Cities By Page
  
```text
GET : http://localhost:8080/api/1.0/cities/page?page=1&size=2
```

```json
{
  "message": "Listelendi",
  "data": [
    {
      "id": 2,
      "cityName": "Ankara",
      "temp": "20",
      "infoDate": "8-6-2023 22:47",
      "icon": "01n",
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:47:46.553766",
        "updatedDate": "2023-06-08T22:47:46.553766",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    },
    {
      "id": 3,
      "cityName": "Berlin",
      "temp": "25",
      "infoDate": "8-6-2023 22:47",
      "icon": "01n",
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:48:26.157918",
        "updatedDate": "2023-06-08T22:48:26.157918",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    }
  ],
  "success": true
}
```
8. Get Cities Order By Name
  
```text
GET : http://localhost:8080/api/1.0/cities/orderbyname
```

```json
{
  "message": "Listelendi",
  "data": [
    {
      "id": 2,
      "cityName": "Ankara",
      "temp": "20",
      "infoDate": "8-6-2023 22:47",
      "icon": "01n",
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:47:46.553766",
        "updatedDate": "2023-06-08T22:47:46.553766",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    },
    {
      "id": 3,
      "cityName": "Berlin",
      "temp": "25",
      "infoDate": "8-6-2023 22:47",
      "icon": "01n",
      "baseAdditionalFields": {
        "createdDate": "2023-06-08T22:48:26.157918",
        "updatedDate": "2023-06-08T22:48:26.157918",
        "createdBy": "aktansn",
        "updatedBy": "aktansn"
      }
    }
  ],
  "success": true
}
```
9. Update City By Id
  
```text
PUT : http://localhost:8080/api/1.0/cities/2
```

```json
Request:
{
  "cityName": "Mersin",
  "userId": 2,
  "temp": "30",
  "infoDate": "8-6-2023 22:47",
  "icon": "02n"
}
```
```json
Response:
{
  "message": "Güncellendi",
  "data": {
    "id": 4,
    "cityName": "Mersin",
    "temp": "30",
    "infoDate": "8-6-2023 22:47",
    "icon": "02n",
    "baseAdditionalFields": {
      "createdDate": "2023-06-08T22:59:59.4572657",
      "updatedDate": "2023-06-08T22:59:59.4572657",
      "createdBy": "aktansn",
      "updatedBy": "aktansn"
    }
  },
  "success": true
}
```
10. Delete City By Id
  
```text
DELETE : http://localhost:8080/api/1.0/cities/3
```

```json
{
  "message": "Silindi",
  "data": {
    "id": 3,
    "cityName": "Berlin",
    "temp": "25",
    "infoDate": "8-6-2023 22:47",
    "icon": "01n",
    "baseAdditionalFields": {
      "createdDate": "2023-06-08T22:48:26.157918",
      "updatedDate": "2023-06-08T22:48:26.157918",
      "createdBy": "aktansn",
      "updatedBy": "aktansn"
    }
  },
  "success": true
}
```
  
  ## Weather
  
1. Get All Weather Data
  
```text
Get : http://localhost:8080/weather/data?cityName=ankara
```
<details>
  <summary>Click for Repsonse</summary
    
    
{
  "message": "Listelendi",
  "data": {
    "cod": "200",
    "list": [
      {
        "dt": 1686258000,
        "main": {
          "temp": 21.78,
          "feels_like": 21.06,
          "temp_min": 18.34,
          "temp_max": 21.78,
          "pressure": 1006,
          "sea_level": 1006,
          "grnd_level": 913,
          "humidity": 40,
          "temp_kf": 3.44
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04n"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 2.2,
          "deg": 70,
          "gust": 2.25
        },
        "visibility": 10000,
        "pop": 0,
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-08 21:00:00"
      },
      {
        "dt": 1686268800,
        "main": {
          "temp": 19.98,
          "feels_like": 19.26,
          "temp_min": 16.39,
          "temp_max": 19.98,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 912,
          "humidity": 47,
          "temp_kf": 3.59
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04n"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 0.41,
          "deg": 28,
          "gust": 0.61
        },
        "visibility": 10000,
        "pop": 0.01,
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-09 00:00:00"
      },
      {
        "dt": 1686279600,
        "main": {
          "temp": 19,
          "feels_like": 18.31,
          "temp_min": 17.61,
          "temp_max": 19,
          "pressure": 1009,
          "sea_level": 1009,
          "grnd_level": 912,
          "humidity": 52,
          "temp_kf": 1.39
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04d"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 2.06,
          "deg": 66,
          "gust": 2.05
        },
        "visibility": 10000,
        "pop": 0.13,
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-09 03:00:00"
      },
      {
        "dt": 1686290400,
        "main": {
          "temp": 20.82,
          "feels_like": 20.24,
          "temp_min": 20.82,
          "temp_max": 20.82,
          "pressure": 1010,
          "sea_level": 1010,
          "grnd_level": 914,
          "humidity": 49,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04d"
          }
        ],
        "clouds": {
          "all": 96
        },
        "wind": {
          "speed": 0.52,
          "deg": 109,
          "gust": 1.99
        },
        "visibility": 10000,
        "pop": 0.17,
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-09 06:00:00"
      },
      {
        "dt": 1686301200,
        "main": {
          "temp": 24.52,
          "feels_like": 24.18,
          "temp_min": 24.52,
          "temp_max": 24.52,
          "pressure": 1009,
          "sea_level": 1009,
          "grnd_level": 914,
          "humidity": 44,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04d"
          }
        ],
        "clouds": {
          "all": 87
        },
        "wind": {
          "speed": 3.05,
          "deg": 106,
          "gust": 3.21
        },
        "visibility": 10000,
        "pop": 0.04,
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-09 09:00:00"
      },
      {
        "dt": 1686312000,
        "main": {
          "temp": 25.82,
          "feels_like": 25.5,
          "temp_min": 25.82,
          "temp_max": 25.82,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 913,
          "humidity": 40,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04d"
          }
        ],
        "clouds": {
          "all": 92
        },
        "wind": {
          "speed": 2.04,
          "deg": 117,
          "gust": 2.18
        },
        "visibility": 10000,
        "pop": 0,
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-09 12:00:00"
      },
      {
        "dt": 1686322800,
        "main": {
          "temp": 24.21,
          "feels_like": 23.97,
          "temp_min": 24.21,
          "temp_max": 24.21,
          "pressure": 1006,
          "sea_level": 1006,
          "grnd_level": 911,
          "humidity": 49,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04d"
          }
        ],
        "clouds": {
          "all": 96
        },
        "wind": {
          "speed": 2.48,
          "deg": 23,
          "gust": 2.44
        },
        "visibility": 10000,
        "pop": 0.14,
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-09 15:00:00"
      },
      {
        "dt": 1686333600,
        "main": {
          "temp": 17.09,
          "feels_like": 17.1,
          "temp_min": 17.09,
          "temp_max": 17.09,
          "pressure": 1009,
          "sea_level": 1009,
          "grnd_level": 911,
          "humidity": 86,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 501,
            "main": "Rain",
            "description": "moderate rain",
            "icon": "10n"
          }
        ],
        "clouds": {
          "all": 91
        },
        "wind": {
          "speed": 5.99,
          "deg": 8,
          "gust": 8.36
        },
        "visibility": 10000,
        "pop": 0.97,
        "rain": {
          "3h": 6.99
        },
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-09 18:00:00"
      },
      {
        "dt": 1686344400,
        "main": {
          "temp": 15.4,
          "feels_like": 15.29,
          "temp_min": 15.4,
          "temp_max": 15.4,
          "pressure": 1011,
          "sea_level": 1011,
          "grnd_level": 913,
          "humidity": 88,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 501,
            "main": "Rain",
            "description": "moderate rain",
            "icon": "10n"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 0.88,
          "deg": 145,
          "gust": 2.34
        },
        "visibility": 10000,
        "pop": 0.88,
        "rain": {
          "3h": 11.26
        },
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-09 21:00:00"
      },
      {
        "dt": 1686355200,
        "main": {
          "temp": 15.37,
          "feels_like": 15.23,
          "temp_min": 15.37,
          "temp_max": 15.37,
          "pressure": 1009,
          "sea_level": 1009,
          "grnd_level": 911,
          "humidity": 87,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10n"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 1.93,
          "deg": 7,
          "gust": 2.23
        },
        "visibility": 10000,
        "pop": 0.85,
        "rain": {
          "3h": 0.54
        },
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-10 00:00:00"
      },
      {
        "dt": 1686366000,
        "main": {
          "temp": 15.1,
          "feels_like": 14.94,
          "temp_min": 15.1,
          "temp_max": 15.1,
          "pressure": 1009,
          "sea_level": 1009,
          "grnd_level": 911,
          "humidity": 87,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04d"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 0.56,
          "deg": 332,
          "gust": 0.79
        },
        "visibility": 10000,
        "pop": 0,
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-10 03:00:00"
      },
      {
        "dt": 1686376800,
        "main": {
          "temp": 18.85,
          "feels_like": 18.49,
          "temp_min": 18.85,
          "temp_max": 18.85,
          "pressure": 1009,
          "sea_level": 1009,
          "grnd_level": 912,
          "humidity": 65,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04d"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 0.66,
          "deg": 346,
          "gust": 1.17
        },
        "visibility": 10000,
        "pop": 0,
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-10 06:00:00"
      },
      {
        "dt": 1686387600,
        "main": {
          "temp": 22.69,
          "feels_like": 22.37,
          "temp_min": 22.69,
          "temp_max": 22.69,
          "pressure": 1008,
          "sea_level": 1008,
          "grnd_level": 912,
          "humidity": 52,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04d"
          }
        ],
        "clouds": {
          "all": 99
        },
        "wind": {
          "speed": 0.33,
          "deg": 211,
          "gust": 1.12
        },
        "visibility": 10000,
        "pop": 0.12,
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-10 09:00:00"
      },
      {
        "dt": 1686398400,
        "main": {
          "temp": 24.82,
          "feels_like": 24.51,
          "temp_min": 24.82,
          "temp_max": 24.82,
          "pressure": 1006,
          "sea_level": 1006,
          "grnd_level": 911,
          "humidity": 44,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 79
        },
        "wind": {
          "speed": 1.54,
          "deg": 265,
          "gust": 1.7
        },
        "visibility": 10000,
        "pop": 0.31,
        "rain": {
          "3h": 0.19
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-10 12:00:00"
      },
      {
        "dt": 1686409200,
        "main": {
          "temp": 23.97,
          "feels_like": 23.7,
          "temp_min": 23.97,
          "temp_max": 23.97,
          "pressure": 1005,
          "sea_level": 1005,
          "grnd_level": 910,
          "humidity": 49,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 802,
            "main": "Clouds",
            "description": "scattered clouds",
            "icon": "03d"
          }
        ],
        "clouds": {
          "all": 41
        },
        "wind": {
          "speed": 3.01,
          "deg": 293,
          "gust": 3.4
        },
        "visibility": 10000,
        "pop": 0.32,
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-10 15:00:00"
      },
      {
        "dt": 1686420000,
        "main": {
          "temp": 19.67,
          "feels_like": 19.42,
          "temp_min": 19.67,
          "temp_max": 19.67,
          "pressure": 1006,
          "sea_level": 1006,
          "grnd_level": 910,
          "humidity": 66,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 802,
            "main": "Clouds",
            "description": "scattered clouds",
            "icon": "03n"
          }
        ],
        "clouds": {
          "all": 42
        },
        "wind": {
          "speed": 2.03,
          "deg": 0,
          "gust": 2.17
        },
        "visibility": 10000,
        "pop": 0.34,
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-10 18:00:00"
      },
      {
        "dt": 1686430800,
        "main": {
          "temp": 16.98,
          "feels_like": 16.74,
          "temp_min": 16.98,
          "temp_max": 16.98,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 910,
          "humidity": 77,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10n"
          }
        ],
        "clouds": {
          "all": 34
        },
        "wind": {
          "speed": 2.6,
          "deg": 59,
          "gust": 2.82
        },
        "visibility": 10000,
        "pop": 0.61,
        "rain": {
          "3h": 0.16
        },
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-10 21:00:00"
      },
      {
        "dt": 1686441600,
        "main": {
          "temp": 16.47,
          "feels_like": 16.26,
          "temp_min": 16.47,
          "temp_max": 16.47,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 910,
          "humidity": 80,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 803,
            "main": "Clouds",
            "description": "broken clouds",
            "icon": "04n"
          }
        ],
        "clouds": {
          "all": 54
        },
        "wind": {
          "speed": 0.87,
          "deg": 65,
          "gust": 1.29
        },
        "visibility": 10000,
        "pop": 0.47,
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-11 00:00:00"
      },
      {
        "dt": 1686452400,
        "main": {
          "temp": 16.36,
          "feels_like": 16.19,
          "temp_min": 16.36,
          "temp_max": 16.36,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 909,
          "humidity": 82,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 0.75,
          "deg": 82,
          "gust": 0.85
        },
        "visibility": 10000,
        "pop": 0.34,
        "rain": {
          "3h": 0.48
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-11 03:00:00"
      },
      {
        "dt": 1686463200,
        "main": {
          "temp": 19.19,
          "feels_like": 18.97,
          "temp_min": 19.19,
          "temp_max": 19.19,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 910,
          "humidity": 69,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04d"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 0.3,
          "deg": 162,
          "gust": 0.41
        },
        "visibility": 10000,
        "pop": 0.32,
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-11 06:00:00"
      },
      {
        "dt": 1686474000,
        "main": {
          "temp": 22.82,
          "feels_like": 22.59,
          "temp_min": 22.82,
          "temp_max": 22.82,
          "pressure": 1006,
          "sea_level": 1006,
          "grnd_level": 911,
          "humidity": 55,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 0.67,
          "deg": 254,
          "gust": 1.14
        },
        "visibility": 10000,
        "pop": 0.69,
        "rain": {
          "3h": 1.11
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-11 09:00:00"
      },
      {
        "dt": 1686484800,
        "main": {
          "temp": 24.09,
          "feels_like": 23.89,
          "temp_min": 24.09,
          "temp_max": 24.09,
          "pressure": 1005,
          "sea_level": 1005,
          "grnd_level": 910,
          "humidity": 51,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 97
        },
        "wind": {
          "speed": 1.66,
          "deg": 199,
          "gust": 2.12
        },
        "visibility": 10000,
        "pop": 0.8,
        "rain": {
          "3h": 2.75
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-11 12:00:00"
      },
      {
        "dt": 1686495600,
        "main": {
          "temp": 20.96,
          "feels_like": 20.89,
          "temp_min": 20.96,
          "temp_max": 20.96,
          "pressure": 1005,
          "sea_level": 1005,
          "grnd_level": 910,
          "humidity": 68,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 92
        },
        "wind": {
          "speed": 2.15,
          "deg": 46,
          "gust": 3.37
        },
        "visibility": 10000,
        "pop": 0.59,
        "rain": {
          "3h": 2.56
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-11 15:00:00"
      },
      {
        "dt": 1686506400,
        "main": {
          "temp": 17.86,
          "feels_like": 17.63,
          "temp_min": 17.86,
          "temp_max": 17.86,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 910,
          "humidity": 74,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10n"
          }
        ],
        "clouds": {
          "all": 74
        },
        "wind": {
          "speed": 2.81,
          "deg": 65,
          "gust": 2.71
        },
        "visibility": 10000,
        "pop": 0.65,
        "rain": {
          "3h": 0.28
        },
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-11 18:00:00"
      },
      {
        "dt": 1686517200,
        "main": {
          "temp": 16.62,
          "feels_like": 16.43,
          "temp_min": 16.62,
          "temp_max": 16.62,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 909,
          "humidity": 80,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 803,
            "main": "Clouds",
            "description": "broken clouds",
            "icon": "04n"
          }
        ],
        "clouds": {
          "all": 74
        },
        "wind": {
          "speed": 1.42,
          "deg": 73,
          "gust": 1.86
        },
        "visibility": 10000,
        "pop": 0.29,
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-11 21:00:00"
      },
      {
        "dt": 1686528000,
        "main": {
          "temp": 16.31,
          "feels_like": 16.16,
          "temp_min": 16.31,
          "temp_max": 16.31,
          "pressure": 1006,
          "sea_level": 1006,
          "grnd_level": 909,
          "humidity": 83,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 804,
            "main": "Clouds",
            "description": "overcast clouds",
            "icon": "04n"
          }
        ],
        "clouds": {
          "all": 87
        },
        "wind": {
          "speed": 1.32,
          "deg": 45,
          "gust": 1.38
        },
        "visibility": 10000,
        "pop": 0.33,
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-12 00:00:00"
      },
      {
        "dt": 1686538800,
        "main": {
          "temp": 16.17,
          "feels_like": 16.06,
          "temp_min": 16.17,
          "temp_max": 16.17,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 909,
          "humidity": 85,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 98
        },
        "wind": {
          "speed": 0.63,
          "deg": 85,
          "gust": 0.98
        },
        "visibility": 10000,
        "pop": 0.38,
        "rain": {
          "3h": 0.19
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-12 03:00:00"
      },
      {
        "dt": 1686549600,
        "main": {
          "temp": 16.14,
          "feels_like": 16.16,
          "temp_min": 16.14,
          "temp_max": 16.14,
          "pressure": 1008,
          "sea_level": 1008,
          "grnd_level": 910,
          "humidity": 90,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 501,
            "main": "Rain",
            "description": "moderate rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 99
        },
        "wind": {
          "speed": 1.45,
          "deg": 254,
          "gust": 2.3
        },
        "visibility": 10000,
        "pop": 0.88,
        "rain": {
          "3h": 3.58
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-12 06:00:00"
      },
      {
        "dt": 1686560400,
        "main": {
          "temp": 17.06,
          "feels_like": 16.94,
          "temp_min": 17.06,
          "temp_max": 17.06,
          "pressure": 1008,
          "sea_level": 1008,
          "grnd_level": 911,
          "humidity": 81,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 2.25,
          "deg": 301,
          "gust": 3.05
        },
        "visibility": 10000,
        "pop": 0.84,
        "rain": {
          "3h": 1.66
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-12 09:00:00"
      },
      {
        "dt": 1686571200,
        "main": {
          "temp": 18.86,
          "feels_like": 18.63,
          "temp_min": 18.86,
          "temp_max": 18.86,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 910,
          "humidity": 70,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 96
        },
        "wind": {
          "speed": 3.28,
          "deg": 329,
          "gust": 3.83
        },
        "visibility": 10000,
        "pop": 0.85,
        "rain": {
          "3h": 0.21
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-12 12:00:00"
      },
      {
        "dt": 1686582000,
        "main": {
          "temp": 19.54,
          "feels_like": 19.27,
          "temp_min": 19.54,
          "temp_max": 19.54,
          "pressure": 1006,
          "sea_level": 1006,
          "grnd_level": 910,
          "humidity": 66,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 53
        },
        "wind": {
          "speed": 3.25,
          "deg": 313,
          "gust": 3.24
        },
        "visibility": 10000,
        "pop": 0.48,
        "rain": {
          "3h": 0.73
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-12 15:00:00"
      },
      {
        "dt": 1686592800,
        "main": {
          "temp": 15.83,
          "feels_like": 15.56,
          "temp_min": 15.83,
          "temp_max": 15.83,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 909,
          "humidity": 80,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10n"
          }
        ],
        "clouds": {
          "all": 35
        },
        "wind": {
          "speed": 1.9,
          "deg": 308,
          "gust": 2.09
        },
        "visibility": 10000,
        "pop": 0.45,
        "rain": {
          "3h": 0.48
        },
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-12 18:00:00"
      },
      {
        "dt": 1686603600,
        "main": {
          "temp": 14.59,
          "feels_like": 14.4,
          "temp_min": 14.59,
          "temp_max": 14.59,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 909,
          "humidity": 88,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10n"
          }
        ],
        "clouds": {
          "all": 47
        },
        "wind": {
          "speed": 1.08,
          "deg": 331,
          "gust": 1.13
        },
        "visibility": 10000,
        "pop": 0.47,
        "rain": {
          "3h": 0.48
        },
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-12 21:00:00"
      },
      {
        "dt": 1686614400,
        "main": {
          "temp": 13.98,
          "feels_like": 13.76,
          "temp_min": 13.98,
          "temp_max": 13.98,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 908,
          "humidity": 89,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10n"
          }
        ],
        "clouds": {
          "all": 72
        },
        "wind": {
          "speed": 1.39,
          "deg": 350,
          "gust": 1.45
        },
        "visibility": 10000,
        "pop": 0.47,
        "rain": {
          "3h": 0.21
        },
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-13 00:00:00"
      },
      {
        "dt": 1686625200,
        "main": {
          "temp": 14.72,
          "feels_like": 14.55,
          "temp_min": 14.72,
          "temp_max": 14.72,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 909,
          "humidity": 88,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 77
        },
        "wind": {
          "speed": 1.11,
          "deg": 17,
          "gust": 1.26
        },
        "visibility": 10000,
        "pop": 0.37,
        "rain": {
          "3h": 0.24
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-13 03:00:00"
      },
      {
        "dt": 1686636000,
        "main": {
          "temp": 16.31,
          "feels_like": 16.11,
          "temp_min": 16.31,
          "temp_max": 16.31,
          "pressure": 1008,
          "sea_level": 1008,
          "grnd_level": 910,
          "humidity": 81,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 88
        },
        "wind": {
          "speed": 1.06,
          "deg": 345,
          "gust": 1.54
        },
        "visibility": 10000,
        "pop": 0.44,
        "rain": {
          "3h": 0.43
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-13 06:00:00"
      },
      {
        "dt": 1686646800,
        "main": {
          "temp": 16.77,
          "feels_like": 16.57,
          "temp_min": 16.77,
          "temp_max": 16.77,
          "pressure": 1008,
          "sea_level": 1008,
          "grnd_level": 910,
          "humidity": 79,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 100
        },
        "wind": {
          "speed": 0.59,
          "deg": 280,
          "gust": 1.12
        },
        "visibility": 10000,
        "pop": 0.8,
        "rain": {
          "3h": 1.07
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-13 09:00:00"
      },
      {
        "dt": 1686657600,
        "main": {
          "temp": 18.77,
          "feels_like": 18.58,
          "temp_min": 18.77,
          "temp_max": 18.77,
          "pressure": 1007,
          "sea_level": 1007,
          "grnd_level": 910,
          "humidity": 72,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 99
        },
        "wind": {
          "speed": 0.89,
          "deg": 39,
          "gust": 1.56
        },
        "visibility": 10000,
        "pop": 0.99,
        "rain": {
          "3h": 1.41
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-13 12:00:00"
      },
      {
        "dt": 1686668400,
        "main": {
          "temp": 19.44,
          "feels_like": 19.24,
          "temp_min": 19.44,
          "temp_max": 19.44,
          "pressure": 1006,
          "sea_level": 1006,
          "grnd_level": 910,
          "humidity": 69,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10d"
          }
        ],
        "clouds": {
          "all": 91
        },
        "wind": {
          "speed": 1.97,
          "deg": 37,
          "gust": 2.38
        },
        "visibility": 10000,
        "pop": 0.91,
        "rain": {
          "3h": 2.19
        },
        "sys": {
          "pod": "d"
        },
        "dt_txt": "2023-06-13 15:00:00"
      },
      {
        "dt": 1686679200,
        "main": {
          "temp": 16.03,
          "feels_like": 15.75,
          "temp_min": 16.03,
          "temp_max": 16.03,
          "pressure": 1008,
          "sea_level": 1008,
          "grnd_level": 910,
          "humidity": 79,
          "temp_kf": 0
        },
        "weather": [
          {
            "id": 500,
            "main": "Rain",
            "description": "light rain",
            "icon": "10n"
          }
        ],
        "clouds": {
          "all": 93
        },
        "wind": {
          "speed": 1.4,
          "deg": 35,
          "gust": 1.48
        },
        "visibility": 10000,
        "pop": 0.8,
        "rain": {
          "3h": 0.31
        },
        "sys": {
          "pod": "n"
        },
        "dt_txt": "2023-06-13 18:00:00"
      }
    ],
    "city": {
      "id": 323786,
      "name": "Ankara",
      "coord": {
        "lat": 39.9199,
        "lon": 32.8543
      },
      "country": "TR",
      "population": 3517182,
      "timezone": 10800,
      "sunrise": 1686190800,
      "sunset": 1686244500
    }
  },
  "success": true
}

  </details>
2. Get Current Weather Data
  
```text
GET : http://localhost:8080/weather/currentWeather?cityName=ankara
```

```json
{
  "message": "Listelendi",
  "data": {
    "coord": {
      "lon": 32.8543,
      "lat": 39.9199
    },
    "weather": [
      {
        "id": 804,
        "main": "Clouds",
        "description": "overcast clouds",
        "icon": "04n"
      }
    ],
    "base": "stations",
    "main": {
      "temp": 21.78,
      "feels_like": 21.06,
      "temp_min": 17.51,
      "temp_max": 21.78,
      "pressure": 1006,
      "humidity": 40
    },
    "visibility": 10000,
    "wind": {
      "speed": 2.55,
      "deg": 63
    },
    "clouds": {
      "all": 100
    },
    "dt": 1686254700,
    "sys": {
      "type": 2,
      "id": 267643,
      "country": "TR",
      "sunrise": 1686190800,
      "sunset": 1686244500
    },
    "timezone": 10800,
    "id": 323786,
    "name": "Ankara",
    "cod": 200
  },
  "success": true
}
```
## Swagger
![Photo](https://user-images.githubusercontent.com/58556840/244499476-b5f4bf68-2789-4784-9b3d-1563e5adc48c.png)  
![Photo](https://user-images.githubusercontent.com/58556840/244499481-fe8b1bb2-eac5-4d40-8523-ad8bfe7d8e06.png)  

