# lost-technology-2014

## 기본 정보
* 서비스명: 캐츠워즈(Catswords) - 자연어 처리기반 악성코드 분석 시스템
* 제출시기: 2014년 ~ 2016년 사이
* 제출처: 한국인터넷진흥원(KISA)

## 개발 내용
### 1. 제품/서비스 개요 및 기획 의도
#### 아이디어 및 개발하고자 하는 것이 무엇인가?
본 기술은 악성코드 분석 기술과 자연어 처리 기술을 결합시키는 새로운 악성코드 분석 방법론을 제시합니다. 프로그래밍 언어와 사람이 사용하는 자연어의 경계를 허물고 수많이 쏟아지는 악성코드의 의도를 파악하여 일정한 목적을 가지고 지속적으로 이루어지는 악성코드 공격의 경향성을 분석하고 대응하기를 원합니다. 제품이 본격적으로 상용화된다면 기계어나 프로그래밍 언어에 의존하지 않고 프로그램을 작성하는 ‘자연어 프로그래밍’ 분야의 신규 원천 특허를 빠르게 확보함은 물론 보안과 인공지능이 결합된 성공적인 예시가 될 것으로 기대하고 있습니다.

### 제품/서비스 개발을 통해 어떤 문제를 해결하고자 하는가?
사물인터넷의 활성화로 각 장치마다 사용되는 임베디드 운영체제는 물론 프로그래밍 언어와 중앙처리장치(CPU)의 플랫폼도 매우 다양해지고 있습니다. 일반 사용자에게도 익숙한 Windows나 Linux(Android) 말고도 현장에서는 X86, ARM, MIPS 등의 서로 다른 명령어 체계를 가진 CPU도 혼용되고 있습니다.

캐츠워즈(Catswords) 시스템이 기본적으로 세우는 가정은 운영체제가 달라도, 프로그래밍 언어가 달라도, CPU가 달라도 사이버 보안을 위협하는 공격 패러다임의 흐름은 동일하다는 것입니다. 하나의 기종에서 분석된 보안 위협이 서로 다른 기종과 환경의 보안 향상에도 도움이 될 수 있도록 공통의 의도를 찾아내는 것이 저희가 해결하고자 하는 문제이자 과제입니다.

### 왜 필요한가?
본 시스템이 필요한 이유는 임베디드 시스템의 성능이 점점 고도화되고 있다는 점입니다. 과거 임베디드 시스템이 한가지 목적만을 처리하기 위해 개발되고 운용되었다면, 현재는 임베디드 시스템도 일반 개인용 컴퓨터(PC)와 맞먹는 처리 내용과 처리량을 수행하고 있습니다.

이런 임베디드 시스템의 발전은 우리가 지금까지 일반 개인용 컴퓨터(PC) 시장에서 겪어왔던 보안 위협을 임베디드 시스템도 똑같이 따라가고 답습하게 될 수 있음을 의미합니다.

우리는 이제 기존 개인용 컴퓨터(PC) 시장에서 학습했던 보안위협 분석 사례와 대응 노하우를 버리는 것이 아닌 새로운 플랫폼에서도 유용하게 활용할 방법을 고민하게 되었고, 그 고민에 캐츠워즈(Catswords) 시스템은 답을 내리고자 합니다.

## 2. 주요 특징 및 핵심 기술
### 핵심 기능이 무엇인가?
악성코드를 포함한 모든 컴퓨터 프로그래밍의 결과물을 사람이 사용하는 자연어 코드를 바탕으로 분석하고 처리할 수 있도록 돕는 것이 핵심 기능입니다.

악성코드가 사용하는 API를 포함한 추출 가능한 리소스를 파악하고 각각의 상세 속성이 기술된 정의서를 바탕으로 자연어 코드로 변환하는 과정을 거칩니다.
변환된 자료는 행동의 분류와 분석에 활용될 수 있으며 이는 공격자의 장기적 의도(APT 공격 의도 등)를 효율적으로 판단하기 위해 활용됩니다.

아래는 소켓 프로그래밍 관련 내용을 자연어로 처리한 예시입니다. 해당 결과에서는 목표 소프트웨어가 소켓을 활용하여 진행하는 특정 행위를 자연어 수준에서 판단하는 자료가 됩니다.

#### <표 1> 자연어 프로그래밍의 관련 이미지 자료
* <그림 1> 소켓 프로그래밍 분석예시 - API 사전에 의한 자연어 코드 변환 및 행위판단의 예시
* <그림 2> 자연어 프로그래밍의 이해를 위한 예시 (Wolfram Alpha)

### 제품/서비스개발에 사용될 어떤 핵심 정보보호 기술을 활용하는가?
기본적으로 두 자료 간 유사성을 비교할 수 있는 알고리즘을 동원하여 만들어집니다. 이러한 알고리즘은 악성코드 분석에도 유효하기에 정보보호 기술은 물론 다양한 분야에서 활용되고 있습니다. 본 프로젝트에서는 악성코드의 유사도 분석을 위해 바이너리의 단순 비교가 아닌 4가지의 기반 분류(Text, Tree, Token, PDG)를 바탕으로 한 이루어진 유사도 비교 프로세스를 활용하고 있습니다.

