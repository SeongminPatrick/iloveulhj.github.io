---
layout: post
title:  "[SQL] 데이터 모델링의 이해"
date:   2015-05-10 00:00:00
categories: posts sql
---

이 포스트는 "SQL 전문가 가이드"의 "1장. 데이터 모델링의 이해"를 학습한 내용으로 이루어져 있습니다. 

---

# 모델링

현실세계를 추상화, 단순화, 명확화하기 위해 일정한 표기법에 의해 표현하는 기법이다. 
모델링은 `데이터`, `프로세스`, `데이터&프로세스` 관점으로 구분하여 설명할 수 있다.

# 데이터 모델링이란?

- 정보시스템을 구축하기 위한 데이터관점의 업무 분석 기법
- 현실세계의 데이터에 대해 약속된 표기법에 의해 표현하는 과정
- 데이터베이스를 구축하기 위한 분석/설계의 과정

# 데이터 모델링의 기능

- 시스템을 현재 또는 원하는 모습으로 가시화하도록 도와준다.
- 시스템의 구조와 행동을 명세화 할 수 있게 한다.
- 시스템을 구축하는 구조화된 틀을 제공한다.
- 시스템을 구축하는 과정에서 결정한 것을 문서화한다.
- 다양한 영역에 집중하기 위해 다른 영역의 세부 사항은 숨기는 다양한 관점을 제공한다.
- 특정 목표에 따라 구체화된 상세 수준의 표현방법을 제공한다.

# 데이터 모델링의 중요성 및 유의점

**파급효과(Leverage)**  
시스템 구축 중의 데이터 구조 변경작업은 전체 시스템 구축 프로젝트에서 큰 위험 요소가 될 수 있다.

**간결한 표현(Conciseness)**  
데이터 모델은 시스템의 정보 요구사항과 한계를 간결하게 표현할 수 있는 도구이다.

**데이터 품질(Data Quality)**  
데이터 품질의 문제는 초기에는 발견되지 않고, 오랜 기간 축적된 데이터를 전략적으로 활용하려는 시점에 발견된다. 
데이터 구조 때문에 발생한 데이터 품질의 문제는 복구할 수 없는 경우가 많다. 
때문에 데이터 모델링을 할 때는 `중복(Dupliocation)`, `비유연성(Inflexibility)`, `비일관성(Inconsistency)`에 유의하도록 하자. 

# 데이터 모델링의 3단계 진행

| 데이터 모델링 | 내용 | 
|:-:|:-:|
| 개념적 데이터 모델링 | 추상화 수준이 높고 업무중심적이고 포괄적인 수준의 모델링 진행. 전사적 데이터 모델링, EA수립시 많이 이용 |
| 논리적 데이터 모델링 | 시스템으로 구축하고자 하는 업무에 대해 Key, 속성, 관계 등을 정확하게 표현, 재사용성이 높음 | 
| 물리적 데이터 모델링 | 실제로 데이터베이스에 이식할 수 있도록 성능, 저장 등 물리적인 성격을 고려하여 설계 | 

# 데이터 모델링의 세가지 개념

- `Things`: 업무가 관여하는 어떤 것
- `Attributes`: 어떤 것이 가지는 성격
- `Relationships`: 업무가 관여하는 어떤 것 간의 관계

# 좋은 데이터 모델의 요소

**완전성(Completeness)**  
업무에서 필요로 하는 모든 데이터가 데이터 모델에 정의되어 있어야 한다.

**중복배제(Non-Redundancy)**  
하나의 데이터베이스 내에 동일한 사실은 반드시 한 번만 기록하여야 한다.

**업무규칙(Business Rules)**  
데이터 모델링 과정에서 도출되고 규명되는 수많은 업무규칙을 데이터 모델에 표현하고 이를 데이터 모델을 활용하는 모든 사용자가 공유할 수 있도록 제공해야 한다.

**데이터 재사용(Data Reusability)**  
데이터는 통합 모델로서 어플리케이션에 대해 독립적으로 설계되어야 재사용성을 향상시킬 수 있다. 
정보시스템을 구축하는 과정에서 데이터 구조의 확장성, 유연성에 많은 노력을 기울여야 한다. 
전체 정보 시스템의 안정성, 확장성을 좌우하는 가장 중요한 요소는 데이터 관점의 통합이다.

