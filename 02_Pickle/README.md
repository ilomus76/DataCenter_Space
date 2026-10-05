# Pandas 자료형 공부 
> Pickle 파일 저장하기 
파이썬 객체(값 여러가지 가지고 있는 것 , padas, series 도 객체) 를 그대로 저장해주는 표준모듈-설치할 필요없다. 
문자열을 저장하는 일반적인 파일입출력과 다르게 피클파일은 객체를 그대로(binary 데이터)로 저장할 수 있어서 AI, ML 의 학습된 모델(특성값,가중치(곡선의 기울기)) 을 저장하는 용도로 많이 사용됨 

> 사용방법 

#1. 피클로 객체 저장하기( dump ) 
import pickle  
 
# 저장할 파이썬의 데이터 - 어떤 타입이든 저장  
person = {'name':'sam','age':20,'hobby':['swimming','running']} 
 
# 피클파일에 딕셔너리를 통으로 저장하기  
# with open('./save_files/person.pickle) 
with open('./save_files/person.pkl','wb') as file: 
# with open('./save_files/person.p) 
	pickle.dump(person,file) 
 
#2.저장된 피클파일 읽어오기 (load) 
with open('./save_files/person.pkl','rb') as file: 
	p = pickle.load(file) 
 
#불러온 데이터 출력 
print(p['name'],p['age'],p['hobby']) 
 
sam 20 ['swimming', 'running'] 
 
#판다스의 데이터프레임도 그대로 피클파일로 저장하고 열기 
with open('./save_files/score.pickle','wb') as file: 
	pickle.dump(df,file) 
 
with open('./save_files/score.pickle','rb') as file: 
	df_a=pickle.load(file) 
 
df_a   
 
