+++
title = '2023 데이터 청년 캠퍼스'
date = 2023-09-07
featured_image = "https://images.unsplash.com/photo-1504711434969-e33886168f5c?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2670&q=80"
tags = ["AI", "Colab", "Python"]
+++

> 2023 데이터 청년 캠퍼스 경제/금융분야 페이크 뉴스 탐지 시스템 구축을 주제로

<br>

3학년 여름방학에 데이터와 코딩 관련 경험을 해보고자 과학기술정보통신부와 한국데이터산업진흥원에서 국내 대학교와 함께 운영하는 **2023 데이터 청년 캠퍼스**에 신청했다. 사실 그렇게 전공이라고 보기에 애매한 상황에서 붙을 수 있을까 고민했는데, 다행히 선발되어 상명대학교 데이터융합과정 (빅데이터 분석 기반 금융분야 비즈니스 인사이트 역량제고 과정)에 참여하게 되었다. 크게 4주 동안의 집체교육, 이후 6주 동안의 프로젝트 기간으로 구성되어있으며 집체교육 동안에는 파이썬 기초부터 ~ 딥러닝(...의 형상을 하고있는 무언가)를 공부하게된다.

우리 1분반 5조는 주제를 정하는 것에 가장 많은 시간을 쏟아부었다. 우리 모두 초심자였기 때문일까? 뭔가 있어보이고 멋있는걸 하고싶었다. 전기차 충전소 입지선정, 산불 위험 지역 분석 등등 다양한 주제가 제시되었지만 이미 공모전에 출품되거나 국가에서 개발해 사용하고 있었다. 특히 금융과정이다보니 금융과 동떨어진 주제를 금융과 억지로 엮는게 힘들었다. 어떤 주제를 골라야 금융과 연관성 있으면서, 그동안 배운 것을 써먹을 수 있을까 고민하던 우리는 **경제/금융분야 페이크 뉴스 탐지 시스템 구축**을 주제로 삼았다.

<br>

# 프로젝트 개요
### 가짜뉴스?
가짜뉴스의 확산은 디지털 시대의 정보 홍수와 더불어 더 큰 문제로 떠올랐다. 특히 17년 미국 대선에 가짜뉴스의 영향이 심심치 않게 작용하며 더욱 이목이 집중 되었다. 요즘 많은 사람들은 대부분의 뉴스, 그러니까 새로운 소식을 인터넷을 통해 접한다. 인터넷이라는 공간의 특성 상 뉴스의 생산속도가 사람들이 소비하는 속도보다 빠르며 가짜뉴스 또한 같은 맥락의 속성을 가지고 있다. 특히 금융/경제 분야의 가짜뉴스의 경우 단순히 거짓 정보를 전달하는 것을 넘어 사회적으로 심각한 악영향을 끼칠 수 있기 때문에 더욱 문제가 되고 있다. 대표적인 예로 미국 SVB 뱅크런 사태, 한국 OK 저축은행 PF 부실 논란이 있겠으며 이 외에도 수많은 금융/경제 분야의 가짜뉴스가 인터넷 상에서 유통되고 있다.

<br>

### 해외의 경우!
- 독일 : SNS에서의 법 집행 개선을 위한 네트워크 집행법(NetDG)
- 포르투갈 : 정부와 민간이 힘을 합쳐 가짜뉴스 퇴치 운동 및 기구 운영
- 미국 : 서비스 공급자의 자율 규제에 무게를 두며 민간 팩트체크 사이트 운영
- 프랑스 : 다양한 언론사와 구글의 주도로 팩트체크 기관 '크로스체크' 운영 중
- 한국 : 프랑스와 비슷하게 다양한 언론사와 서울대학교가 함께 팩트체크 아카이브 운영 중

