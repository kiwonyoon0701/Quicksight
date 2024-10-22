**Amazon Web Services**

**Table of Contents**

## 

[개요... 3](#_Toc38957839)

[데이터 이해.. 3](#_Toc38957840)

[신속하고 손쉬운 비즈니스 분석을 위한 QuickSight 시작.. 4](#_Toc38957841)

[데이터 세트 준비.. 6](#_Toc38957842)

[핵심성능지표(KPI)로 전년 대비 매출 시각화.. 15](#_Toc38957843)

[월간 판매 동향 시각화.. 18](#_Toc38957844)

[막대 차트의 드릴 업/다운 기능.. 18](#_Toc38957845)

[목표 대비 성과 시각화.. 20](#_Toc38957846)

[카테고리별 총 매출의 % 시각화.. 22](#_Toc38957847)

[카테고리별 분석을 위한 트리맵... 23](#_Toc38957848)

[분포와 관계 분석을 위한 산점도... 24](#_Toc38957849)

[막대 콤보 차트... 24](#_Toc38957850)

[파라미터 및 컨트롤을 사용한 필터링... 25](#_Toc38957851)

[세부사항 시트 추가 및 드릴 다운.. 29](#_Toc38957852)

[계산된 필드를 사용한 전년 대비 매출 차이... 33](#_Toc38957853)

[계산된 필드를 사용한4주 이동 평균 비교.. 34](#_Toc38957854)

[ML기반 예측.. 36](#_Toc38957855)

[ML기반 예측.. 36](#_Toc38957856)

[ML기반 가정 분석.. 37](#_Toc38957857)

[인사이트 추가... 37](#_Toc38957858)

[ML 기반 이상 탐지.. 39](#_Toc38957859)

[제안된 인사이트에서 ML 기반 예측과 자동 설명 추가... 44](#_Toc38957860)

[만들어진 대시보드의 모습... 46](#_Toc38957861)

[대시보드 공유를 위한 사용자 초대.. 47](#_Toc38957862)

[대시보드 공유를 위한 사용자 초대.. 49](#_Toc38957863)

[QuickSight 모바일 앱... 51](#_Toc38957864)

 

---

## 개요

 

Amazon QuickSight는 조직 내 모든 구성원에게 통찰력을 손쉽게 제공할 수 있게 지원하는 빠른 클라우드 기반 비즈니스 인텔리전스 서비스입니다. 완전관리형 서비스인 QuickSight를 사용하면 ML Insights가 포함된 대화형 대시보드를 손쉽게 생성 및 게시할 수 있습니다. 대시보드는 어떤 디바이스에서든 액세스할 수 있는 것은 물론, 애플리케이션, 포털, 웹 사이트에 임베딩할 수도 있습니다. 

 

본 Lab에서는 데이터 연결, 시각적 객체 구성, 대화형 디자인과 ML 활용과 대시보드 공유 등을 학습하여 데이터 분석가(Analyst)와 BI 엔지니어가 QuickSight를 사용하는 방법을 안내합니다.

 

본 Lab은 아래의 내용을 포함하고 있습니다.

 

·   데이터 연결하기(파일 업로드)

·   데이터 세트와 대시보드 이해

·   다양한 유형의 데이터 시각화

·   계산된 필드와 드릴 다운/업 사용

·   필터 적용과 화면 컨트롤

·   ML 인사이트

·   대시보드 공유와 모바일 앱

## 

---

## 데이터 이해

 

본Lab에서 사용될 데이터는 가상의 리테일 판매 데이터로 아래와 같은 형식의 데이터입니다.

 

| 컬럼명       | 컬럼  내용    | 데이터  유형 | 컬럼명       | 컬럼  내용    | 데이터  유형 |
| ------------ | ------------- | ------------ | ------------ | ------------- | ------------ |
| ordereid     | 주문ID        | STRING       | orderdate    | 주문일자      | DATE         |
| customerid   | 주문자ID      | STRING       | shipdate     | 배송일자      | DATE         |
| customertype | 주문자 유형   | STRING       | customername | 주문자명      | STRING       |
| city         | 도시명        | STRING       | country      | 국가명        | STRING       |
| postcode     | 우편번호      | STRING       | state        | 주명          | STRING       |
| productid    | 제품ID        | STRING       | regiontype   | 지역유형      | STRING       |
| subcategory  | 하위 카테고리 | STRING       | bigcategory  | 상위 카테고리 | STRING       |
| price        | 가격          | DECIMAL      | productname  | 제품명        | STRING       |
| discount     | 할인률        | DECIMAL      | quantity     | 수량          | INTEGER      |



**retail-dataset.csv** : [retail-dataset.csv](retail-dataset.csv) 

**Quicksight Manifest** : [manifest.json](manifest.json) 



---

## 신속하고 손쉬운 비즈니스 분석을 위한 QuickSight 시작

 

1. **AWS** **관리 콘솔** 의 **서비스 찾기** 에서 **QuickSight** 를 입력한 후 **QuickSight** 로 이동합니다.

![image-20220606152512787](images/image-20220606152512787.png)

\2.   **QuickSight**를 처음 사용하는 경우 **Sign up** (가입)을 통해 사용할 환경을 생성합니다.

 

\3.   **ML** **인사이트** 나 **이메일 보고서 전송** 등 QuickSight의 다양한 기능을 사용하기 위해서 **Enterprise Edition**을 선택합니다.

 

\4.   아래의 **QuickSight****계정 생성** 페이지에서 **QuickSight** **리전** 을 **Asia Pacific(Seoul)**로 지정하고 **QuickSight** **계정 이름**, **알림 이메일 주소** 등을 입력하고 **완료** 하면 가입이 완료됩니다.

 

\5.   **Amazon QuickSight****로 이동** 버튼을 클릭하여 QuickSight로 이동합니다.

 

 

 

## 데이터 세트 준비

 

**Option2****로 진행하세요****!**

**Option 1: S3** **매니페스트 파일 사용**

 

\1.   데이터 세트를 생성을 위해 아래의 초기화면에서 **데이터 관리** 로 이동합니다.

 

\2.   데이터 관리 페이지에서 새 데이터 세트를 선택하여 사용할 **데이터 세트 생성** 으로 이동합니다. **데이터 세트 생성** 페이지에서는 다양한 데이터 원본에서 데이터 세트를 생성할 수 있습니다. 본 Lab에서는 아래의 데이터 원본 중 **S3**를 사용하여 데이터 세트를 생성하도록 하겠습니다.

 

\3.   JSON **매니페스트 파일** 을 사용하여 **QuickSight** 로 가져올 Amazon S3 파일을 지정합니다. 데이터 세트 페이지에서 S3를 선택하면 나타나는 팝업창에서 데이터세트의 이름인 **데이터 원본 이름** 과 **매니페스트 파일 업로드** 입력란에 아래와 같이 입력한 후 연결을 클릭합니다.

 

매니페스트 파일 업로드 URL:

https://aws-kr-immersionday.s3.ap-northeast-2.amazonaws.com/quicksight/retail.manifest

 

\4.   **데이터 세트 생성** 이 완료되었습니다. 생성된 데이터 세트의 데이터를 조회하고 편집하기 위해 **데이터 편집****/****미리보기** 를 선택합니다.

 

**Option 2:**

 

\1.   데이터 세트를 생성을 위해 아래의 초기화면에서 **데이터 관리** 로 이동합니다.

 

\2.   데이터 관리 페이지에서 **새 데이터 세트**를 선택하여 사용할 **데이터 세트 생성** 으로 이동합니다. **데이터 세트 생성** 페이지에서는 다양한 데이터 원본에서 데이터 세트를 생성할 수 있습니다. 본 Lab에서는 아래의 데이터 원본 중 **S3**를 사용하여 데이터 세트를 생성하도록 하겠습니다.

 

\* 업로드할 파일은 아래의 링크를 통해 미리 다운로드 받습니다.

https://aws-kr-immersionday.s3.ap-northeast-2.amazonaws.com/quicksight/retail-dataset.csv

 

\3.   파일 업로드가 완료되면 **설정 편집 및 데이터 준비** 를 선택합니다.

 

 

 

\4.   데이터 편집과 조회를 위한 페이지가 아래와 같이 보여집니다.

 

 

\5.   지역 정보의 계층화된 데이터를 관리하기 위해 **계층** 을 생성하도록 하겠습니다. country 필드의 **V**를 클릭하여 **계층에 추가** 를 선택합니다.

 

 

\6.   **필드를 계층에 추가** 팝업에서 새로운 지역 계층 생성을 선택하고 **추가** 버튼을 클릭하면 아래와 같이 생성할 계층을 입력할 수 있습니다. 계층 이름을 Location을 입력하고 **이 계층은 단일 국가용입니다****.** 를 선택한 후 데이터 세트에 사용되는 국가인 **미국** 을 선택합니다.

 

\7.   다시 한번 country 필드의 **V**를 클릭하여 **계층에 추가** 를 선택하면 아래와 같이 지역 계층에 추가할 수 있는 팝업이 나타나며 이전에 생성한 **기존 지역 계층에 추가** 를 선택하고 **Location** 을 지정한 후 **추가** 버튼을 클릭합니다.

 

\8.  **city**와 **state**, **postcode**도 동일하게 계층에 추가하면 좌측 필드가 아래와 같이 보여집니다.

 

 

\9.   필드의 데이터 유형에 맞도록 데이터 형식을 변경하도록 하겠습니다. **orderdate**의 **V** 를 클릭하면 나타나는 메뉴에서 **데이터 형식 변경** 을 선택하고 데이터 형식을 **Date**로 변경합니다. 

 

 

\10. 변경하려는 Date의 날짜 형식이 자동으로 감지되지 않을 경우 데이터 원본의 날짜 형식을 입력해야 합니다. 아래와 같은 **날짜 형식 편집** 창에서 입력하고 업데이트를 클릭합니다.

 

입력할 날짜 형식: dd/MM/yyyy HH:mm 

 

\11.  **shipdate**도 동일하게 **Date**로 변경하면 필드가 아래와 같이 보여집니다. 

 

 

\12.  원본 데이터에는 **주문별 제품 가격**과 **수량**, **할인정보** 등이 있지만 데이터 분석에는 **주문 건 별 총 판매 금액**이 필요합니다. 메뉴의 **계산된 필드 추가** 를 클릭하여 판매 금액 필드를 생성합니다. 

 

\13.  계산된 필드 편집 팝업에서 아래와 같이 계산된 필드 이름과 공식을 입력하고 생성을 클릭합니다. 

 

**계산된 필드 이름**: sales

**공식**: price * quantity * (1 - discount)

 

데이터 세트가 준비되었습니다. 상단의 **저장 및 시각화** 를 클릭하여 시각화 페이지로 이동합니다. 

 

 

## 핵심성능지표(KPI)로 전년 대비 매출 시각화

 

\1.   좌측 필드 목록에서 **sales**와 **orderdate**를 선택합니다. 이때 **AutoGraph**는 주문일자별 판매 금액에 대해 아래와 같이 자동으로 적합한 차트를 선택해서 보여줍니다.

 

 

\2.   화면 좌측 하단에서 **시각적 객체 유형** 을 **핵심성능지표****(KPI)** 차트로 변경합니다.

\3.   상단의 **필드 모음** 에서 **orderdate** 필드의 메뉴를 클릭하여 집계를 **년** 으로 변경합니다.

 

\4.   **sales(****합계****)** 의 메뉴를 클릭하고 **형식****: 1,235** (세 번째 옵션)를 선택하여 표기 형식을 변경합니다.

 

\5.   sales(합계) 입력란의 메뉴를 다시 클릭하고 **다음과 같이 표시****:** **통화** 를 선택합니다.

\6.   차트 오른쪽 상단의 **시각적 객체 형식 지정 메뉴** 버튼을 클릭합니다.

 

 

\7.   **시각적 객체 형식 지정** 에서 아래와 같이 **비교 방법** 을 **퍼센트 차이** **(%)** 로 변경합니다.

 

\8.  제목을 클릭하여 전년 대비 판매로 변경하고 시각적 객체 크기를 더 작게 조정합니다.

 

 

 

 

## 월간 판매 동향 시각화

 

\1.   좌측 상단에서 **+** **추가** 를 선택한 후 **시각적 객체 추가** 를 클릭합니다.

 

\2.   **필드 목록** 에서 **sales**와 **orderdate**를 선택합니다. 2개의 필드를 선택하는 것만으로도 아래와 같이 일별 판매 추세를 보여주는 시계열 차트가 자동으로 완성됩니다.

 

\3.   화면 상단의 **필드 모음** 에서 **orderdate** 필드의 메뉴를 사용하여 집계를 **월** 로 변경합니다.

 

 

## 막대 차트의 드릴 업/다운 기능

 

\1.   좌측 상단에서 **+** **추가** 를 선택한 후 **시각적 객체 추가** 를 클릭합니다.

\2.   필드 목록에서 **sales**와 **bigcategory**를 선택하면 아래와 같은 막대 차트가 나타납니다.

 

\3.   상단의 **필드 모음** 을 클릭하여 확장시킨 후 **필드 목록** 에서 **subcategory** 필드를 드래그하여 필드 모음의 **bigcategory** 필드 아래에 놓습니다. 이때 **드릴다운 계층 추가** 라고 표시됩니다.

 

\4.   **subcategory** 필드가 **드릴다운 계층** 으로 추가되면 **Y****축** 은 아래와 같이 보여집니다.

 

\5.   차트의 **bigcategory** 를 클릭하면 **subcategory****까지 드릴다운** 이라는 추가 메뉴가 표시됩니다.

 

\6.   **subcategory****까지 드릴다운** 을 선택하면 해당 카테고리의 데이터만 막대 차트로 보여집니다.

 

\7.   필드 목록에서 **productname** 필드를 필드 모음의 subcategory 필드 아래에 드래그합니다. 이제 **productname**까지 드릴다운할 수 있습니다. 이때 **시각적 객체** 우측의 화살표를 클릭해서도 드릴다운과 드릴업을 할 수 있습니다.

 

 

## 목표 대비 성과 시각화

 

\1.   좌측 상단에서 **+** **추가** 를 선택한 후 **시각적 객체 추가** 를 클릭합니다.

\2.   좌측 하단에서 **시각적 객체 유형** 을 **게이지 차트** 로 변경합니다.

 

 

\3.   **필드 목록** 에서 **sales**를 선택합니다.

 

\4.   좌측 상단에서 **+** **추가** 를 선택한 후 **계산된 필드 추가** 를 선택합니다.

\5.   **계산된 필드 이름** 에는 **goal** 을 입력하고 **공식** 에는 숫자 **2000000** (2백만)을 입력합니다.

 

\6.   **필드 목록** 에서 **goal**필드를 클릭하여 **게이지 시각적 객체** 에 **대상** 값으로 추가합니다.

\7.   **대상 값** 의 goal 필드의 메뉴를 클릭하고 **집계** 를 **합계** 에서 **평균** 으로 변경합니다.

 

## 카테고리별 총 매출의 % 시각화

 

\1.   좌측 상단에서 **+** **추가** 를 선택한 후 **시각적 객체 추가** 를 선택합니다.

\2.   좌측 하단에서 **시각적 객체 유형** 을 아래와 같이 **도넛 차트** 로 변경합니다.

 

 

\3.   **필드 목록** 에서 **sales**와 **subcategory**를 선택합니다.

\4.   **시각적 객체** 에서 **시각적 객체 형식 지정 메뉴** 를 클릭합니다.

 

\5.   **데이터 레이블 영역** 을 확장하고 **지표 표시** 체크박스를 체크합니다.

\6.   **범례 영역** 을 확장하고 **범례 표시** 선택을 해제하고 Title의 **제목 표시** 도 해제합니다.

 

## 카테고리별 분석을 위한 트리맵 

 

\1.   좌측 상단에서 **+** **추가** 를 선택한 후 **시각적 객체 추가** 를 클릭합니다.

\2.   좌측 하단에서 **시각적 객체 유형** 을 **트리맵** 으로 변경합니다.

\3.   **필드 목록** 에서 **그룹화 기준** **subcategory**, **크기** **sales**, **색상** **discount**을 지정합니다.

 

## 분포와 관계 분석을 위한 산점도

 

\1.   좌측 상단에서 **+** **추가** 를 선택한 후 **시각적 객체 추가** 를 클릭합니다.

\2.   좌측 하단에서 **시각적 객체 유형** 을 **산점도** 로 변경합니다.

\3.   필드 목록에서 **X****축** **price**, **Y****축** **discount**, **크기** **sales**, **그룹****/****색상** **subcategory**를 지정합니다.

\4.   **price**, **discount**를 **평균**, **sales**를 **합계** 로 지정합니다.

\5.   **시각적 객체 형식 지정 메뉴** 를 클릭하여 **Y****축 범위** 를 **사용자 지정 범위** **0 ~ 0.4**로 변경합니다.

 

## 막대 콤보 차트

 

\1.   좌측 상단에서 **+** **추가** 를 선택한 후 **시각적 객체 추가** 를 클릭합니다.

\2.   좌측 하단에서 **시각적 객체 유형** 을 **클러스터 막대 콤보 차트** 로 변경합니다.

\3.   **필드 목록** 에서 **X****축** **orderdate**(**월**), **막대** **sales**, **선** **discount**를 지정합니다.

 

## 파라미터 및 컨트롤을 사용한 필터링

 

\1.   좌측 메뉴에서 **파라미터** 를 클릭한 다음 **하나 생성** 을 클릭합니다.

 

\2.   **이름** 을 **subcategory**로 입력하고 **생성** 버튼을 클릭합니다.

 

\3.   **파라미터 추가됨** 창에서 **컨트롤** 을 선택합니다.

 

\4.   **파라미터용 컨트롤 추가** 창에서 **표시 이름** 을 **subcategory**로 입력하고 **스타일** 을 **단일 선택 드롭다운** 으로 변경합니다. **데이터 세트 필드에 연결** 을 선택한 후 **데이터 세트 선택** 과 **열 선택** 에서 **subcategory** 컬럼을 선택하고 추가합니다.

 

\5.   이때 시각적 객체 위에 접힌 상태로 표시된 새로운 **컨트롤** 영역을 클릭하여 확장하면 **subcategory** 필드의 값이 포함된 새 **컨트롤** 을 볼 수 있습니다. 여기에 있는 값 목록은 새 세그먼트가 데이터에서 추가되거나 제거되면 자동으로 업데이트됩니다.

 

\6.   **필터** 버튼을 클릭한 다음 **하나 생성** 을 클릭하여 **subcategory** 필드를 선택합니다.

 

\7.   **subcategory** **필터**를 클릭하여 확장하고 **필터 유형** 을 **사용자 지정 필터** 로 변경합니다.

 

\8.  **파라미터 사용** 체크 박스를 선택하면 적용할 필터 범위를 모든 시각적 객체로 변경할지 묻는 팝업이 표시되고 **예** 를 선택하면 필터가 이 탭의 모든 시각적 객체에 적용되도록 설정됩니다. 

 

\9.   **subcategory** **파라미터** 를 선택하고 **적용과 닫기** 를 클릭합니다. 

 

\10. 이제 **subcategory** **컨트롤** 을 사용하여 이 탭/시트의 모든 시각적 객체를 필터링할 수 있습니다.

## 세부사항 시트 추가 및 드릴 다운

 

\1.   **시트** **1** 의 이름을 **요약** 으로 바꾸고 시트 1의 탭 옆에 있는 + 버튼을 클릭하여 **새 시트** 를 만든 후  이름을 **세부 사항** 으로 바꿉니다.

 

\2.   세부 사항 시트의 시각적 객체를 **테이블 시각적 객체 유형** 으로 선택합니다.

 

\3.   **필드 목록** 에서 **ordered, orderdate, customername, productname, subcategory, city, state, sales, quantity, discount** 등을 클릭하여 필드를 추가합니다.

\4.   화면의 전체 너비에 맞게 **시각적 객체** 크기와 컬럼 크기를 아래와 같이 조정합니다.

 

\5.   **시각적 객체 이름** 을 **주문 상세** 로 변경합니다.

 

\6.   category 필드에 대한 파라미터를 사용하여 **요약** 시트의 **도넛 차트** 에서 **세부 사항** 시트 의 **테이블** 로 드릴 다운하도록 세부 사항에 적용될 **파라미터** 를 생성하겠습니다.

\7.   **필터** 메뉴에서 **하나 생성** 을 클릭한 후 **subcategory** 필드를 선택합니다. 생성한 필터를 확장하여 **필터 유형** 을 **사용자 지정 필터** 로 변경하고 **파라미터 사용** 을 선택합니다. 이때 필터의 범위를 변경할 것인지에 대해 묻는 팝업에서 **예** 를 선택합니다.

 

\8.  **파라미터** 중 **subcategory**를 선택하고 **적용과 닫기** 를 클릭합니다.

\9.   **세부 사항** 시트의 브라우저에서 URL의 마지막 부분에 아래를 추가합니다. 이때 URL을 통해 파라미터의 값을 설정하면 테이블이 Auto로 필터링되는 것을 볼 수 있습니다.

**#p.subcategory=Paper**

 

\10. **URL actions** 기능을 사용하여 **요약** 시트 에서 **세부 사항** 시트로 드릴 다운을 설정하겠습니다.

\11.  **세부 사항** 시트에서 아래와 같은 형식의 주소 표시줄의 URL을 복사합니다.

https://ap-northeast-2.quicksight.aws.amazon.com/sn/analyses/xxxxxxxxxxxxxxxxxxxx-9b08e48d7c34#p.subcategory=

\12.  **요약** 시트에서 **도넛 차트** 의 메뉴를 사용하여 **작업** 을 선택합니다.

 

\13.  **작업** 에서 + 버튼을 클릭하여 **새 작업** 을 생성하고 **작업 이름** 에 **상세 보기** 를 입력하고 **+** 버튼을 클릭하여 아래와 같이 **subcategory** 필드를 삽입합니다.

 

\14. **활성화** 방식은 **메뉴 옵션** 을 선택하고 **작업 유형** 은 **URL** **작업** 으로 지정합니다. URL에는 세부 사항 시트에서 복사한 URL을 붙여넣기한 후 **‘#p.subcategory=’**을 URL 끝부분에 추가합니다. 그리고 **+** **버튼** 을 클릭하여 **subcategory** **필드** 를 끝에 삽입한 후 **저장과 닫기** 를 클릭합니다

 

\15.  이제 **도넛 차트** 에서 어떤 subcategory를 클릭하든지 다음과 같은 새로운 옵션을 볼 수 있고 옵션을 선택하면 **세부 사항** 시트로 이동하여 선택한 카테고리로 자동 필터링이 적용됩니다.

 

 

## 계산된 필드를 사용한 전년 대비 매출 차이

 

\1.   +의 **계산된 필드 추가** 를 선택하고 **함수 목록** 에서 **percentDifference**를 선택한 후 **공식** 에 아래를 입력합니다.

**계산된 필드 이름**: YoY% increase

**공식**: percentDifference(sum(price * quantity * (1 - discount)),[orderdate ASC],-1,[regiontype])

 

\2.   좌측 상단에서 **+** **추가** 를 선택한 다음 **시각적 객체 추가** 를 선택하고 **필드 목록** 에서 **orderdate, regiontype, YoY% increase**를 선택합니다. **orderdate** **집계** 를 **년** 으로 변경합니다.

 

## 계산된 필드를 사용한4주 이동 평균 비교

 

\1.   +의 **계산된 필드 추가** 를 선택하고 **함수 목록** 에서 **windowAvg**를 선택한 후 아래와 같이 입력합니다.

**계산된 필드 이름****: Rolling Avg Sales**

**공식****: windowAvg(sum(sales),[{orderdate} ASC],4,0)**

\2.   좌측 상단에서 **+** **추가** 를 선택한 다음 **시각적 객체 추가** 를 선택하고 **필드 목록** 에서 **orderdate, sales, Rolling Avg Sales**를 선택합니다. **orderdate** **집계** 를 **주** 로 변경합니다.

 


 



 

 

 

## ML기반 예측 

 

Amazon QuickSight는 ML Insights를 통해 숨겨진 데이터 추세를 발견하거나, 주요 비즈니스 동인을 파악하고, 향후 결과를 예측하고, 읽기 쉬운 자연어 서술로 데이터를 요약하여 수동 분석 및 조사에 들이는 시간을 절약할 수 있게 해 줍니다.

 

## ML기반 예측 

 

\1.   이전에 생성했던 **판매 동향 차트** 의 **메뉴** 를 사용하여 **예측 추가** 를 선택합니다.

 

\2.   좌측의 **예측 속성** 에서 **앞으로의 기간** 을 **14**, **이전 기간** 을 **14**로 변경하고 **적용** 을 클릭합니다. 이때 나타나는 차트에서 지난 14개월 동안의 예측이 실제와 얼마나 비슷한지 알 수 있습니다.

 

\3.   **제목** 을 클릭하여 월간 판매 동향으로 변경하고 **예측 속성** 에서 **이전 기간** 을 0으로 다시 변경하고 적용을 클릭하여 아래와 같이 앞으로의 14개월간의 예측만 보여지도록 변경합니다. 

 

 

## ML기반 가정 분석 

 

\1.   **가정 분석****(What-if** **분석****)**을 통해 **대상** 에 대한 예측을 생성할 수 있습니다. 가정 분석을 실행하기 위해 차트의 예측 그래프(여기서는 마지막 부분)를 클릭하여 **가정 분석 메뉴** 를 선택합니다.

 

\2.   현재 예상되는 매출의 2배로 가정 분석을 실행하기 위해 **가정 분석** 의 **대상** 을 **14158.6126**에서 **30300**으로 약 2배로 값을 변경하고 적용을 클릭합니다.

\3.   **대상** 값에 따른 가정 분석과 예측 분석이 **실선** 과 **점선** 으로 아래와 같이 동시에 보여집니다.

 

##  

## 인사이트 추가

 

\1.   **대시보드** 에 **인사이트** 를 추가하기 위해 +의 **인사이트 추가** 를 클릭합니다.

 

\2.   **컴퓨팅** 팝업창에서 **상위 무버** 를 선택한 다음 **선택** 을 클릭합니다.

 

\3.   **필드 목록** 에서 **orderdate, customerame, sales**를 **인사이트** 에 필드를 추가하고 **orderdate**의 **집계** 를 **월** 로 변경합니다.

\4.   최근 2 개월 동안의 데이터 판매량 변화 비교로 3대 고객이 가장 크게 증가했음을 알 수 있습니다. **이름** 을 인사이트에서 **상위 고객** **Mover**로 변경합니다.

 

 

## ML 기반 이상 탐지

수십억 개의 데이터 포인트를 지속적으로 분석하여 숨겨진 통찰력을 파악합니다.

 

\1.   좌측 상단에서 **+** **추가** 를 선택한 다음 **인사이트 추가** 를 클릭합니다.

 

\2.   **컴퓨팅** 팝업창에서 **이상 탐지****(ML****기반 인사이트****)** 를 선택한 다음 **선택** 을 클릭합니다.

 

\3.   **필드 목록** 에서 **orderdate, subcategory, sales**를 선택하고 **orderdate** 필드에서 **집계** 를 **월** 로 변경한 후 인사이트 내에서 **시작하기** 버튼을 클릭합니다.

\4.   **이상 탐지 구성** 에서는 표시할 **최대 이상현상 수** 를 설정하고 **실행 빈도** 를 예약할 수 있으며 **기여 분석** 을 실행할 필드와 하나 이상의 **범주****/****차원** 의 조합을 사용해 분석할 수도 있습니다.

 

\5.   **기여 분석** 기능을 통해 발견된 이상을 탐색하고 이상에 기여한 원인을 파악할 수 있습니다. **기여 분석** 드롭 다운에서 **city**와 **customername**, **productname**을 선택하고 저장을 클릭합니다.

 

\6.   **인사이트** 의 **지금 실행** 을 클릭합니다.

 

\7.   실행하는데 몇 분이 걸리고 완료되면 탐지된 이상이 보여집니다.

 

\8.  탐지된 이상이 보여지면 **인사이트** 에서 **이상 탐색** 을 클릭합니다.

 

\9.   **이상 탐색** 페이지에서는 왼쪽에서 탐지된 이상에 기여한 **상위 기여자** 를 볼 수 있습니다.

 

\10. 기여자 중 하나를 가리키면 더 많은 정보를 볼 수 있습니다. 

 

\11.  **분석으로 돌아가기** 를 클릭합니다.

\12.  좌측 **인사이트** 메뉴를 클릭하여 **제안된 인사이트** 를 조회합니다.

 

\13.  제안된 인사이트들 중 **YOY INCREASE** **기준** **ORDERDATE AND REGIONTYPE**아래 **시트에 이상을 추가** 버튼을 클릭하고 **이상 탐지 구성** 에서 필요한 변경 사항을 지정한 후 저장합니다..

 

\14. **지금 실행** 버튼을 클릭합니다.

 

## 제안된 인사이트에서 ML 기반 예측과 자동 설명 추가

단순한 포인트 앤 클릭 방식으로 성장 및 비즈니스 추세를 예측하고 이해하기 쉬운 언어로 된 설명을 사용하여 고객에게 대시보드의 정보를 전달합니다.

 

\1.   **인사이트** 메뉴를 클릭하면 QuickSight가 자동으로 생성한 모든 인사이트를 확인할 수 있으며 다른 사용자에게 도움이 될 것으로 생각되는 인사이트를 대시 보드에 추가합니다.

 

\2.   상단으로 스크롤하여 **월간 판매 동향** 의 **월에 걸친 월** 변경 통계 위로 마우스를 가져간 다음 +를 클릭하여 **대시 보드** 에 추가합니다. **예측 인사이트** 도 반복 수행합니다.

 

\3.   **기간별 인사이트** 의 메뉴를 사용하여 **서술 사용자 지정** 을 선택합니다.

 

\4.   판매 증가와 감소를 강조하기 위해 **increase by**와 **decrease by**를 빨간색으로 변경한 후 (문구 수정도 가능) 저장을 클릭합니다.

 

 

\5.   변경한 **자동 설명** 이 아래와 같이 보여집니다.

 

 

## 만들어진 대시보드의 모습

 

## 대시보드 공유를 위한 사용자 초대

 

\1.   화면 우측 상단의 관리를 위한 설정 버튼을 클릭하고 **QuickSight****관리** 를 선택합니다.

 

\2.   **사용자 관리** 메뉴에서 **사용자 초대** 버튼을 클릭합니다.

 

\3.   **대시보드** 를 공유할 사용자의 **이메일 주소** 를 입력하고 **엔터키** 를 입력하거나 **+** 를 클릭하여 아래의 목록에 해당 사용자가 추가되면 사용자의 역할을 독자(Reader)로 지정합니다. **IAM** **사용자** 가 아니므로 **아니요** 를 선택합니다.

 

\4.   사용자가 추가되고 처음 사용자에게는 아래와 같은 **초대 메일** 이 발송됩니다.

 

\5.   초대를 수락하면 아래와 같은 계정 생성과 로그인 창이 나타나며 이때 로그인할 암호를 생성하면 로그인이 됩니다.

 

\6.   아래와 같이 로그인을 위한 계정이 활성화 되었음을 알려주는 페이지가 나타납니다.

 

## 대시보드 공유를 위한 사용자 초대

 

\1.   아래와 같이 공유할 대시보드 우측 상단의 **공유** 버튼을 클릭하고 **대시보드 게시** 를 선택합니다.

 

\2.   **대시보드 이름** 을 입력하고 **대시보드 게시** 를 클릭합니다. 

 

\3.   다음 화면에서 이미 등록된 QuickSight 사용자를 검색해서 **대시보드** 를 **공유** 할 수 있습니다. 

\* 계정을 Active Directory에 연결했거나 QuickSight API를 통해 사용자 그룹을 프로비저닝한 경우는 그룹 이름을 입력하여 개별 사용자가 아닌 그룹과 대시 보드를 공유 할 수도 있습니다.

 

\4.   공유가 완료된 계정이 아래와 같이 **관리자** 나 **독자** 로 보여집니다.

 

\5.   관리자(작성자) 계정은 로그 아웃하고 새로 공유한 사용자로 로그인하면 공유된 대시보드를 아래와 같이 볼 수 있습니다.

 

 



 

## QuickSight 모바일 앱

 

QuickSight 모바일 앱을 사용하면 어디서든 안전하게 데이터에서 통찰력을 얻고, 대시보드 검색 및 즐겨찾기 추가, 상호 작용 등을 할 수 있습니다. 드릴다운 및 필터를 사용하여 데이터를 탐색하고, 예측을 통해 앞서 나가고, 데이터에서 예상치 않은 변경이 발생할 때 이메일 알림을 받고, 통찰력을 동료와 공유할 수 있습니다.

 

\1.   QuickSight Mobile 앱을 다운로드하려면 iOS 및 Android별로 디바이스용 앱을 아래의 링크를 통해 다운로드 받습니다.

iOS App Store: https://apps.apple.com/us/app/amazon-quicksight/id1148226615

Google Play: https://play.google.com/store/apps/details?id=com.amazonaws.quicksight.mobile&hl=en_US

 

\2.   다운로드가 완료되면 아래와 같이 계정명, 이메일 주소, 비밀번호를 입력하여 로그인합니다.

​       

 

\3.   로그인이 되면 대시보드를 클릭하여 공유된 대시보드를 조회합니다. 아래와 같이 도넛차트의 차트를 클릭하여 상세보기 전환을 하거나 상단의 필터를 적용할 수 있습니다.

​      



 

**Option 1:** **이벤트 엔진을 사용한** **AWS Console** **접속**

 

\* 이벤트 엔진을 사용하는 경우 https://dashboard.eventengine.run 으로 접속한 후 아래와 같이 배포된 12자리의 Team Hash를 입력하면 로그인하면 아래와 같은 Team Dashboard로 이동합니다. 

 

 

위의 화면에서 AWS Console을 클릭해서 AWS 관리 콘솔로 접속하기 위한 팝업에서 Open AWS Console을 클릭합니다.

 

 

 

이제 AWS 관리 콘솔에서 QuickSight를 사용할 수 있습니다.

 

**Option 2: Redshift****에 데이터 세트 생성**

 

Redshift 테이블 생성을 위해 아래 3개의 DDL을 실행합니다.

​     create table customer(     customerid varchar(10) not null,     customername varchar(30),     customertype varchar(20),     country varchar(20),     city varchar(20),     state varchar(20),     postcode varchar(10),     regiontype varchar(10)  );     create table product(     productid varchar(20),     bigcategory varchar(20),     subcategory varchar(20),     productname varchar(100),     price decimal(5, 2)  );     create table customer_order(     seq integer not null,     orderid varchar(20),     orderdate timestamp,     shipdate timestamp,     customerid varchar(10),     productid varchar(20),     quantity integer,     discount decimal(3, 2)  );     

 

생성한 테이블에 데이터 적재를 위해 아래와 같이 COPY 명령어를 사용해서 S3에서 데이터를 적재합니다.

  COPY  customer   FROM  's3://aws-kr-immersionday/redshift/customer.csv'  credentials  'aws_iam_role=arn:aws:iam::AccountNumber:role/redshift_role'  CSV  IGNOREHEADER  1;     COPY  customer_order   FROM  's3://aws-kr-immersionday/redshift/order.csv'   credentials  'aws_iam_role=arn:aws:iam::AccountNumber:role/redshift_role'  CSV  IGNOREHEADER  1;     COPY  product   FROM  's3://aws-kr-immersionday/redshift/product.csv'   credentials  'aws_iam_role=arn:aws:iam::AccountNumber:role/redshift_role'  CSV  IGNOREHEADER  1;  

 

이제 QuickSight를 사용할 데이터가 Redshift에 적재되었습니다.

 

**Option 3: Private** **서브넷의** **Redshift****와 함께** **QuickSight** **사용하기**

 

Private 서브넷의 Redshift 클러스터와 QuickSight를 사용하기 위해서는 Private한 Connection 설정이 필요합니다. 먼저 Redshift 클러스터가 있는 VPC에 QuickSight가 사용할 Private 서브넷을 생성합니다.

 

**VPC** 의 **서브넷** 에서 **VPC** 에 Redshift 클러스터 VPC를 지정하고 **가용 영역** 은 지정하지 않고 CIDR 블록을 VPC CIDR를 고려한 값을 입력하여 **서브넷** 을 생성합니다.

 

**VPC** 메뉴의 **보안 그룹** 에서 **보안 그룹 생성** 을 클릭하고 아래와 같이 QuickSight **보안 그룹** 을 생성합니다.

 

QuickSight **보안 그룹** 의 **인바운드 규칙** 탭에서 **규칙 편집** 을 클릭하여 아래와 같이 **규칙** 을 입력합니다.

 

**유형****:** **모든** **TCP,** **프로토콜****: TCP,** **포트 범위****: 0 – 65535,** **소스****:** **사용자지정****(Redshift** **클러스터 보안그룹****ID)**

 

QuickSight **보안 그룹** 의 **아웃바운드 규칙** 탭에서 **규칙 편집** 을 클릭하여 아래와 같이 **규칙** 을 입력합니다.

 

**유형****: Redshift,** **프로토콜****: TCP,** **포트 범위****: 5439,** **대상****:** **사용자지정****(Redshift** **클러스터 보안그룹****ID)**

 

Redshift**보안 그룹** 의 **인바운드 규칙** 탭에서 **규칙 편집** 을 클릭하여 아래와 같이 **규칙** 을 입력합니다.

 

**유형****: Redshift,** **프로토콜****: TCP,** **포트 범위****: 5439,** **대상****:** **사용자지정****(QuickSight** **보안그룹****ID)**

 

Redshift **보안 그룹** 의 **아웃바운드 규칙** 탭에서 **규칙 편집** 을 클릭하여 아래와 같이 **규칙** 을 입력합니다.

 

**유형****:** **모든** **TCP,** **프로토콜****: TCP,** **포트 범위****: 0 – 65535,** **소스****:** **사용자지정****(QuickSight****보안그룹****ID)**

 

관리 기능을 사용하기 위해 우측 상단 버튼을 클릭하여 아래와 같은 **QuickSight** **관리** 페이지로 이동합니다.

 

아래와 같이 메뉴에서 **VPC** **연결 관리** 를 선택하고 **VPC** **연결 추가** 버튼을 클릭합니다.

 

**VPC** **연결 추가** 에서 **VPC** **연결 이름** 은 **qsconnection**, **VPC ID** 는 **Redshift VPC****의** **ID**, **서브넷** **ID**에는 앞에서 생성한 서브넷을 지정한 후 **보안 그룹** **ID** 에는 생성한 **QuickSight** **보안그룹** **ID** 를 입력합니다.

 

 

**새 데이터 세트** 의 **데이터 세트 생성** 에서 **Redshift** **자동 검색됨** 을 클릭합니다.

 

 

**새** **Redshift** **데이터 원본** 팝업창에서 **데이터 원본 이름** 은 **retail-dataset**, **인스턴스** **ID** 는 **Redshift** **클러스터** **ID**, **연결 유형** 은 **qsconnection**, **데이터베이스 이름** 은 **dev**, **사용자 이름** 은 **awsuser**, **암호** 를 입력한 후 **연결 확인** 버튼을 클릭합니다.

 

 

정상적으로 연결된 경우 아래와 같이 버튼이 **확인됨** 으로 바뀌며 이때 **데이터 원본 생성** 버튼을 클릭합니다.

 

 

**테이블 선택** 팝업에서 테이블을 선택하지 않고 **사용자 지정** **SQL** **사용** 버튼을 클릭합니다.

 

아래와 같이 사용자 지정 SQL 쿼리의 **쿼리명** 과 **쿼리** 를 입력하고 **쿼리 확인** 버튼을 클릭합니다.

 

​      \* 입력 쿼리

  SELECT customer_order.orderid, customer_order.orderdate,      customer_order.shipdate,  customer_order.customerid,      customer.customername,  customer.customertype,       customer.country, customer.city,  customer.state,       customer.postcode,  customer.regiontype,      product.productid,  product.bigcategory, product.subcategory,       product.productname, product.price,  customer_order.quantity,       customer_order.discount  FROM  customer_order, customer, product  WHERE  customer_order.customerid =  customer.customerid and       customer_order.productid =  product.productid  

 

QuickSight의 데이터 저장소 SPICE로 가져올 데이터 세트 생성이 완료되었음을 나타내는 팝업에서 **데이터 편집****/****미리 보기** 를 클릭합니다.

 

데이터 세트 준비가 완료되었습니다. 아래의 화면에서 필드를 클릭하여 가져온 데이터를 확인합니다.

 

 

 

 



 

 

 

 

 

 

 

 

수고하셨습니다! Amazon QuickSight Hand-On Lab이 끝났습니다.

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

END OF DOCUMENT