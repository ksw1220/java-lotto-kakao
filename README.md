# java-lotto-kakao

## 문제정의
- 로또 구입 금액을 입력하면 구입 금액에 해당하는 로또를 발급해야 한다.
- 로또 1장의 가격은 1000원이다.

---

## 구현할 기능 목록


---

## 도메인
- GeneralNumber (숫자 클래스)
  - 검증
    - 최소 최대값 범위 확인
    - 숫자가 맞는지
- WinningLotto (당첨 번호 숫자 리스트 일급 컬렉션) extend Lotto
  - 입력된 친구
  - 검증
    - 사이즈 6개
    - 모두 다른 숫자
- Lotto (로또 번호 숫자 리스트)
  - [1, ... , 45] 변수로 가지고 있음
  - 생성자에서 Collections.shuffle() -> 앞의 6개 뽑아서 저장
  - getResult(WinningLotto, BonusNumber)
    - 알맞은 Result를 계산하는 로직
    - contains 합
    - 보너스볼 일치여부
    - Result Enum 타입 마다 테스트 구현
- BonusNumber (보너스)
  - GeneralNumber 클래스 상속
  - 당첨 번호와 다른 숫자
- Lottos (List<Lotto>)
  - 생성자(금액) -> List<Lotto> 생성
  - checkWin(WinningLotto, Bonus) 당첨 확인 기능
    - Map<Result, Integer> return
  - WinningLotto, Bonus를 가지고 있음 생성할 때
- Profit (일치 결과 맵 일급 컬렉션)
  - Map<Result, Integer>
  - 수익률 계산
- Result (로또 일치 여부 Enum)
  - Result.[THREE, FOUR, FIVE, FIVEBONUS, SIX]
- Constants (공통 상수 모음)
  - 로또 범위 최소/최대, 로또 번호 길이, 구분자 등

---

## 입출력

---

## 컨트롤러

- 컨트롤러 (Controller)
  - 구입 금액 입력 요구 (Out)
  - 구입 금액 입력 (In)
  - 로또 개수 출력 (Out)
  - 구입 금액에 맞는 로또 번호 목록 생성 (Lottos)
  - 로또 번호 목록 출력 (Out)
  - 당첨 번호 입력 요구 (Out)
  - 당첨 번호 입력 (In)
  - WinningNumbers 생성 (WinningNumbers)
  - 보너스볼 번호 입력 요구 (Out)
  - 보너스볼 번호 입력 (In)
  - Bonus 생성 (Bonus)
  - 번호 일치 여부 판단 (Check)
  - 번호 일치 여부 출력 (Out)
  - 수익률 계산 (Profit)
  - 수익률 출력 (Out)


구입금액을 입력해 주세요.
14000
14개를 구매했습니다.
[8, 21, 23, 41, 42, 43]
[3, 5, 11, 16, 32, 38]
[7, 11, 16, 35, 36, 44]
[1, 8, 11, 31, 41, 42]
[13, 14, 16, 38, 42, 45]
[7, 11, 30, 40, 42, 43]
[2, 13, 22, 32, 38, 45]
[23, 25, 33, 36, 39, 41]
[1, 3, 5, 14, 22, 45]
[5, 9, 38, 41, 43, 44]
[2, 8, 9, 18, 19, 21]
[13, 14, 18, 21, 23, 35]
[17, 21, 29, 37, 42, 45]
[3, 8, 27, 30, 35, 44]

지난 주 당첨 번호를 입력해 주세요.
1, 2, 3, 4, 5, 6
보너스 볼을 입력해 주세요.
7

당첨 통계
---------
3개 일치 (5000원)- 1개
4개 일치 (50000원)- 0개
5개 일치 (1500000원)- 0개
5개 일치, 보너스 볼 일치(30000000원) - 0개
6개 일치 (2000000000원)- 0개
총 수익률은 0.35입니다.(기준이 1이기 때문에 결과적으로 손해라는 의미임)

---

1. 일급컬렉션에 static 변수가 있어도 되는가?
2. Map 변수 이름,,,
3. 메서드 파라미터에 왜 final?
4. 생성자 바디에서 this()는 왜,,,맨 위로 가야되나요ㅠ
5. test코드에서 특정 예외가 발생하지 않는다는 것은 어떻게 테스트하나요?
6. 