위 사례에서 독일은 특이하게 실제 법안을 입법해 운용하고 있는데 운용 과정에서 표현의 자유와 가짜뉴스 검열 사이의 첨예한 의견 대립이 이어지고 있다. 한국은 17년 이후로 다양한 입법 시도가 있었으나 통과까지 이어지지 못했다.
결국 이러한 법적인 제약을 넘어 가짜뉴스와 맞서기 위해서는 결국 (어쩔 수 없게도) 사회 구성원 개인의 노력이 필요하다. 그렇기에 최근 어디서든 시민들의 미디어 리터러시 능력 향상이 중요 이슈로 떠오르는 것!
그러나 일반 사용자가 뉴스를 보며 매번 논문과 추가 자료를 찾아보며 교차검증하기에는 물리적으로 시간이 부족하다. 그렇다고 해서 사용자가 뉴스를 읽을 때마다 "이 뉴스는 과연 진짜일까?"라고 걱정한다면 아마 그 피로는 상당할 것이다. 따라서 가짜뉴스 데이터를 학습시켜서 어느 정도 걸러낼 수 있는 인공지능 모델을 만든다면, 사용자가 정보를 접할 때 1차 거름망 역할을 해줄 수 있지 않을까.

<br>

# 연구방법
![연구 방법](/images/Data_on_air/01.png)
우리가 개발한 모델은 기준으로 서울대학교 언론정보연구소의 팩트체크 정보를 활용한다.
가짜뉴스의 정의와 판별 기준은 여전히 논의 중이며, 놀랍게도 이는 각 개인 또는 그들이 속한 집단의 입장에 따라 달라질 수 있다...! 어른들의 사정이란... 따라서 우리는 서울대학교 팩트체크 사이트에서 주제별로 라벨링 된 기준을 채택하여 모델을 훈련하기로 했다. 우리의 모델은 이러한 팩트체크 기준을 활용하여 Naver 기사와 YouTube 영상 스크립트에 대한 준 지도 학습... factcheck에서는 이미 라벨이 붙어 있지만 Naver와 YouTube에는 라벨이 붙어 있지 않다는 점과 그 비율이 균일하지 않다는 점을 고려해 준 지도 학습을 진행했다. 우리의 목표는 한국언론진흥재단의 자료를 기반으로 한 온라인 뉴스 중에서 매주 가장 많이 이용되는 Naver 뉴스 YouTube를 활용하여 모델을 향상하는 것이다. 이를 통해 모델의 실제 성능과 범용성을 향상할 것이다.

<br>

# 프레임워크
![프레임워크](/images/Data_on_air/frame.png)

<br>

# 모델링_01 : SNU 언론정보연구소 데이터 활용
### 데이터 수집 및 확인

![데이터 수집 및 확인](/images/Data_on_air/02.png)

우리는 팩트체크에서 총 790개의 데이터를 수집했다. 이때 row_id에 인덱스를 / 내용에 기사, 영상제목을 / 상세내용에 기사내용, 영상 스크립트를 / 주장검증매체에 언론사, 채널 명을 / label에 SNU 언론정보연구소 라벨링 정보를 가져왔다. 선행연구를 참조해 판단유보를 제외하고 False와 True를 구분했다.

<br>

### 라벨링 인덱스
![라벨링 인덱스](/images/Data_on_air/03.png)
선행연구를 참조해 판단유보를 제외하고 False와 True를 구분했다.

<br>

### 워드클라우드
![워드클라우드](/images/Data_on_air/04.png)
위 그래픽은 수집한 로우데이터의 상세 내용을 시각화한 것으로 왼쪽 붉은색이 False, 오른쪽 푸른색이 True로 라벨링된 텍스트의 워드클라우드이다. 보면 생각보다 비슷한 단어들이 많고 의미없이 반복되는 단어들이 많은 것을 알 수 있는데, 이를 통해서 데이터 전처리 진행에 대한 틀을 잡고 더 나아가 불용어 사전 구축에도 아이디어를 얻을 수 있었다!

<br>

### 데이터 전처리
![데이터 전처리](/images/Data_on_air/05.png)
판단유보를 제외한 총 760개 데이터를 대상으로 맞춤법 검사 / 불용어 제거(사전 수동 구축) / 토픽모델링(중복 주제 그룹화) / 오버샘플링(T/F 비율 1:1) 순서로 전처리를 진행했다. 최종적으로 760개의 데이터를 전처리 후 모델 훈련용 544개, 검증용 데이터 136개로 구분 지었다.

<br>

