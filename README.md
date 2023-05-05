# :palm_tree::hotel: 제주도 호텔리뷰 감성분석 :hotel::palm_tree:
프로젝트 기간 : 2023.3.2 - 2023.3.16
  
  <br/>


## :one: 프로젝트 주제 ##

인터넷 상 존재하는 구매후기를 자연어 처리로 긍정/부정으로 감성 분석하여 새로운 평점 기준을 설정

<br/>

## :two: 주제 선정 이유 ##

> 평점은 낮은데 리뷰속 내용은 긍정 혹은 평점 높은데 리뷰텍스트는 부정인 것을 구분할 수 있을까??

</br>

#### _평점,후기 기반의 리뷰에서 평점은 낮지만 후기 내용은 좋거나, 평점은 높아도 후기 내용이 부정적인 리뷰 다수… 사용자가 평점을 매기는 것이 아닌, 후기 내용을 분석하여 평점 부여_ ####
</br>


 영화나 식당, 숙박업, 인터넷 쇼핑 등 다양한 소비 분야에서 고객들의 평점 및 리뷰를 확인할 수 있다. <br/>
이는 단순히 개인의 경험을 서술하는 것에 그치지 않고, 그 상품을 구매할 가능성이 있는 사람들에게 대단히 큰 영향력을 미친다. <br/>
한국소비자연맹에서 제공하는 지표에 따르면, 소비자가 상품을 구매하기 전, 이용후기를 확인하는 비율이 97.2%에 이른다. 또한, 엠브레인 트렌드 모니터에서 조사한 바에 따르면, 상품 리뷰를 확인하는 이유 중 1위는 믿을 수 있는 제품인지 확인하기 위해서이다. <br/>
주제 선정에 있어서 가장 큰 이유는 _평점과 후기 내용의 모순_ 이다. 
</br>

 여러 리뷰 데이터를 수집한 결과, 세부 내용에는 ‘상품에 만족함’, ‘재방문 의사가 있음’, ‘방문 경험에 만족함’ 등 긍정적인 단어가 포함되어 있지만 평점은 상대적으로 낮게 책정된 리뷰를 많이 볼 수 있었다. <br/>
실제로 그 제품의 성능이나 만족도가 높더라도, 평점이 낮게 책정되어 있으면 리뷰를 보는 소비자들은 세부 내용을 하나하나 확인하기보단 직관적으로 평점에 따라 판단하기 때문에, 좋은 품질의 제품을 선택하는 것에 있어서 혼란을 줄 수 있다고 생각하였다. 
</br>
</br>

이에 따라, 평점이 주가 되는 리뷰를 어디까지 믿을 수 있는 것인가에 대하여 의문을 가지고 프로젝트 주제를 선정하였다.

<br/>

## :three: 데이터 ##

1) 데이터 수집
: 아고다 홈페이지에서 호텔업 등급 결정 현황 (2023.2.20 -제주특별자치도관광협회)에서 발표한 56개의 호텔기준으로 웹크롤링

2) 데이터 가공
- 결측치, 이상치 확인 후 변경
- 한국국적 리뷰만 추출

<br/>

## :four: EDA ##
![제목 없음](https://user-images.githubusercontent.com/122995812/226657583-45cf4aa4-67a1-4c2c-8ec2-525dccd073c8.png), ![제목 없음](https://user-images.githubusercontent.com/122995812/226657917-5ca21082-0aa2-4fa5-9a25-e563e3a900c4.png)


<br/>

## :five: 머신러닝 ##
</br>

- 평점 7점 기준으로 긍정/부정 분류
</br>
- 내용 확인 결과, 6점-9점 사이는 내용이 긍정/ 부정 반반
</br>
- 6점미만, 9점이상 데이터 학습 (나이브베이즈, 선형회귀, 랜덤포레스트 중 나이브베이즈 성능이 우수 ->  _나이브베이즈 분류기_ 선택)
</br>
- 평점 7점 이상 리뷰 : 긍정(1), 7점 미만 리뷰 : 부정(0) </br>
- 긍정/부정 키워드 추출 
</br>
- 명사, 형태소분석중 성능이 더 좋은 형태소로 리뷰 분석

<br/>

## :six: 결과 ##

![제목 없음](https://user-images.githubusercontent.com/122995812/226656905-dfcd92eb-1227-43b7-a9b2-49bfdfd1c2b8.png), ![제목 없음](https://user-images.githubusercontent.com/122995812/226657125-c946a02c-fbef-4a3d-9b99-ea57171ffb4e.png)

다른 지역의 호텔 리뷰를 확인한 결과, 2.0 평점을 받은 긍정적인 리뷰는 실제로 긍정적인 내용을 담고 있었고, 6.8 평점을 받은 부정적인 리뷰는 실제로 부정적인 내용을 담고 있음

<br/>

## 7️⃣ 기대효과
- 평점의 모호한 기준을 보완
-  다른 산업에서도 이러한 기준을 사용하여 평점을 확인한다면 기존의 평점보다는 조금 더 객관적으로 판단 가능

</br>

### 🤔 프로젝트 회고 ###
 처음 진행해 보는 머신러닝 프로젝트였기 때문에 주제 선정부터 어려움이 많았지만 팀원들 덕분에 성공적으로 마무리할 수 있었다.<br/>
프로젝트 초반에는 머신러닝을 배운지 얼마 안 돼서 걱정했었는데 선형회귀, 나이브 베즈, 랜덤 포레스트 분류기의 결과를 비교하면서 점점 더 좋은 결과를 찾아나아갔다. <br/>
 또한, 자연어처리에서 긍정 혹은 부정 중 어느 것에 중점을 둘지, 형태소와 명사 단위 중 어떤 것을 비교하여 성능이 더 좋았던 형태소분류를 하였다. 데이터 전처리와 시각화 과정에서 다양한 시각에서 살펴보면서 그 과정이 프로젝트의 방향을 결정하는 중요한 단계임을 깨달았다.<br/>
 EDA 과정에서 시각화하는 것이 마무리인줄 알았는데 어느 데이터가 적게 나왔다면 이유가 뭔지 알아보고 추론해보는 게 마무리이자 또 다른 시작임을 배웠다.
 




