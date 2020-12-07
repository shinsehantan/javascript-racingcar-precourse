# 🏎️ 자동차 경주 게임

- 우아한테크코스의 2주차 미션인 자동차 경주 게임 구현하기 프로젝트입니다.
- 객체 지향형, 함수 분리, 모듈화에 주의하며 구현하였습니다.
- 자바스크립트 코드 컨벤션을 지키며 순수 vanilla JS로만 구현하였습니다.

## 👩🏻‍💻 기능 목록

- elments에 id 부여
- 횟수 입력, 실행 결과창 숨김 처리

  - 숨기기 방식 display(none, block)에서 visibility(hidden, visible)로 수정

- 자동차 이름 입력 버튼에 이벤트 리스너 추가
- 입력이 유효하지 않을 경우 alert 메시지 띄우기

  - 5자 이상인 이름이 포함되어 있는 경우
  - 0자 이하인 이름이 포함되어 있는 경우
  - 플레이어가 1명일 경우에는 홀로 플레이하는 것으로 설정

- 자동차 이름, 랜덤 숫자, move 부여한 car 객체 생성
- 랜덤 숫자 생성하여 객체에 업데이트
- 횟수 입력창 숨김 해제 처리
- 횟수 입력 버튼에 이벤트 리스너 추가
- 입력이 유효하지 않을 경우 alert 메시지 띄우기

  - 음수를 입력할 경우

- 전진 여부 출력을 위해 car 객체에 move 인스턴스 업데이트
- 입력된 횟수만큼 레이싱 결과 출력
- 우승자 판별 및 이름 출력
- 실행 결과창 숨김 해제 처리

## ⛓ 문서 구조

```plaintext
├── .vscode
│   └── setting.json
│
├── docs
│   └── README.md            // 구현할 기능 목록을 적은 문서
│
├── images
│   ├── result.gif
│   └── result.jpg
│
├── src
│   ├── core                 // 게임 실행에 핵심이 되는 파일을 모아놓은 상위 폴더
│   │   │   car.js           // car 객체를 생성하는 파일
│   │   └── racingCarGame.js // 생성된 car 객체를 받아 우승자의 이름을 출력하는 게임의 핵심 역할을 하는 파일
│   │
│   ├── Manager              // 게임 실행을 돕는 파일을 모아놓은 상위 폴더
│   │   ├── gameManager.js   // 입력, 검증, 실행, 출력 등 게임 진행을 돕는 파일
│   │   ├── uiManager.js     // elment에 id 부여, 숨김, 표시 및 ui와 관련된 일을 담당하는 파일
│   │   └── utils.js         // car 객체 생성을 돕는 파일
│   │
│   ├── index.js             // 파일 오픈과 동시에 main 함수를 실행하는 파일
│   ├── main.js              // RacingCarGame을 생성하는 파일
│   │
├── index.html
└── LICENSE
```

---

## 🎯 기능 요구사항

- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 random 값을 구한 후 random 값이 4 이상일 경우 전진하고, 3 이하의 값이면 멈춘다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.
- 우승자가 여러명일 경우 ,를 이용하여 구분한다.

## 💻 프로그램 실행 결과

![실행이미지](images/result.gif)
![실행이미지](images/result.jpg)

## ✅ 프로그래밍 요구사항

- 사용자가 잘못된 입력 값을 작성한 경우 `alert`을 이용해 메시지를 보여주고, 재입력할 수 있게 한다.
- 외부 라이브러리(jQuery, Lodash 등)를 사용하지 않고, 순수 Vanilla JS로만 구현한다.
- **자바스크립트 코드 컨벤션을 지키면서 프로그래밍** 한다
  - [https://google.github.io/styleguide/jsguide.html](https://google.github.io/styleguide/jsguide.html)
  - [https://ui.toast.com/fe-guide/ko_CODING-CONVENSION/](https://ui.toast.com/fe-guide/ko_CODING-CONVENTION)
- **indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용**한다.
  - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
  - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메소드)를 분리하면 된다.
- **함수(또는 메소드)가 한 가지 일만 하도록 최대한 작게** 만들어라.

### 추가된 요구사항

- **함수(또는 메소드)의 길이가 15라인을 넘어가지 않도록 구현한다.**
  - 함수(또는 메소드)가 한 가지 일만 잘 하도록 구현한다.
- 자동차의 이름을 입력하는 input 태그는 `#car-names-input` id값을 가진다.
- 자동차의 이름을 제출하는 button 태그는 `#car-names-submit` id값을 가진다.
- 레이싱 횟수를 입력하는 input 태그는 `#racing-count-input` id값을 가진다.
- 레이싱 횟수을 제출하는 button 태그는 `#racing-count-submit` id값을 가진다.
- 다음 Car 객체를 만들고, new 를 이용해 인스턴스를 만든다.

```javascript
function Car(name) {
  this.name = name;
}

class Car {
  constructor(name) {
    this.name = name;
  }
}
```

- 변수 선언시 `var` 를 사용하지 않는다. `const` 와 `let` 을 사용한다.
  - [const](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/const)
  - [let](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/let)
- `import` 문을 이용해 스크립트를 모듈화하고 불러올 수 있게 만든다.
  - [https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/import](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Statements/import)
- `template literal`을 이용해 데이터와 html string을 가독성 좋게 표현한다.
  - [https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Template_literals](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Template_literals)

## 📝 미션 저장소 및 진행 요구사항

- 미션은 [https://github.com/woowacourse/javascript-racingcar-precours](https://github.com/woowacourse/javascript-racingcar-precourse) 저장소를 fork/clone해 시작한다.
- **기능을 구현하기 전에 javascript-racingcar-precourse/docs/README.md 파일에 구현할 기능 목록**을 정리해 추가한다.
- **git의 commit 단위는 앞 단계에서 README.md 파일에 정리한 기능 목록 단위로 추가**한다.
- [프리코스 과제 제출](https://github.com/woowacourse/woowacourse-docs/tree/master/precourse) 문서 절차를 따라 미션을 제출한다.
