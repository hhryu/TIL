## MVC Pattern

#### 1. Model

- Data + State + Business logic
- View나 Controller에 종속되지 않으므로 재사용에 용이.



#### 2. View

- 모델의 표현(UI).
- 사용자가 버튼을 클릭하거나 값을 입력하면 Controller에게 통지.
- Controller로부터 Model의 변경을 통지받아 그 결과를 표현.



#### 3. Controller

- Model이나 View의 변경을 통지받으면 그것을 전달하는 역할.

  

![1530758038530](C:\Users\hhryu\AppData\Local\Temp\1530758038530.png)

#### 4. 문제점

- 모듈화 및 유연성 : Controller가 View에 족송되므로 View를 변경하면 Controller도 변경되어야 함.
- 유지보수 :  시간이 흐를수록 Controller의 코드 비중이 많아져 문제가 발생하기 쉬워짐.