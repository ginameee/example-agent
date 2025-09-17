# AI Agent 란?

- LLM + 특정 목적을 수행할 수 있는 도구/권한 (브라우저 조작, 파일 시스템 접근, 코드의 실행 등)
- LLM을 기반으로 특정한 목적을 수행하는 시스템을 의미

## 구현하는 방식

1. LLM 에게 내가 제공하려는 서비스 목록을 알려준다.

```
I have the follwing functions in my system

`get_weather`
`get_currency`
`get_news`

All of them receive the name of a country as an arguemnt (i.e get_news('Spain'))
Please answer with the mane of the function taht you would like me ot run
please say nothing else, just the name of the function with the arguments.
```

2. LLM은 저 PROMPT 를 기반으로 사용자의 질문를 이해하고 실제로 호출해야하는 함수가 무엇인지를 답변해준다.

```
Answer the follwing question:
What is the weater in Greece?

get_weather('Greece')
```

3. 각 함수의 구현체를 개발자가 직접 만들고, 응답값을 받아온다.

4. 받아온 응답값을 LLM에게 전달하여 응답에 사용해달라고 프롬프팅한다.
