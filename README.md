# TDD (Test Driven Development)

### Right-BICEP: 무엇을 테스트할 것인가?
|분류|내용|
|------|---|
|Right|결과가 올바른가|
|B|경계 조건(boundary conditions)은 맞는가|
|I|역 관계(inverse relationship)를 검사할 수 있는가|
|C|다른 수단을 활용하여 교차 검사(cross-check) 할 수 있는가|
|E|오류 조건(error  conditions)을 강제로 일어나게 할 수 있는가|
|P|성능 조건(performance characteristics)은 기준에 부합하는가|

1. [Right]-BICEP: 결과가 올바른가?
   - 테스트 코드는 무엇보다도 먼저 기대한 결과를 산출하는지 검증할 수 있어야 한다.


2. Right-[B]ICEP: 경계 조건은 맞는가?
   1) 경계 조건
      - 모호하고 일관성 없는 입력 값 (ex. 특수문자)
      - 잘못된 양식의 데이터 (ex. 이메일 주소 - jhchoi@google.)
      - 수치적 오버플로를 일으키는 계산
      - 비거나 빠진 값 (ex. "", null, 0)
      - 이성적인 기댓값을 훨씬 벗어나는 값 (ex. 200세의 나이)
      - 중복을 허용해서는 안 되는 목록에 중복 값이 있는 경우
      - 정렬이 안 된 정렬 리스트 혹은 그 반대 (ex. 퀵 정렬 알고리즘에 역순 데이터를 넣으면 성능 최악)
      - 시간 순이 맞지 않는 경우

   2) 경계 조건에서는 CORRECT를 기억하라
      |분류|내용|
      |------|---|
      |Conformance(준수)|값이 기대한 양식을 준수하고 있는가?|
      |Ordering(순서)|값의 집합이 적절하게 정렬되거나 정렬되지 않았나?|
      |Range(범위)|이성적인 최솟값과 최댓값 안에 있는가?|
      |Reference(참조)|코드 자체에서 통제할 수 없는 어떤 외부 참조를 포함하고 있는가?|
      |Existence(존재)|값이 존재하는가? (ex. null 이 아니거나, 0이 아니거나, 등등..) |
      |Cardinality(기수)|정확히 충분한 값들이 있는가?|
      |Time(절대적 혹은 상대적 시간)|모든 것이 순서대로 일어나는가? 정확한 시간에? 정시에?|
      
      
3. Right-B[I]CEP: 역 관계를 검사할 수 있는가?
   - 논리적인 역 관계를 적용하여 검사한다.
   - ex. 곱셈으로 나눗셈을 검증하고 뺄셈으로 덧셈을 검증
    
4. Right-BI[C]EP: 다른 수단을 활용하여 교차 검사할 수 있는가?
  
5. Right-BIC[E]P: 오류 조건을 강제로 일어나게 할 수 있는가?
   - 오류를 강제로 발생 시켜서 테스트를 진행한다.
   - 오류의 종류 혹은 환경적인 제약 사항 체크
      - 메모리가 가득 찰 때
      - 디스크 공간이 가득 찰 때
      - 서버와 클라이언트 간 시간이 달라서 발생하는 문제들
      - 네트워크 가용성 및 오류들
      - 시스템 로드
      - 제한된 색상 팔레트
      - 매우 높거나 낮은 비디오 해상도 

6. Right-BICE[P]: 성능 조건은 기준에 부합하는가?
   - 코드를 충분한 횟수만큼 실행해서 CPU 에 관한 이슈를 제거
   - 반복하는 코드 부분을 자바(JVM)가 최적화하지 못하는지 확인해야 한다
   - 성능을 테스트할 때는 사전 조건을 단단하게 정의해 놓아야 반복성과 재현성을 보장할 수 있다.
   - 테스트 도구: JMeter, JUnitPerf(단위 수준 성능 측정 시 사용하면 좋음)
