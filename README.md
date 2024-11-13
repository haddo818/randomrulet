!pip install streamlit 
import streamlit as st
import random 
import time

st.title("밥을 어디에서 먹으면 좋을까요? 랜덤 룰렛 ദി(⩌ᴗ⩌ )")
candidate = st.number_input("\( ´ ▽ ` )후보군의 개수를 지정해주세요!( ´ ▽ ` )ﾉ", min_value = 1, step = 1)
date = st.text_input("언제 식사하나요?(￣∠ ￣ )ﾉ", placeholder = "예: 내일 저녁") 
res = []
for i in range(int(candidate)):
  restaurant = st.text_input(f"{i+1}번째! 가고 싶은 식당을 입력하세요!", key=f"restaurant_{i}")
  if restaurant:
    res.append(restaurant)

if st.button("랜덤룰렛돌리기(*´∀｀*)ﾉ｡+ﾟ *｡"):
  if res:
    st.write(f"우리가 **{date}**에 갈 식당은...? 두구두구두구두구둑...")
    time.sleep(2)
    st.write(f"**{random.choice(res)}** 입니다!")
  else:
    st.write("추천할 식당을 입력해주세요.")

if st.button("다시 하기"):
  st.experimental_rerun()
