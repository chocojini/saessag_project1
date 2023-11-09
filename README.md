<h2>saessag_project1</h2>

<h3>kaggle_data를 가지고 데이터분석 </h3>
<h4> 1. 주제 : 건강보험 가입자 중 자동차 보험 가입할 타겟 대상으로 마케팅활용</h4>

`Health Insurance Cross Sell Prediction 🏠 🏥`

[kaggle_Url](https://www.kaggle.com/datasets/anmolkumar/health-insurance-cross-sell-prediction/code)


<table>
  <tbody>
    <tr>
      <td align="center">
        <img src="https://github.com/chocojini/saessag_project1/assets/150269712/314f2583-9bbb-4508-bac0-ed7bb90b07d7" width="100px;"><br />
        <sub><b>jini:</b></sub>
      </td>
    </tr>
  </tbody>
</table>

<h4> 2. Tech Stack </h4>
<div align=left>
  <img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white"> 
  <img src="https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"> 
  <img src="https://img.shields.io/badge/numpy-013243?style=for-the-badge&logo=numpy&logoColor=white">


<h4> 3. columns 정리</h4>

  `Response`   -  0 : 고객이 관심이 없음 , 1 : 고객이 관심이 있음 <br>
  `Driving_License`   -  0 : 고객이 자동차 보험에 가입X, 1 : 고객이 이미 자동차 보험에 가입O <br>
  `Previously_Insured`   -  0 : 고객 과거에 차량을 파손X, 1: 고객 과거에 차량 파손 O <br>
  `Vehicle_Damage`   -  Yes, No로 표시 되어있음 <br>
  `Vehicle_Age`   -  1-2year, < 1year, > 2year  <br>
  <br>
  `Age` 범주화하기 <br>
  👉🏻 20대, 30대, 40대, 그 이상으로 나누기

```python
X_data['Age_GP_s'] = np.where (df['Age'] < 30, 1,
                           np.where(df['Age'] < 40, 2,
                           np.where(df['Age'] < 50, 3, 4)))
X_data.Age_GP_s.value_counts(), sorted(X_data.Age_GP_s.unique()), len(X_data.Age_GP_s.unique())
```

<h4> 4. 모델 선정</h4>
 <img src="https://github.com/chocojini/saessag_project1/assets/150269712/b573c8f8-1a4e-4f60-b8a9-00dd244f4740" width="500px;">

<h4> 5. 결론 </h4>
  <img src="https://github.com/chocojini/saessag_project1/assets/150269712/ceb3206e-d063-484b-ba8b-390d4c239400" width="500px;">

👉🏻 보험이 중복적으로 가입이 되면 납부에 대한 부담감이 크기 때문에, 
핸드폰처럼 가족 결합 상품을 만드는 것이 가입자들의 부담을 덜어줄 것으로 생각한다.
<br>
👉🏻 타보험(자동차)를 가지고 있는 사람들이 보험을 변경 하면,
보장금액이나 내역을 확대해주면 신규 가입자들을 늘릴 수 있을 것이다.
<br>
👉🏻자동차를 가지고있고, 자동차 소유 기간에 따른 연령별로 보험료 금액을 조절 하는 것

✔️사회 초년생들이 차량 구매시, 처음에 비싸서 부담이 되지만, 건강보험이나 몇개월 또는 몇년 조건을 걸어서 무사고 발생시 금액을 낮춰주는 특약이 있으면 좋을 것 같다. 


📌아쉬운 점
- AutoML 을 나중에 알게 되어서 사용하지 못했다.<br>
    → 사용을 했으면, 다양한 머신러닝 모델의 결과를 확인해서 선택 해서 비교를 할 수 있었을 텐데 그런 점이 아쉽다.

