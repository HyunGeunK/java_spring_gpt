# java_spring_gpt

gpt 4o mini 사용법

필수 부분
model (문자열)
사용할 모델의 이름을 지정합니다.
예: "gpt-4o-mini"

messages (배열)
대화 히스토리를 나타내는 메시지 객체의 배열입니다.
각 메시지 객체는 다음 두 가지 필드를 포함해야 합니다:

role (문자열): "system", "user", 또는 "assistant" 중 하나
content (문자열): 메시지의 실제 내용

{
"model": "gpt-4o-mini",
"messages": [
{
"role": "user",
"content": "Hello, world!"
}
]
}

http://localhost:8080/api/v1/chatGpt/modelList		GET	사용 가능한 모델리스트를 조회합니다
http://localhost:8080/api/v1/chatGpt/model		GET	유효한 모델인지 확인합니다.
http://localhost:8080/api/v1/chatGpt/legacyPrompt	POST	레거시 모델(gpt-3.5-turbo-instruct, babbage-002, davinci-002)을 사용하여 프롬프트를 입력하고 결과값을 받습니다.
http://localhost:8080/api/v1/chatGpt/prompt		POST	새로운 모델(gpt-4, gpt-4 turbo, gpt-3.5-turbo)을 사용하여 프롬프트를 입력하여 결과값을 받습니다.

선택부분
max_tokens (정수)
생성할 최대 토큰 수를 지정합니다.
기본값은 모델에 따라 다릅니다.

temperature (부동 소수점, 0-2 사이)
출력의 무작위성을 제어합니다. 높을수록 더 창의적인 출력이 생성됩니다.
기본값은 일반적으로 1입니다.

top_p (부동 소수점, 0-1 사이)
핵심 샘플링이라고도 하며, 모델이 고려할 토큰의 확률 질량을 제어합니다.
기본값은 일반적으로 1입니다.

n (정수)
생성할 응답의 수를 지정합니다.
기본값은 1입니다.

stream (불리언)
응답을 스트리밍할지 여부를 지정합니다.
기본값은 false입니다.

stop (문자열 또는 문자열 배열)
생성을 중지할 시퀀스를 지정합니다.
기본값은 null입니다.