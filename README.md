**안드로이드 1주차 커리큘럼**
안드로이드 기본 구성과 개발 환경을 이해하고 안드로이드 화면을 구성하기 위해 필요한 요소들을 이해한다. 특히 레이아웃과 뷰컨테이너 그리고 주요 위젯들의 특징 및 사용 방법을 이해한다.

1. **안드로이드의 이해와 환경**
- 안드로이드 개념 : 안드로이드, 세계에서 가장 인기있는 모바일 플랫폼
	 - 글로벌 파트너쉽과 대규모의 사용자
	 - 빠른 기술 혁신 : 사용자와 개발자들에게 최신의 기술을 제공
	 - 강력한 개발 프레임워크 : 다양한 타입의 기기에 맞춰 UI를 자동으로 적용
	 - 오픈 마켓 

	
 - 안드로이드 구성요소 :
			①Activity ② Service  ③ Content Provider ④ Broadcast Receiver
			
 - 안드로이드 버전별 특징

 -  안드로이드 개발환경
 
	- 안드로이드 버전별 특징
	- 안드로이드 개발환경
	
2. **안드로이드 개발 환경 구성**

 - 안드로이드 스튜디오 설치 및 화면 구성
 - 에뮬레이터 실행하기
 - 실제 안드로이드 기기 연동하기

3. **안드로이드 첫 번째 프로젝트 실행하기**

 - 프로젝트 생성
 - 프로젝트 실행
 - 프로젝트 구성 요소의 이해

4. **액티비티 살펴보기**

- **액티비티 이해**

	 - 액티비티(Activity)는 **사용자 인터페이스 화면**을 관리하는 컴포넌트이다. 액티비티 역할을 하기 위해서는 Activity 클래스를 상속해야 하며, 액티비티가 기본적으로 가지고 있는 생명주기 메소드를 재정의해서 원하는 기능을 구현해야 한다.
 
	 - main메소드를 호출하는 프로그램과 달리, 안드로이드 시스템은 엑티비티 객체에서 **특정한 콜백함수를 호출**함으로써 특정 생명주기 구역에 대응하여 코드를 시작한다.


	 - 앱에서 액티비티를 이용하려면 **AndroidManifest에 액티비티와 속성들**을 선언해야 한다.

- **액티비티 생명주기 메소드**
	- **onCreate() :** <br>
      -- 액티비티가 **생성될 때** 호출되며 **사용자 인터페이스 초기화**에 사용<br>
      -- 전체 생명주기 안에 **오직 한번만** 일어나야할 로직을 여기서 수행한다.
	
	- **onStart() :** <br>
			-- 액티비티가 사용자에게 **보여지기 바로 직전**에 호출 <br>
			-- 빠르게 끝남

	- **onResume() :** <br>
			-- 액티비티가 사용자와 **상호작용하기 바로 전**에 호출됨 <br>
			-- onPause로 인하여 릴리즈된 컴포넌트를 **초기화** 하는데 적당한 메소드
	
	- **onPause() :** <br>
			-- **다른 액티비티가 보여질 때** 호출됨(액티비티를 떠날때)<br>
			-- **리소스를 릴리즈** 하고 **간단한 데이터를 저장**하기에 적당한 메소드(ex) camera, 스레드 중지 등...<br>
			-- 메소드가 끝나기전에 부하가 큰 작업은 다 끝나지 않을 수 있기 때문에 그런 작업들은 onStop에서 수행한다 (ex) DB 트랜잭션<br>
	
	- **onStop():**<br>
			-- 액티비티가 더이상 사용자에게 **보여지지 않을 때** 호출됨<br>
			-- DB에 저장하는 작업, Broadcast Receiver 해제와 같은 작업 수행<br>
			-- onRestart로 다시 액티비티로 복귀<br>

 	- **onDestroy():** <br>
			-- **액티비티가 소멸될 때** 호출됨 	 <br>
      -- finish() 메소드가 호출되거나 시스템이 메모리 확보를 위해 액티비티를 제거할   때 호출됨.<br>

 	- **onRestart():** 	<br>
			-- 액티비티가 멈췄다가 **다시 시작되기 바로 전**에 호출됨.

