# ASK-Crawler
ASK 프로젝트에 사용된 크롤링 api 입니다.

# 네이버 뉴스
## 필요 라이브러리
1. user_agent
2. requests
3. bs4
4. chardet
5. pandas   
## 크롤링 가능한 언론사
'국민일보', '미주한국일보', '서울경제', '파이낸셜뉴스언론사 선정', '에너지경제', '국제뉴스', '연합뉴스', '이데일리', '노컷뉴스', 'ZDNet Korea언론사 선정', '전남매일', '한국경제언론사 선정', '조선비즈언론사 선정', '뉴시스', '인사이트코리아', '미디어펜', '이코노믹리뷰', '한스경제', '뉴스투데이'
## input
query_list('str' or 'list') : 크롤링 키워드   
start_date('datetime') : 크롤링 시작 날짜   
end_date('datetime') : 크롤링 끝 날짜   
## output
df('dataframe')   
## 사용 예시
~~~
cl = news_crawler()
date_format = '%Y%m%d'

arg_list = ['20210101', '20210104']

start_date_str = arg_list[0]
end_date_str = arg_list[1]

query_list = ["아반떼", "쏘나타"]

start_date = datetime.strptime(start_date_str, date_format)
end_date = datetime.strptime(end_date_str, date_format)

df = cl.news_crawler(query_list, start_date, end_date)
print(df)
~~~
## 결과 화면
![image](https://user-images.githubusercontent.com/28096454/167677694-f71f06ee-98bb-4ccd-bc44-ba9febcd8ed0.png)

# 트위터
## 필요 라이브러리
1. selenium
2. bs4
3. pandas   
레포지토리에 포함된 chromedriver.exe가 설치된 크롬브라우저 환경과 맞지 않을 경우 [이곳](https://chromedriver.chromium.org/downloads)에서 다운로드 받아주시기 바랍니다.   

## input
query_list('str' or 'list') : 크롤링 키워드   
start_date('datetime') : 크롤링 시작 날짜   
end_date('datetime') : 크롤링 끝 날짜   

## output
df('dataframe')   

## 사용 예시
~~~
arg_list = ['20211101', '20211104']

start_date_str = arg_list[0]
end_date_str = arg_list[1]

query_list = ["아반떼", "쏘나타"]

cl = tweet_crawler()
date_format = '%Y%m%d'
start_date = datetime.strptime(start_date_str, date_format)
end_date = datetime.strptime(end_date_str, date_format)

result = cl.tweet_crawler(query_list, start_date, end_date)  # dataframe
~~~
## 결과 화면
![image](https://user-images.githubusercontent.com/28096454/167748384-055392a8-a06f-4d56-b519-4073bfde2818.png)

## Github profile of Team members :
강두원 : https://github.com/DW-K   
김소정 : https://github.com/Sojeong-Kim0915   
박태현 : https://github.com/Taehyuny   
노민하 : https://github.com/MinaRoh      
ASK프로젝트의 모든 기능은 [다음과 같은 주소](https://github.com/DW-K/A.S.K.-AnalysisStock-)에서 확인하실 수 있습니다.
