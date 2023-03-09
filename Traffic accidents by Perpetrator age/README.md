## Car accidents by Perpetrator age
[Kaggle Link]()
[Source Link](https://www.data.go.kr/tcs/dss/selectFileDataDetailView.do?publicDataPk=15070183#/layer_data_infomation)


The Road Traffic Authority is a quasi-governmental agency under the National Police Agency that was established as a special corporation for education and technology research on road traffic safety based on the Road Traffic Act.

This agency provides the data collected and held free of charge to the private sector based on the Traffic Safety Act.

This data is statistical information on traffic accidents investigated and handled by the police, and only accidents with human damage were counted.

It contains the number of traffic accidents, the number of fatalities, the number of serious injuries, the number of minor injuries, and the number of reported injuries based on the age group of the offending driver.

### Dataset Details
| feature name | description |
|:--:|----|
| age| The perpetrator's categorical age |
|num_of_accident|number of incidents|
|deathtoll|number of people who died|
|num_of_sinj|number of people seriously injured in accidents|
|num_of_minj|Number of people with minor injuries as a result of accidents|
|num_of_reported_inj|Number of people reporting injuries to the police|
|year|year the acidents occurred|

### Problems
- 개별 파일을 하나로 합치는 문제
    - os 라이브러리와 for문을 사용해서 해결
    - 그러나 이 데이터의 경우 크기가 매우 작은 경우이기 때문에 데이터셋 각각의 크기가 커지는 경우에는 어떨지 모르겠다
- rename()시 행 값을 변경하는 문제
    - rename을 이용해 행과 열의 한글을 영어로 바꾸려고 하였으나 값이 바뀌지 않는 오류가 있었다.
    - 열의 경우 inplace를 설정하지 않았기 때문이었다.
    - 행의 경우, index가 각 행의 index를 의미하기 때문이었다. 따라서 rename()으로는 각각 인덱스의 행 값만 변경이 가능했다.
    - 따라서 replace()를 사용하여 행 값을 변경하였다.
