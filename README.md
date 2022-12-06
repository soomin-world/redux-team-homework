## Q1. 컴포넌트 A는 리덕스 스토어를 구독하고 있습니다. 리덕스에 저장된 데이터가 변경되었을 때(A가 구독 중인 값이 변경되었다고 가정합니다. 어떤 과정을 거쳐 컴포넌트 A가 변경된 값을 가져올 수 있는 지 흐름을 그려볼까요? (메모장, 사진 등)

A에서 값 변경이 일어남(액션) -> <br>
디스패치가 해당 액션을 reducer에 전달 -> <br>
reducer내에서 [State]에 있는 값을 꺼내어 요청한 [Action(명령)]을 수행 후 변경된값을 다시 [State]에 쓴다.
(이 때 기존에 가지고 있던 [State]는 사라지며, 동일한 이름으로 다시 새로 쓰여지게 된다.)- ><br>
변경된 새로운 상태 값은 Store 저장된다-><br>
Store에서 구독 중인 A에 수정된 데이터를 넘겨준다

## Q2. 옵셔널 체이닝이란 뭘까요? 어떤 경우에 사용할까요?

optional chaning연산자 (?.)는 객체 내의 key에 접근할 때 그 참조가 유효한지 아닌지 직접 명시하지 않고도 접근할 수 있는 연산자입니다.

?. 앞의 평가대상이 만약 nullish ( undefined 또는 null ) 일 경우 평가를 멈추고 undefined를 반환합니다.

우리는 코드를 짜면서 객체내의 값을 접근하는 경우가 종종 있습니다. 하지만 항상 그 key값이 존재하는 경우 보다는 없는 경우도 있기 때문에 옵셔널 

## Q3. <form>을 사용할 때, <button type="submit">을 함께 사용하면 리덕스 데이터가 초기화 되는데, 왜 초기화 되는 지 생각해봅시다.

< form > 내부의 < button >은 클릭시 submit 이벤트가 발생되는데 데이터를 submit하기 위해 페이지를 리로딩하고 그 페이지가 리로딩되면 리덕스 store의 state 값이 초기화가 된다

## Q4. 새로고침 시에도 리덕스 내의 데이터를 유지하려면 어떤 방법을 써야할까요?

- state를 LocalStorage, SessionStorage에 직접 저장, 삭제유지하고 싶은 데이터를 LocalStorage, SessionStorage에 저장
- Redux-Persist 라이브러리 사용하기
    - Redux-Persist : LocalStorage, SeesionStorage를 redux에서 사용
    - Redux-Persist의 persistReducer를 특정 Reducer와 결합 후 Storage에서 저장
    - [https://11001.tistory.com/191](https://11001.tistory.com/191)