5. **안드로이드 기본 위젯 살펴보기**
- **텍스트뷰** : 텍스트뷰는 화면에 고정된 텍스트 문자열을 표시하는 뷰이다. 이 뷰의 문자열은 사용자가 수정할 수 없다.<br>
	- **상속계층도** 

				java.lang.Object
				  ↳ android.view.View
				    ↳ android.widget.TextView
    
	- **이미지**
		  ! [textView](Textview.png)



- **에디트텍스트** : 에디트텍스트는 사용자에게 입력을 받을 수 있는 뷰이며, 입력 기능을 제외하고는 텍스트뷰와 동일하다.
	- **상속계층도**

			java.lang.Object
			  ↳ android.view.View
			    ↳ android.widget.TextView
			      ↳ android.widget.EditText
   
	- **이미지**
		  ! [textView](Textview.png)


- **버튼** :  버튼은 누를 수 있는 버튼들의 가장 일반적인 형태로 텍스트를 누를 수 있게 해준다. 
	- **상속계층도** 

			java.lang.Object
			  ↳ android.view.View
			    ↳ android.widget.TextView
			      ↳ android.widget.EditText


	 이미지버튼은 이미지를 설정할 수 있는 버튼이다.
	- **상속계층도** 
	
					>java.lang.Object
					   ↳ android.view.View
					    ↳ android.widget.ImageView
					     ↳ android.widget.ImageButton
					 
	- **주요 코드** : android:src="@drawable/ic_launcher" : 이미지 지정
		

- **이미지뷰** : 이미지를 보여주기 위한 뷰이다.
	- **상속계층도** 
		
					> java.lang.Object
					 ↳ android.view.View
					  ↳ android.widget.ImageView

	- **주요 코드** :
		-- android:contentDescription="Image_view" : 이미지를 보여줄 수 없을때 대체할 문자열<br>
		-- android:src="@drawable/ic_launcher" : 이미지 지정<br>
		
- **체크박스** :  "체크됨"과 "체크되지 않음"이라는 두 개의 상태를 표시하는 버튼이다.
	- **상속계층도** 
	
					>java.lang.Object
					 ↳ android.view.View
					  ↳ android.widget.TextView
					   ↳ android.widget.Button
					    ↳ android.widget.CompoundButton
					     ↳ android.widget.CheckBox

	- **주요 코드** :
		 -- android:text="check" : 체크박스 옆에 나오는 문자열이다.<br>
		 -- android:checked="true" : 체크된 상태<br>
		
- **토글버튼** : 전원 스위치처럼 "ON", "OFF"를 표시하는 버튼이다.
	- **상속계층도** 
				
					> java.lang.Object
					 ↳ android.view.View
					  ↳ android.widget.TextView
					   ↳ android.widget.Button
					    ↳ android.widget.CompoundButton
					     ↳ android.widget.ToggleButton
	  
	- **주요 코드** :
		 -- android:textOn="On" : 토글버튼이 ON일때 표시되는 문자열<br>
		 -- android:textOff="Off" : 토글버튼이 OFF일때 표시되는 문자열<br>
		 
- **스위치** : 두 개의 상태를 표시하는 버튼이다.
	- **상속계층도** 
	
				> java.lang.Object
			  	 ↳ android.view.View
			   	  ↳ android.widget.TextView
			     	   ↳ android.widget.Button
				    ↳ android.widget.CompoundButton
				     ↳ android.widget.Switch

	- **주요 코드** :
		 -- android:textOn="On" : 토글버튼이 ON일때 표시되는 문자열<br>
		 -- android:textOff="Off" : 토글버튼이 OFF일때 표시되는 문자열<br>
		 -- android:checked="true" : 체크된 상태<br>
		 
- **라디오버튼** :  여러 개 중에서 한 개를 선택할 수 있는 선택 버튼이다. 라디오 버튼은 일반적으로 라디오 그룹(RadioGroup)으로 묶어서 사용한다.
	- **상속계층도** 
	
					> java.lang.Object
					 ↳ android.view.View
					  ↳ android.widget.TextView
					   ↳ android.widget.Button
					    ↳ android.widget.CompoundButton
					     ↳ android.widget.RadioButton
	
	- **주요 코드** :
		 -- android:checked="true" : 체크된 상태<br>
		 
