# 정규표현식 (RegExp)

정규식, Regular Expression

## 역활

- 문자 검색
- 문자 대체
- 문자 추출

## 테스트 사이트

https://regexr.com/

## 정규식 생성

```js
// 생성자
new RegExp("표현", "옵션");
new RegExp("[a-z]", "gi") /
  // 리터럴
  표현 /
  옵션 /
  [a - z] /
  gi;
```

## 영화 api

omdbapi.com/?apikey=7035c60c&s=frozen

## gi

- 생성자 방식
  g는 전체 i 대소문자 상관없이

```js
const str = `
010-2209-5651
daoclove@gmail.com
https://www.omdbapi.com/?apikey=7035c60c&s=frozen
The quick brown fox jumps over the lazy dog.
aabbccddd the
`;
const regexp = new RegExp("the", "gi");
console.log(str.match(regexp));
```

- 리터럴방식

```js
const regexp = /the/gi;
console.log(str.match(regexp));
```

## 메소드

| 메소드  | 문법                              | 설명                                                 |
| ------- | --------------------------------- | ---------------------------------------------------- |
| exec    | `정규식.exec(문자열)`             | 일치하는 하난의 정보 반환                            |
| test    | `정규식.test(문자열)`             | 일치여부 반환 (Boolean)                              |
| match   | `문자열.match(정규식)`            | 일치하는 문자열의 배열(Array)반환                    |
| replace | `문자열.replace(정규식,대체문자)` | 일치하는 문자열을 대체하고 대체된 문자열(srting)반환 |

```js
const regexp = /the/gi;
console.log(regexp.test(str));
//true
console.log(str.replace(regexp, "AAA"));
//AAA quick brown fox jumps over AAA lazy dog.
// aabbccddd AAA
```

## 플레그(옵션)

| 플레그 | 설명                                        |
| ------ | ------------------------------------------- |
| g      | 모든 문자 일치(global)                      |
| i      | 영어 대소문자를 구분 않고 일치(ignore case) |
| m      | 여러줄 일치(multi line)                     |

## 단축 .

```js
console.log(str.match(/the/gi));
console.log(str.match(/\.$/gim));
```

\ $ 문자로 인식

## 패턴(표현)

| 패턴    | 설명                              |
| ------- | --------------------------------- |
| ^ab     | 줄 시작에 있는 ab와 일치          |
| ab$     | 줄 끝에 있는 ab와 일치            |
| \.      | 임의의 한 문자와 일치             |
| a \| b  | a 또는 b와 일치                   |
| ab?     | b가 없거나 b와 일치               |
| {3}     | 3개 연속일치                      |
| {3,}    | 3개 이상 연속 일치                |
| {3,5}   | 3개이상 5개 이하(3~5개) 연속 일치 |
| [abc]   | a 또는 b 또는 c                   |
| [a-z]   | a부터 z소문자                     |
| [A-Z]   | A부터 Z 대문자                    |
| [0-9]   | 0부터 9사이                       |
| [가-힣] | 가부터 힣                         |
| \w      | 63개 문자에일치대소영문+숫자10 \_ |
| \b      | 63문자일치하지안는 문자           |
| \d      | 숫자에 일치                       |
| \s      | 공백 탭 일치                      |
| (?=)    | 앞쪽 일치                         |
| (?<=)   | 뒤쪽 일치                         |