**의사소통(Communication)**  
데이터 모델은 대상으로 하는 업무를 데이터 관점에서 분석하고 이를 설계하여 나오는 최종 산출물이다. 
데이터를 분석과정에서는 자연스럽게 많은 업무 규칙들이 도출된다. 
이 과정에서 도출되는 많은 업무 규칙들은 데이터 모델에 엔티티, 서브타입, 속성, 관계 등의 형태로 자세하게 표현되어야 한다. 
데이터 모델은 관련자들이 설계자가 정의한 업무 규칙들을 동일한 의미로 받아들이고 정보시스템을 활용할 수 있게하는 역할을 할 수 있다.

**통합성(Integration)**  
기업들이 이전에는 개별 업무별로의 단위 정보시스템을 구축하여오곤 하였다. 
그래서 동일한 성격의 데이터임에도 불구하고 전체 조직관점에서 보면 여러곳에 동일한 데이터가 존재하기 마련이다. 
바람직한 데이터의 구조는 돌일한 데이터는 전체 조직 차원에서 한번만 정의되고, 이를 여러 다른 영역에서 참조, 활용하는 것이다.

---

# 엔티티(Entity)란?

- 사람, 장소, 물건, 사건, 개념등의 명사에 해당한다.
- 업무상 관리가 필요한 관심사에 해당한다.
- 저장이 되기 위한 어떤 것(Thing)이다.

# 엔티티의 특징

- 업무에서 필요로 하는 정보여야 한다.
- 식별이 가능해야 한다.
- 인스턴스들의 집합이여야 한다.
- 업무 프로세스가 엔티티를 이용해야 한다.
- 속성을 포함해야 한다.
- 다른 엔티티와 관계가 존재해야 한다.

# 엔티티의 명명

- 현업에서 사용하는 용어를 사용한다.
- 약어를 사용하지 않는다.
- 단수 명사를 사용한다.
- 모든 엔티티에서 유일한 이름을 가져야 한다.
- 엔티티 생성 목적에 맞는 이름을 명명한다.

---

# 속성(Attribute)이란?

업무에서 필요로 하는 인스턴스에서 관리하고자 하는 의미상 분리되지 않는 최소의 데이터 단위이다.

# 속성의 특징

- 해당 업무에서 필요하고 관리하고자 하는 정보이다.
- 정규화 이론에 근간하여 정해진 주식별자에 함수적 종속성을 가져야 한다.
- 하나의 속성에는 한 개의 값만을 가진다.

# 도메인

엔티티 내에서 속성에 대한 데이터타입과 크기 그리고 제약사항을 지정하는 것이다.

# 속성의 명명

- 해당업무에서 사용하는 이름을 쓴다.
- 서술식 속성명은 사용하지 않는다.
- 약어사용은 가급적 제한한다.
- 전체 데이터 모델에서 유일해야 한다.

---

# 관계(Relationship)란?

엔티티의 인스턴스 사이의 논리적인 연관성으로서 존재의 형태로서나 행위로서 서로에게 연관성이 부여된 상태를 의미한다.

# 관계의 3가지 개념

**관계명(Membership)**  
관계명은 엔티티가 참여하는 형태를 지칭한다. 
각각의 관계는 두 개의 관계명을 가지고 있다. 
또한 각각의 관계명에 의해 두가지 관점으로 표현될 수 있다. 
관계명은 애매한 동사를 피하고, 현재형으로 표현한다.

**관계차수(Degree/Cardinality)**  
두 개의 엔티티간 관계에서 참여자의 수를 표현하는 것을 관계차수(Cardinality)라고 한다. 
가장 일반적인 관계차수 표현방법은 1:M, 1:1, M:N이다.

**관계선택사양(Optionality)**  
관계에 참여하는 엔티티가 항상 참여하는지 아니면 참여할 수도 있는지를 나타내는 방법이 필수(Mandatory Membership)과 선택 참여(Optional Membership)이다. 
선택참여된 항목은 물리속성에서 Foreign Key로 연결된 경우 Nullable이 되어야 한다.