- **스피너** : 사용자가 여러 개의 아이템 중에서 한 개를 선택할 수 있게 해주는 뷰이다. 
		- 아이템들은 어댑터나 배열로 설정 가능<br>
		- getSelectedView() 메소드로 선택한 텍스트를 가지고 올 수 있음<br>
		- XML의 android:prompt 속성에는 반드시 문자열 자원 참조를 설정해야 함<br>
		
	- **상속계층도** 
	
				> java.lang.Object
				 ↳ android.view.View
				  ↳ android.view.ViewGroup
				   ↳ android.widget.AdapterView <T extends android.widget.Adapter>
				    ↳ android.widget.AbsSpinner
				     ↳ android.widget.Spinner
         
- **시크바** :   ProgressBar를 확장하여 사용자가 터치로 상태를 변경할 수 있도록 한 뷰이다. 시크바는 볼륨 조절이나 화면 밝기 조절 등에 사용할 수 있으며 발생된 이벤트는 SeekBar.OnSeekBarChangeListener 인터페이스를 통해 처리할 수 있다.

	- **상속계층도** 
				  			
					> java.lang.Object
					  ↳ android.view.View
					    ↳ android.widget.TextView
					      ↳ android.widget.Button
						↳ android.widget.CompoundButton
						  ↳ android.widget.RadioButton

	- **주요 코드** :
		 -- android:max="100" : 시크바의 최대 값<br>
		 -- android:progress="50" : 시크바의 현재 값<br>
		 -- android:secondaryProgress="75" : 시크바의 기준 값이며 사용자에게 시크바를 어느 정도 움직이는 것이 적당한지를 보여주기 위한 용도로 사용할 수 있다.<br>

- **카드뷰** : - 둥근 테두리와 그림자를 가진 FrameLayout
	       - elevation으로 그림자 효과를 줄 수 있다.
	       
	- **상속계층도** 
				  			
					
					> java.lang.Object
					  ↳ android.view.View
					    ↳ android.view.ViewGroup
					      ↳	android.widget.FrameLayout
						↳ android.support.v7.widget.CardView
					
	- **주요 코드** :
		-- card_view:cardCornerRadius : 모서리의 반지름<br>
		-- card_view:cardBackgroundColor : 카드의 배경색 지정<br>
		
	- **종속성 추가** :
	
				> dependencies {
    						...
    						compile 'com.android.support:cardview-v7:21.0.+'
												  }
	
- **자동완성 텍스트뷰** : 자동완성 텍스트뷰는 사용자 입력을 자동으로 완성해주는 텍스트뷰(TextView)이다. 이름이 텍스트뷰이기는 하지만 실제 속성은 에디트텍스트(EditText)에 더 가깝다. 사용자가 문자열 입력 시 자동으로 보여줄 문자열들은 ArrayAdapter를 사용해서 자동완성 텍스트뷰에 설정해야 한다. 

	- **상속계층도**
	
				> java.lang.Object
  				  ↳ android.view.View
   				   ↳ android.widget.TextView
				    ↳ android.widget.EditText
				     ↳ android.widget.AutoCompleteTextView
				     
	- **주요 코드** : -- android:completionThreshold="2" : 사용자가 입력한 글자가 몇 글자일 때 문자열 리스트를 보여줄지를 지정하는 속성이다.<br>
	

- **멀티 자동완성 텍스트뷰** : 멀티 자동완성 텍스트뷰는 사용자 입력을 자동으로 완성해주는 텍스트뷰(TextView)이다. 멀티 자동완성 텍스트뷰는 자동완성 텍스트뷰와 한 가지 차이점을 제외하고는 동일하다.<Br>
		--여러 개의 단어 완성<br>
		--토크나이저 설정 필요(CommaTokenizer: 쉼표로 단어들을 구분)<Br>
		자동완성 텍스트뷰는 한 개의 단어만을 자동으로 완성시켜 주며, 멀티 자동완성 텍스트뷰는 여러 개의 단어를 자동으로 완성시켜 준다.<br>

	- **상속계층도**
	
				> java.lang.Object
  				  ↳ android.view.View
   				   ↳ android.widget.TextView
 				    ↳ android.widget.EditText
				     ↳ android.widget.AutoCompleteTextView
				      ↳ android.widget.MultiAutoCompleteTextView