### 모델링
![모델링](/images/Data_on_air/06.png)
Word2Vec 벡터화된 데이터를 양방향 LSTM (BiLSTM) 모델에 적용하여 실험을 진행했다. 초기에는 일반 LSTM을 사용하여 모델을 구성했으나, 검증 결과의 성능이 예상보다 낮아서 모델을 변경해야 할지에 대한 고민을 했다. 그런데, 더 다양한 연구와 논문 서칭을 통해 LSTM보다 성능이 우수한 BiLSTM 모델을 발견했다. 이 모델은 문맥을 양방향으로 고려하는 데에 있어서 우수한 성과를 보이며, 특히 문맥 기반의 연관성 분석에 유리한 모델이다. 따라서 BiLSTM 모델을 채택하고 적용한 결과, 성능에서 유의미한 개선이 이루어졌다.

<br>

# 모델링_02 : Naver / Youtube 데이터 활용

### 데이터 수집 및 확인

![데이터 수집 및 확인](/images/Data_on_air/07.png)

모델링_01 과정을 통해 훈련시킨 모델에 네이버 뉴스 기사와 유튜브 스크립트 데이터를 넣고 준지도 학습을 시행했다. SNU 펙트체크에서 스크래핑한 760개의 데이터(판단유보 제외)에서 각각 키워드를 3개씩 선정했다. 그리고 해당 키워드를 네이버와 유튜브에 입력해 각각 관련도 / 조회수 순으로 스크래핑했다.

<br>

### 데이터 전처리
![데이터 전처리](/images/Data_on_air/08.png)

<br>

### 모델링
![데이터 수집 및 확인](/images/Data_on_air/09.png)
기존 SNU 데이터 뿐만이 아니라  Naver, Youtube 데이터까지 함께 입력되었을 때 모델 평가지표의 변화를 염두하여 이를 최대한 방지하고자 다양한 파라미터를 조절해가며 최적의 결과를 얻기 위해 노력했다. 최소 100번이 넘는 수동... 조정 과정을 통해 F-1 스코어와 정확도가 함께 60% 이상인 경향을 보이는 파라미터를 찾을 수 있었다.

<br>

# 개선방안

### Checkonomy
![Checknomy](/images/Data_on_air/10.png)
우리가 만든 모델을 가지고 어떻게 활용할 수 있을까 봐 청사진을 멋지게 그려보았을 때 가장 먼저 생각난 것은 다른 서비스로 확장성이었다. 그 첫번째로 웹사이트 구축! 온라인 뉴스의 이용률이 증가하고 있는 만큼, 접근성 측면에서 가장 뛰어나다고 생각했던 웹페이지 형식으로 가짜뉴스 탐지 서비스를 제공하면 좋겠다는 아이디어가 나왔고 이에 Checknomy라는 이름의 웹사이트를 제작했다! 사실 아직 모델과 미 연동된 상태로 기능별 구역 구분만 되어있지만, 코딩과 접점이 전혀 없는 조원들이 만들어 낸 결과물이라 너무 대단했고, 멋있다고 생각했다. 이번 프로그램에서 가장 많이 배운 것은 뭐든지 깨부하면서 하면 되는구나... 였다.
{{<alert>}}
<a href="https://64ed9d4d8e967a2a277e2d9d--stellular-sundae-f4c52b.netlify.app/">Checkonomy 구경하기</a>
{{</alert>}}

<br>

### Chrome 확장 프로그램
![Chrome 확장 프로그램](/images/Data_on_air/11.png)
두 번째 활용방안은 크롬 확장프로그램이다. 체코노미 사이트에 직접 접속하지 않아도 크롬 브라우저에서 우리 모델을 사용해 현재 읽고 있는 기사를 검증하는 확장 프로그램으로 사용할 수 있지 않을까? 하는 의견에서 나온 아이디어이다. 사용자는 기사를 읽다가 상위 툴 팁이 뜨면 지금 읽고 있는 기사의 대략적인 검증이 가능하며, 더 알아보고 싶은 경우 아래 버튼을 눌러 체코노미 사이트로 이동해 상세 내용을 볼 수 있다.

<br>

# 결론

### 프로젝트를 마치고
방학 동안 4주 동안의 교육과 6주 동안의 프로젝트를 통해 시간을 알차게 보냈지만, 생각해 보면 그동안의 노력에 비해 얻은 것이 적은 것 같기도 하다.

