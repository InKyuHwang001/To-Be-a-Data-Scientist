# streamlit 기초

---

python 으로 브라우저에 UI 를 쉽게 만들 수 있는 라이브러리 입니다.

공식 사이트 : https://streamlit.io/

비슷한 라이브러리로 gradio 같은게 있습니다.

##  **0. 사용이유**

다른 사람에게 vscode나 jupyter notebook으로 보여주면 뽀대가 나지 않습니다. 그래서 사용합니다.



### **1. 설치**

```
pip install streamlit
```

또는 requirements.txt 에 아래와 같이 입력 (최신 버전은 [pypi](https://pypi.org/project/streamlit/) 확인)

```
streamlit==1.5.1
```

 

### **2. Test Code : helllo world** 

test.py 에 아래와 같이 입력합니다.

```
import streamlit as st

st.title("Streamlit Test")
st.write("hello world")
st.write("""
# MarkDown
> comment
- one
- two
- three
""")
```

그리고 파이참에서 Run/Debug 를 하면? 안됩니다. 

터미널에서 이 파이선 파일이 있는 경로로 이동 후에 아래 명령어로 실행을 합니다.

```
streamlit run test.py
```



![img](https://blog.kakaocdn.net/dn/cHsVCK/btrtxlCL4xa/nkb0sn7a2XYOgEuNAmzXYk/img.png)



port 는 8501 부터 시작해서 존재하면 +1 씩 올라가는 듯 합니다.

위 로그에 나온대로 localhost:8503 으로 접속해 봅니다. ( 이미 브라우저가 바로 떴을 겁니다. )



![img](https://blog.kakaocdn.net/dn/oPuHO/btrtwjrxnXm/YxH3aTtdrXvUi2qQGrHaBk/img.png)



웹 페이지가 떴습니다.

 

button, input box, file_uploader, image, checkbox, radio, selectbox 등등.. 많은 것들을 지원합니다.

 

### **간단히 맛보기**

```
import streamlit as st

st.title("Streamlit Test")

input_user_name = st.text_input(label="User Name", value="default value")
radio_gender = st.radio(label="Gender", options=["Male", "Female"])
check_1 = st.checkbox(label="agree", value=False)
memo = st.text_area(label="memo", value="")

if st.button("Confirm"):
    con = st.container()
    con.caption("Result")
    con.write(f"User Name is {str(input_user_name)}")
    con.write(str(radio_gender))
    con.write(f"agree : {check_1}")
    con.write(f"memo : {str(memo)}")
```

이 코드로 실행해 보면,



![img](https://blog.kakaocdn.net/dn/kJ12I/btrtABSBTKM/hRSPAbGyEFNP2KyQt5DOb1/img.gif)



 

버튼 클릭을 했을 때, 

python library등을 사용해 이것저것 실행 해 볼수 있겠죠.