<!--
  템플릿은 아직 PR 작성이 익숙하지 않으신 분들을 위해서 제공하는 가이드입니다!
  리뷰어 또는 이 PR을 보게 될 다른 사람들이 이 PR을 보는데 참고할 수 있는 내용이 있다면 포함해서 작성해주시면 됩니다.
-->
## 회고록
<a href="https://velog.io/@jzo09/Notion-Cloning-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%EB%A5%BC-%EB%A7%88%EC%B9%98%EB%A9%B0...-%ED%9A%8C%EA%B3%A0" target="blank">회고록(ctrl + 클릭)<a>
## 📌 프로젝트 설명 
바닐라 JS만을 이용해 📄**노션을 클로닝**📄합니다.
기본적인 레이아웃은 노션과 같으며, 스타일링, 컬러값 등은 원하는대로 커스텀합니다.

## 👩‍💻 요구 사항과 구현 내용 

## 기본 요구사항
해당 프로젝트는 크게 **문서 목록**과 **편집기** 두가지 부분으로 구성되어있다. 

-  **문서 목록** 
   - [x] **루트 문서**들을 보여준다. 
   - [x] 루트 문서에 **하위 문서**가 있는 경우, 해당 루트 문서 아래에 트리 형태로 보여준다.
   - [x] **하위 문서 추가 기능** 
       문서 우측 `+` 버튼을 클릭하면 하위 문서로 새 문서를 생성하고 편집화면에 보여준다. 
       
- **편집기** 
  - [x] **자동 저장 기능** 
      저장 버튼을 따로 두지 않고 지속적으로 서버에 저장되도록 한다.  
- **공통** 
  - [x] **History API**를 이용해 **SPA** 형태로 만든다. 
  - [x] **루트 UR**L 접속 시엔 편집화면을 보여주지 않고 **메인 화면**을 보여준다. 
  - [x]  **/documents/{documentId}** 로 접속시, 해당 문서의 **편집화면**을 띄워준다. 

### UI-초기 화면📄

![초기화면](https://user-images.githubusercontent.com/66211721/132082185-f5079cfc-8367-4aa5-b344-17099a46ab05.png)

### UI-문서 목록📄 && 편집기📖

![ui 합](https://user-images.githubusercontent.com/66211721/132082370-d803121a-f725-489d-8ef8-92a9fac75122.png)

#### 기본 동작

![기본동작](https://user-images.githubusercontent.com/66211721/132047811-404a4ac6-ec95-4afb-ac11-8801a6e0d4c9.gif)


#### 페이지 하위 폴더 저장&&삭제
![페이지하위 문서 삭제 추가](https://user-images.githubusercontent.com/66211721/132047974-d1945a74-4463-4e76-89e5-fbc6213e1fcf.gif)




## 보너스 요구사항
- [x] **편집기 우측하단** 에 **🏠home** 버튼을 누르면  메인화면으로 간다.
- [x] **하위 문서 접기/펼치기 기능**
     - 문서 좌측 `▶` 을 클릭하면 하위 문서들을 접었다 펼칠 수 있다. 
- [x] **문서 삭제 기능** 
   - 문서 목록에서 각 문서 우측에는```―``` 버튼이 있다. 
   - 해당 버튼을 클릭하면   해당 문서를 삭제하고 , 휴지통에 들어가고, 업데이트 된 문서 목록을 보여준다.
- [x] **삭제, 추가 버튼에 마우스오버 메시지**를 띄워 사용자 편의성을 높인다.  
- [x] **휴지통 기능** 
   - 삭제 버튼을 누른 페이지들은 **로컬스토리지**에 저장되어 휴지통에 담는다.
   - 휴지통 클릭시 삭제한 페이지들이 나온다
   - 각 페이지 리스트들은 ♻(복구) ✂(삭제) 버튼을 갖는다.
   - ♻(복구)를 누르면 페이지의 title을 수정후 복구 시킨다.
   - ✂(삭제)를 누르면 영구삭제 확인 메세지와 함께 영구 삭제가된다.
   - 우측 하단에 **휴지통 비우기** 를 누르면 휴지통이 비워진다.

#### 🗑휴지통-기본 동작
![페이지삭제 휴지통삭제](https://user-images.githubusercontent.com/66211721/132048247-93bb67b3-1066-44c9-ac66-1febf3258d6f.gif)

#### 🗑휴지통-✂삭제 && 전체 삭제
![휴지통삭제 전체삭제](https://user-images.githubusercontent.com/66211721/132048446-ce10bd68-8acf-4130-9beb-fed63384ef06.gif)

#### 🗑휴지통-♻복구
![휴지통복구](https://user-images.githubusercontent.com/66211721/132048768-b340463c-3824-43e4-8d70-fbb43be15282.gif)

#### 🗑휴지동&&로컬스토리지 비교
![휴지통 로컬 비교](https://user-images.githubusercontent.com/66211721/132128590-83670838-4b95-401c-87f9-cd0bfbf517fc.gif)

## 개선사항
- [x] 첫 화면 구성
- [ ] 페이지 추가시 노션처럼 입력될때마다 렌더링
- [ ] 휴지통은 로컬스토리지로 구현이 되어있기 때문에 ♻(복구) 버튼을 누를시, 로컬스토리지에서 title값만을 받아 와서, api를 통해 다시 'post' 하여 id를 받아 새로운 문서가 된다.(기존 제목에서 수정을 해야만 복구가능) 




## ✅ 피드백 반영사항  

## ✅ PR 포인트 & 궁금한 점 
