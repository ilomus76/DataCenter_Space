>df_tidy = df.melt( 
>    id_vars='지역',     # 그대로 유지될 컬룸 지정 
>    value_vars=['2021','2022','2023'], # '녹여서'행으로 변환될 컴룰명들.(지정하지 않으면 모두) 안쓰면 다.. 
>    var_name='연도', #기존 컬룸명이 값이된 컬룸명의 이름지정 
>    value_name = '매출액' #값들이 들어간 컴룸의 이름지정 
 
) 
df_tidy

>#지역별, 연도별로 묶어서 총매출액의 총합 , 평균을 집계한 데이터프레임으로 변경 
>df2 = df.pivot_table( # pivot 은 돌리기만 하는것이고 pivot_table은 집계까지 하는 것 
>    index = '지역', 
>    columns = '연도', 
>    values = '판매액', 
>    aggfunc=['sum','mean'] 
 
> )  
> df2


> 지역별, 연도별로 묶어서 총매출액의 총합 , 평균을 집계한 데이터프레임으로 변경 
> df2 = df.pivot_table( # pivot 은 돌리기만 하는것이고 pivot_table은 집계까지 하는 것 
>    index = '지역', 
>    columns = '연도', 
>    values = '판매액', 
>    aggfunc=['sum','mean'] 
> 
> ) 
> df2 
