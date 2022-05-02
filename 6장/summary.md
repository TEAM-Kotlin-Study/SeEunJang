:ghost: kotlin 6장 정리 :ghost:
=============
### 배운 점 
-------------
1. FloatingActionButton은 벡터 이미지를 표현할 수 있다.
2. timer 기능
  * 워커스레드 : 오래 걸리는 작업을 보이지 않는 곳에서 처리함. 이는 UI를 조작할 수 없다. 따라서 runOnUiThread() 메서드를 사용해야 함.
3. java로 개발할때는 TextView 객체를 받아서 setText를 이용해 텍스트 뷰에 있는 text 내용을 바꾸는걸 배웠는데, Kotlin을 이용하면 binding.위젯id.text = "$수정 텍스트 내용"으로 변경할 수 있다. 