### 무슨 장점을 갖고 있는가?
자연어 처리가 악성코드 분석 등의 바이너리 처리에 도입되면 나타나는 장점은 이기종에서 운영되는 프로그램만이 아닌 일반 문서와 사진, 영상 등과도 연관성을 가지는 자료를 도출 받을 수 있다는 점입니다. 자연어 처리를 통해 프로그래밍 언어로 이루어진 프로그램과 일반 문서(신문기사, 연구자료 등)와 사진, 영상과의 상관관계를 찾아내어 공격자의 장기적인 의도(APT 공격 등)의 파악을 더 효율적으로 진행함은 물론 공격자의 규모 파악에도 도움을 줄 것이라 기대하고 있습니다.

### 보유한 기술을 활용하여 제품/서비스를 개발할 수 있는 방법은 무엇인가?
보유한 기술을 활용하여 제품 및 서비스를 개발하는 절차는 본 프로젝트의 최종 목표 및 개발 내용 범위와도 같습니다. 사전에 활용 사례를 가진 여러 분석 라이브러리와 모듈을 통합(Integration)하는 과정을 통해 더 많은 정보를 취득하고, 취득된 리소스를 문장으로 사전화된 리소스 정의서를 바탕으로 변환하여 처리하게 됩니다.

### 최종 목표 및 개발 내용과 범위 (주요 성능 목표 제시)
  1. API 정의서를 보유한 150종 이상의 소프트웨어 개발 및 운용 환경에서 보안 위협을 분석하는 시스템으로 발전하는 것이 최종 목표.
  2. Data-Flow 기반의 분석 방법론을 도입하여 자연어 변환성능 향상
    * 정적 분석 시: PC에서의 JMP 계열 어셈블리 명령, 안드로이드의 DEX Invokation 추적
    * 동적 분석 시: 인텔社의 PIN(Desktop) / jUnit(안드로이드)
  3. 악성코드 API 및 리소스 빈도를 활용한 추천 리소스 기능 제공
  4. 악성코드 분석에 쓰일 수 있는 후보 시스템과의 결합성 테스트 및 검증
    * API 추천: PredictionIO, DeepDetect (설치형 머신러닝 플랫폼)
    * 가상환경 분석: VirtualBox, QEMU, Cuckoo Sandbox, ...
  - 바이너리: Valgrid, BitBlaze, DynamoRIO, PinTool, Snowman, ...
  - 안드로이드: Androguard, DroidBox, APKTool, JAD, ...
  - 외부 서비스: VirusTotal, MetaScan, URLQuery, ...

### 부족한 기술 또는 애로사항이 있는가? 만일 있다면 해결방법은 무엇인가?
현재 시스템 운용에 있어 아래의 건에 대해서는 모든 케이스에서 성공적으로 처리할 수 있도록 지속적인 성능 개선이 필요한 것으로 확인되고 있습니다.

####  API 감춤(Wrapping)과 가상 RISC 기술을 활용한 코드 은닉 우회방안
* API Wrapping(윈도우/안드로이드)
  기존의 API 외부 참조 방식이 아닌 호출부의 동적 라이브러리 코드를 실행파일에 직접 임베드하는 방식으로 정적 및 동적 분석을 회피. (대표 사례: PC에서의 Themida, 안드로이드 DEX Reflector 패킹 방식)

* 가상 RISC(Virtual RISC)
  소프트웨어적으로 구성된 예약 명령을 가진 별도의 RISC를 생성하여 분석가에게 노출되기 쉬운 연산 영역을 분석이 어려운 내부 RISC에서 처리 한 후 네이티브 환경에서는 연산 결과만 주고받아 분석가의 분석을 어렵게 함.

(가림)

### 아이디어의 우수성을 입증할 수 있는 내용(자유 기술)은 어떤 것이 있는가?
프로그래밍 언어를 자연어 처리 방법으로 처리하게 되면서 알고리즘의 변화에 따라 분석대상의 크기를 줄여나갈 수 있는 것이 특징입니다.
자연어 문서 요약(Summarization)에 활용되는 모든 알고리즘을 바이너리 분석에도 활용할 수 있으며 이는 분석하고자 하는 샘플의 분석 속도를 비약적으로 향상시키는 결과를 가져올 수 있습니다.
자연어 처리 기술을 도입하여 대용량의 윈도우 PE(Portable Execution)는 물론 안드로이드 APK(Android Application Package)의 분석 건을 처리함에 있어 리소스 사전(Dictionary)에 의해 생성된 자연어 문장을 매우 강하게 손실 압축하는 구조를 가지고 있습니다.
이렇게 추출된 어휘는 컴퓨터 프로그래밍 언어 뿐만이 아닌 일반 자연어 데이터와도 연결성을 가지게 되어 바이너리로부터 도출된 어휘로 관련 논문이나 사진 등을 탐색하는데 활용할 수 있습니다.