---

# 식별자(Identifiers)란?

식별자란 하나의 엔티티에 구성되어 있는 여러개의 속성 중에 엔티티를 대표할 수 있는 속성을 의미하며 하나의 엔티티는 반드시 하나의 유일한 식별자가 존재해야 한다. 
보통 식별자는 업무적으로 구분이 되는 정보로 생각할 수 있으므로 논리 데이터 모델링 단계에서 사용하고, 키는 데이터베이스 테이블에 접근을 위한 매개체로서 물리 데이터 모델링 단계에서 사용한다.

# 식별자의 특징

- 주식별자에 의해 엔티티 내에 모든 인스턴스들이 유일하게 구분되어야 한다.
- 주식별자를 구성하는 속성의 수는 유일성을 만족하는 최소의 수가 되어야 한다.
- 지정된 주식별자의 값은 자주 변하지 않는 것이어야하 한다.
- 주식별자가 지정이 되면 반드시 값이 들어와야 한다.

# 주식별자 도출 기준

- 해당 업무에서 자주 이용되는 속성을 주식별자로 지정하도록 함
- 명칭, 내역 등과 같이 이름으로 기술되는 것은 피함
- 속성의 수가 많아지지 않도록 함

# 외부 식별자: 식별자관계와 비식별자관계에 따른 식별자

**식별자 관계**  
부모로부터 받은 식별자를 자식엔티티의 주식별자로 이용하는 경우는 Null값이 오면 안되므로 반드시 부모 엔티티가 생성되어야 자기 자신의 엔티티가 생성되는 경우이다. 
부모로부터 받은 속성을 자식엔티티가 모두 사용하고 그것만으로 주식별자를 사용한다면 1:1의 관계가 된다. 
만약 부모로부터 받은 속성을 포함하여 다른 부모 엔티티에서 받은 속성을 포함하거나 스스로 가지고 있는 속성과 함께 주식별자로 구성하는 경우는 1:M 관계가 된다.

**비식별자 관계**  
부모 엔티티로부터 속성을 받았지만 자식엔티티의 주식별자로 사용하지 않고 일반적인 속성으로만 사용하는 경우가 있다. 
이와 같은 경우를 비식별자 관계(Non-Identifying Relationship)이라고 한다.
비식별자 관계는 다음과 같은 경우 발생한다.

- 자식 엔티티에서 받은 속성이 반드시필수가 아니어도 무방하기 때문에 부모 없는 자식이 생성될 수 있는 경우
- 엔티티별로 데이터의 생명주기를 다르게 관리할 경우
- 여러 개의 엔티티가 하나의 엔티티로 통합되어 표현되었는데 각각의 엔티티가 별도의 관계를 가질 때
- 자식엔티티에 주식별자로 사용하여도 되지만 자식 엔티티에서 별도의 주식별자를 생성하는 것이 더 유리하다고 판단될 때

**식별자와 비식별자 관계 비교**

| 항목 | 식별자 관계 | 비식별자 관계 | 
| :-: | :- | :- |
| 목적 | 강한 연결관계 표현 | 약한 연결관계 표현 |
| 자식 주식별자 영향 | 자식 주식별자의 구성에 포함됨 | 자식 일반 속성에 포함됨 |
| 표기법 | 실선 표현 | 점선 표현 | 
| 고려 사항 | - 반드시 부모 엔티티에 종속<br> - 자식 주식별자구성에 부모 주식별자 포함 필요<br> - 상속받은 주식별자속성을 타 엔티티에 이전 필요  | - 약한 종속관계<br> - 자식 주식별자구성을 독립적으로 구성<br> - 자식 주식별자구성에 부모 주식별자 부분 필요<br> - 상속받은 주식별자속성을 타 엔티티에 차단 필요<br> - 부모쪽의 관계참여가 선택관계 |

---

출처: `"SQL 전문가 가이드, 2013 Edition", 서강수, 한국데이터베이스진흥원, 2013` 
