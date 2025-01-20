# OCR_Android

#### 📢 TessTwo를 활용하여 카메라 앱으로 촬영된 사진의 문자를 인식하는 어플리케이션
🖥️ 개발환경 : Java, Android Studio, Tesseract(TessTwo)  

<br>

📜 Tesseract ?
> OCR 광학 문자 인식 오픈 소스 라이브러리.    
> 다양한 OS를 지원하기 위한 엔진으로 무료 소프트웨어이며 Apache 라이선스이다.

<br>

### 영상 인식 알고리즘
1. Preprocessor
> 최초 들어온 이미지를 처리하기 위해 히스토그램 스트레칭과 히스토그램 평활화, 이진화 작업과 영상 작업을 통하여 보다 효율적인 출력물을 얻기 위한 전처리 작업.   
> 예시: 히스토그램, 이치화, 역상
2. Segmentation
> Preprocessor 작업을 거친 뒤 이미지에서 글자 단위로 혼합의 Text를 분류하는 작업

<br>

📜 Tesseract 원리
> 오프라인 문자인식 기법으로 입력된 input 이미지의 특징점을 추출하고 그것을 사용하여 문자를 인식한다.
> 기본적으로 상위의 Preprocessor와 Segmentation 과정을 거쳐 나온 이미지를 시녕망 기법과 template matching 기법을 사용하여 input 이미지를 인식하고 출력한다.

<br>

📜 Training
> Tesseract는 인식률 향상을 위해서  Training 데이터를 적용할 수 있다.
> 미리 학습 시켜놓은 데이터들을 Tesseract 데이터 베이스에 저장하여 글자와 트레이닝 데이터와 유사율을 비교하여 인식 결과를 반환한다.

<br><br>

1. ProgressCircleDialog.java & res>values>styles 의 newDialog 필수값

&nbsp;&nbsp;&nbsp; (MainActivity.java)
1. dispatchTakePictureIntent : 기본 카메라 어플 실행 및 사진 촬영
2. DrawOn : 텍스트 사각형 그리기
3. rotateImage : 사진 회전
4. PermissionCheck : 특정 버전 이상일 경우에는 권한 체크 및 요청 
5. Tesseract : 언어 파일 경로 설정 후 트레이닝데이터가 카피되어있는지 확인, TessBaseAPI 호출