먼저, 이 프로젝트를 진행하면서 많은 부분을 '0'부터 시작해야 했고, 중간마다 생긴 문제나 질문을 해결할 방법이 부족했다. 물론 현업자 멘토링과 교수님의 멘토링이 있었지만, 더 자세한 조언과 첨삭이 필요한 순간에는 부족한 부분이 있었다. 또한 초심자의 욕심으로 인해 더 좋아 보이는, 더 멋있어 보이는 주제를 선정하는 것에 시간이 오래 걸렸고 덕분에 주제의 난이도가 급상승한 감도 없지 않아 있다.

게다가, 프로젝트를 진행하면서 딥러닝을 전공한 조원이 개인 사정으로 중도 포기했고, 나머지 팀원 중에는 코딩 경험이 없는 사람이 대다수인 상황에서 조장이 되었다. 이런 상황에서 모두가 프로젝트를 어떻게 진행해야 할지 막막해하고 있었으나 정말 다행히도 유사 프로젝트를 진행한 경험이 있는 컴퓨터공학 조원이 있어 조금씩 밀림을 헤쳐 나갈 수 있었다.

모델을 다루는 과정에서도 어려움을 겪었다. 한국어 처리에 강력한 모델인 KoBERT를 사용하려 했으나 패키지 버전 충돌 문제로 설치에 어려움을 겪었으며 결국 KoBERT가 아닌 BiLSTM 모델을 사용해 과제를 수행했다. KoBERT를 설치 문제로 사용하지 못한 것이 너무 아쉬워 과제와 별개로 계속 설치를 시도했는데 결국 프로젝트 마감 하루 전에 버전 충돌 이슈를 해결했다. 물론 우리 과제가 KoBERT를 사용하더라도 큰 변화가 있을지는 확신하지 못하겠지만 시도조차 하지 못했던 것은 아주 아쉬웠다.

또한, 모델에 대한 이해도가 낮았던 점도 어려움 중 하나였다. 다른 조원의 코드를 이해하는 것만으로도 어려움을 겪었으며, 파라미터를 조정하면서 모델을 훈련하기는 했지만, 해당 파라미터가 의미하는 바를 정말 구체적으로 파고들어 이해한 상태에서 사용하지 못했다.

그러나 이 경험을 통해 자연어 처리 과정에 대한 기본적인 이해를 얻었으며, 데이터 수집, 전처리, 임베딩, 모델 훈련 등의 다양한 단계를 공부할 수 있었다. 또한, 다양한 딥러닝 모델에 대한 지식도 쌓을 수 있었다. 이러한 경험들은 미래에 비슷한 프로젝트나 업무를 수행할 때 분명 도움이 되지 않을까.

<br>

### 그 이후
프로젝트를 수행하는 과정에서 분명 여러 가지를 배웠지만, 이를 끝으로 아무것도 하지 않는다면 말짱 도루묵이 될 것이다. 따라서 이번 방학에 공부하고 배운 것을 잊지 않고 정말 머릿속에 집어넣으려면 추가로 개인 프로젝트를 진행해야만 할 것 같다...! 이제 KoBERT 설치 이슈가 어느 정도 해결되었으므로, 더 많은 실험과 결과를 확인할 수 있게 되었다. 개인 프로젝트에서는 단일 모델의 파라미터를 변화시키는 것뿐만 아니라 다양한 모델의 종합적인 결과를 비교함으로써 모델 간의 우위를 평가할 예정이다.

비록 이번 프로젝트에서 모든 것을 완벽히 마스터하지는 못했지만, 2달 동안 많은 것을 배우고 경험한 것을 느끼며, 특히 팀원들과의 협력 과정에서 많은 것을 얻었다. 모르는 분야에서 팀원들과 함께 여러가지를 도전한 경험이 뜻깊었고, 이를 통해 많은 것을 배울 수 있었다! 이러한 경험을 헛되게 두지 않기 위해 추가적인 개인 프로젝트를 진행해보고 싶다. 물론 일단 바쁜게 끝난 다음에...

전반적인 프로그래밍에 힘써준 피쌤과, 발표자료부터 전처리~모델링 과정에서 힘써준 조쌤, 전처리~웹사이트 구축에 힘써준 박쌤1-유쌤, 자료 스크래핑에 힘써준 박쌤2 다들 고생 많았고 이제 복학해서 성불하세요 :\)

{{<alert>}}
<a href="https://elecbrandy.github.io/">>> Elecbrandy.github.io >></a>
{{</alert>}}