## 3. 시장 분석
### 타겟 시장의 규모(국내외), 주 타겟 이용층(B2B, B2C 등)은 누구인가?
본 시스템의 타겟 시장은 보안업체가 아닌 업무용 솔루션(ECM, ERP 등)을 개발하고 공급하는 업체입니다. 업무용 소프트웨어를 수출 또는 수입할 때 개발 회사가 겪는 어려움 중에 하나가 해당 지역이나 국가에서 사용되는 파일 형식을 처리하기 위해 추가적인 처리기(Parser) 개발을 고민해야 한다는 것입니다.
캐츠워즈(Catswords) 시스템의 특징은 단독 시스템으로는 자연어 처리를 통한 악성코드 분석기의 역할을 수행하지만, 외부 시스템과 연동되면 누구나 손쉽게 사용할 수 있는 처리기(Parser)가 됩니다.
소프트웨어 국제화를 계획하고 있거나 특정 단체에서만 활용되는 파일 형식의 처리를 필요로 하는 개인, 업체, 기관을 대상으로 제공될 수 있습니다.
  
### 누가 경쟁자이고 어떤 경쟁력을 갖고 있으며 어떻게 차별화 할 것 인가?
본 서비스의 경쟁자와 경쟁력을 정의하는데 있어 아래와 같은 두 가지 원칙을 세우고 있습니다. 첫째, 외국의 클라우드 보안 서비스의 사례를 봐라봐서는 우리나라에서의 비즈니스를 발굴 할 수 없다는 점. 둘째, 진정한 경쟁자는 보안업계 밖에서 찾아야 한다는 점입니다.

1. 클라우드 보안 서비스는 경쟁상대가 아니다.
기존의 클라우드 보안 서비스를 경쟁자로 삼아서 우리나라에서 비즈니스 타겟으로 잡을 수 있는 수요층을 명확하게 정의한다는 것은 불가능합니다. 이런 경쟁자들로는 우리나라에서의 비즈니즈를 정의함에 있어서 영감을 받을 수 있는 환경이 많이 부족하기 때문입니다. 단지 우리는 이런 서비스를 통해 방향을 배울 뿐입니다. 주로 바이러스 토탈, ThreatExpert, HerdProtect 등이 있습니다.

2. 진정한 경쟁자는 보안업계 밖에서 찾아야 한다.
저희는 데이터 사전 정제(Data Preparation) 솔루션 업체인 Paxata를 경쟁상대로 보고 있습니다. 현 시점은 연구를 통해 신규 알고리즘을 탄생시키는 것 보다는 기존에 연구된 알고리즘에 대한 동향을 파악하고 적재적소에 성공적으로 적용할 수 있는 제안을 하는 것이 더욱 중요해진 시대입니다.
실제로 데이터 분석에 있어 알고리즘보다 데이터 사전 정제(Data Preparation)가 상당히 긴 개발 소요 시간을 차지하고 있는 것으로 알려지고 있습니다. 시선을 달리하여 보면 수준 높은 사전 정제 기술만 확보하여도 사이버 보안 위협을 분석하는데 높은 경쟁력을 가질 수 있다는 뜻이 됩니다.

### 수익모델은 무엇인가?
  수익모델은 두 가지로 생각할 수 있습니다. 첫째, 단독으로 제공되는 경우 악성코드 분석기로서 사용자 요구에 맞는 다양한 과금 정책을 바탕으로 한 수익 구조를 창출합니다. 둘째, 다른 소프트웨어와 연동되어 제공되는 경우 보안 솔루션의 역할이 아닌 업무용 소프트웨어(ECM, ERP)를 위한 손쉬운 처리기(Parser) 기능을 제공하여 소프트웨어 수출 또는 수입 등으로 소프트웨어 국제화를 고려하는 업체가 수익 대상이 되어 트랜젝션 당 과금 정책이 적용될 것으로 전망됩니다.

## 4. 팀 구성
(가림)

## 5. 선발 이후 계획
### 최종 결과물
1. 외부 시스템에서 활용할 수 있도록 REST/(JSON/XML) 규격의 API 제공.
2. 분석 대상 악성코드의 행위와 의도에 연결되는 자연어 형식의 자료를 제시.
3. 분석 대상 악성코드의 개발 요점을 자동으로 정리 및 결과 출력.
4. 신규 분석결과와 기존 분석 결과와의 유사도 판단 결과 제공.
5. 오픈소스 ECM, ERP에 처리기(Parser)로 연결될 수 있는 플러그인 제공.

### 선발이후 계획
본 시스템은 전문지식 없이도 누구나 이용할 수 있는 전문가 시스템이라는 점을 표방하여 국내는 물론 해외에서도 동등한 서비스를 제공받을 수 있습니다. 
본 사업을 통해 자연어 처리 및 인공지능의 보안 업계 적용 사례가 많지 않다는 점을 극복하고 산업 현장과 연결되어 클라우드 기술을 적극 활용한 우수한 보안 서비스의 선례를 만들고 제공하고자 합니다. 일반 사용자에게는 기존 백신 한계 극복, 기업 사용자에게는 더욱 성공적인 보안 정책을 수립하는데 도움을 줄 수 있을 것이라 기대됩니다.
