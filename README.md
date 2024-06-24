# NKIA-LLM

## 1. Manual RAG

### 문제정의
1. 제품의 사용자가 제품의 메뉴얼에 대한 질문을 할 수 있다.
2. 메뉴얼은 제목, 소제목의 계층적 구조로 되어있고, html파일로 되어있다.
3. 메뉴얼은 복잡한 표가 많다.

### 해결방안
1. 사용자의 질문의 뉘양스가 애매할 수 있으니 multi query retriever를 사용. 하지만, 질문이 여러개이면 검색되는 문서도 여러개일 수 있으므로 LLM을 통해 검색된 문서가 답변에 필요한 문서인지 판단함.
2. 문서는 계층적 구조의 특징을 갖기 때문에 제목, 소제목을 기준으로 부모 문서를 정의하고, 검색된 문서의 부모 문서까지 프롬프트로 사용.
3. 표는 마크다운으로 변환한다.

<img width="700" alt="Screenshot 2024-06-23 at 3 12 51 PM" src="https://github.com/Youngdong2/NKIA-LLM/assets/48584373/abc405a8-4ea9-4f7a-ac85-7759382574d2">

## 2. MongoDB Query Agent

### 문제정의
1. 자사 제품의 데이터 조회를 하기 위해서는 제품의 DB인 MongoDB의 query문을 생성하는 LLM이 필요하다.
  - 예를 들어 사용자가 "CPU사용률이 가장 높았던 서버 알려줘"라는 질문에 대응하기 위해서 DB 조회가 필요함.
<img width="1894" alt="스크린샷 2024-06-24 오후 9 04 01" src="https://github.com/Youngdong2/NKIA-LLM/assets/48584373/6fda7c4f-5243-482f-95d5-3b5cc74d6a67">
