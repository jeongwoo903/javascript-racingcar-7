# javascript-racingcar-precourse

## 파일 구조

```markdown
src
┣ constants
┃ ┣ message.js
┃ ┗ threshold.js
┣ utils
┃ ┣ validator
┃ ┃ ┣ car.js
┃ ┃ ┗ count.js
┃ ┣ view
┃ ┃ ┣ input.js
┃ ┃ ┗ output.js
┃ ┣ error.js
┃ ┣ parser.js
┃ ┗ sort.js
┣ App.js
┣ Car.js
┣ Race.js
┗ index.js
```

## 진행 순서도

- [x] 게임 시작
    - **[ 출력 ]** 사용자에게 `경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)` 문구를 출력해준다.
    - **[ 입력 ]** 사용자가 경주할 자동차 이름을 입력한다.
        - **[ 검증 ]** 이름이 빈 값인가?
        - **[ 검증 ]** 이름이 5글자 이하인가?
    - **[ 출력 ]** 사용자에게 `시도할 횟수는 몇 회인가요?` 문구를 출력한다.
    - **[ 입력 ]** 사용자가 시도할 횟수를 입력한다.
        - **[ 검증 ]** 입력된 시도 횟수가 숫자 타입인가?
        - **[ 검증 ]** 시도할 횟수가 1 이상인가?
- [x] 자동차 경주 진행
    - **[ 기능 ]** 사용자의 입력값으로 부터 이름을 추출한다.
    - **[ 기능 ]** 사용자가 요청한 횟수만큼 세트를 반복한다.
        - **[ 기능 ]** 0~9 사이의 무작위 값을 생성해 조건에 부합시 해당 자동차의 포인트를 +1 한다.
            - **[ 검증 ]** 무작위 값이 4 이상인가?
        - **[ 출력 ]** 한 세트가 끝날때마다 해당 자동차 가지고 있는 point만큼 `-`를 출력한다.
- [x] 우승 자동차 선정
    - **[ 기능 ]** 자동차들을 point에 따라서 내림차순으로 정렬한다.
        - **[ 검증 ]** 인덱스 0번째와 같은 점수의 자동차가 있는가?
- [x] 게임 종료
    - **[ 출력 ]** 사용자에게 `최종 우승자 : {우승 자동차}` 문구를 출력한다.

## 구현할 기능 목록

> 각 타이틀은 기능 분류 정도로 생각해주시면 됩니다.

### App

- [x] 자동차 경주 게임을 실행시킨다.

### Car

- **속성**
    - `name`: 자동차 이름
    - `points`: 전진한 횟수
- **기능**
    - [x] 랜덤 숫자가 전진 기준 숫자(예: 4) 이상인 경우 `points`을 1 증가시킨다.
    - [x] 자동차의 이름을 반환한다.
    - [x] 자동차의 현재 점수를 반환한다.

### Race

- **속성**
    - `cars`: `Car` 객체들의 리스트
    - `count`: 시도 횟수
    - `winner`: 우승자 리스트
- **기능**
    - [x] `count`만큼 게임을 진행한다.
    - [x] 자동차의 수 만큼 경주를 진행시킨다.
    - [x] `cars` 리스트를 받아 가장 높은 `points` 값을 가진 자동차(들)을 찾아낸다.
    - [x] 우승자 이름들의 리스트를 반환한다.

### Input

- [x] 사용자에게 `경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)` 메시지를 출력한다.
- [x] 사용자에게 `시도할 횟수는 몇 회인가요?` 메시지를 출력한다.

### Output

- [x] 각 자동차의 현재 점수를 `-`로 표시하여 출력한다.
- [x] 우승자 이름들을 쉼표로 구분하여 `최종 우승자 : pobi, crong` 형식으로 출력한다.

### Validator

- [x] 입력된 자동차들의 이름이 빈 값인지 검증한다.
- [x] 각 이름이 최대 이름 길이(예: 5글자) 이하인지 검증한다.
- [x] 입력된 시도 횟수가 숫자 타입인지 검증한다.
- [x] 시도 횟수가 1 이상인지 검증한다.

### Parser

- [x] 입력된 문자열을 쉼표 기준으로 분리하여 자동차 이름의 리스트로 반환한다.

### Sort

- [x] `cars` 리스트를 받아 내림차순 정렬한다.

### Error

- [x] 에러 메세지를 받아 `throw new Error`를 수행한다.

### Constants

- [x] 게임에서 사용되는 상수값들을 관리한다.

## 테스트 목록

### CarTest

- [x] 올바른 이름 값이 입력된 경우
- [x] 빈 이름 값이 입력된 경우
- [x] 이름이 5자 이상 입력된 경우

### CountTest

- [x] 올바른 시도 횟수가 입력된 경우
- [x] 시도 횟수가 입력되지 않은 경우
- [x] 시도 횟수가 1미만인 경우

### OutputTest

- [x] 실행 결과가 올바르게 출력 되는가
- [x] 우승자가 올바르게 출력 되는가
