# Django(Python)과 MySQL의 연동
---
## Django 및 MySQL 설치
> PyCharm을 이용해서 Django와 MySQL을 설치 후 사용해보자.  
![image](https://user-images.githubusercontent.com/71700079/142802244-67715e87-3f54-4a3b-a78f-61d7615204d6.png)  
![image](https://user-images.githubusercontent.com/71700079/142802337-fb1f24dd-272d-49c3-a7fd-cecf0ccc7fe6.png)  

- 먼저 Terminal에 위 두 명령어를 이용해 Django와 MySQL을 설치하여야한다.
- 안될 시에 아래와 같은 명령어를 따로 입력해 준다.

![image](https://user-images.githubusercontent.com/71700079/142802391-9668091d-9a78-441b-a2c7-2af9adbdfeff.png)  
![image](https://user-images.githubusercontent.com/71700079/142802432-95a163c5-9091-4312-9b3f-72ef5635c189.png)  

## MySQL DATABASE 생성
- MySQL을 켠 후, Connection을 새로 만들어 놓는다.
- Connection에 접속하면, Query 창이 뜨는데, 모든 명령은 Query 창에서 진행되며 아래와 같이 새 DB를 생성한다.  

![image](https://user-images.githubusercontent.com/71700079/142802654-3fd16eab-f873-43ec-b894-5ac145382d03.png)

- 그 이후 CREATE TABLE 등으로 직접 DB를 Manage 해보면 되겠다.  

## Django & MySQL Migration
> Web Framework인 Django를 통해서 웹과 DB를 연결해보자.  
1. 먼저 Django Project를 새로 만들어야한다. 아래와 같이.  
  ![image](https://user-images.githubusercontent.com/71700079/142802830-72401d3a-df73-4080-ac1b-8eef1bc47b6a.png)  
  ![image](https://user-images.githubusercontent.com/71700079/142802860-87eec32b-ed96-4f80-bd4b-e1f981aa58e4.png)  
    - Mark Directory as 항목을 통해 Sources Root Folder로 설정해주어야 한다.

2. Django Project를 만들었으니 그 안에 Django Application을 새로 만들어주어야 한다.  
  ![image](https://user-images.githubusercontent.com/71700079/142802983-db4935c8-8a6f-4fd3-a9ed-76211e293c13.png)  
  ![image](https://user-images.githubusercontent.com/71700079/142802999-ab94674e-f1e9-4c89-9912-00dc5ece0f8d.png)  

3. 새로 만든 Django Application을 이제 testDB 폴더의 ```Settings.py``` 등록해주어야 사용이 가능하다.  
  ![image](https://user-images.githubusercontent.com/71700079/142803077-535b9f65-71fc-485c-b984-d725c65f3ad2.png)  

4. 아래와 같이 Database와의 Migration을 진행해준뒤, 서버가 잘 열리는 지 확인해본다.
  ![image](https://user-images.githubusercontent.com/71700079/142803165-95f6d9d4-dfdb-4ee6-a6ba-2007cebd8ae1.png)  
  ![image](https://user-images.githubusercontent.com/71700079/142803189-c4f9d228-5288-4f58-9f1e-2a3b0b7949f2.png)  
    - 홈페이지가 무사히 열리면 제대로 Migration이 완료된 것이다.

5. 이제 MySQL로 만든 Database를 Django Project로 가져와야 한다. 아래와 같이 진행한다.  
    - testDB의 Settings 파일 내에 DATABASE를 추가한다.  
 
  ![image](https://user-images.githubusercontent.com/71700079/142803332-ca5fbb15-194c-46b0-996c-3a313b418b8b.png)  
    - 추가한 뒤 이전에 진행했던 ```python manage.py migration``` 작업을 한번 더 해준다.  

  ![image](https://user-images.githubusercontent.com/71700079/142803735-fa15273f-ba25-48b6-ac0f-a8d822fce93a.png)  
  ![image](https://user-images.githubusercontent.com/71700079/142803771-97f30f16-bff0-495b-ba1e-f4d3ecf07643.png)  
    - inspectdb 명령어를 이용하면, 이렇게 mySQL에서 만든 DB의 Table이 나온다.






