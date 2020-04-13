# TabViewManager
> **Extends**: 

탭이 있는 화면을 일괄처리하는 클래스

<br/>

## Methods

### addTab( tabInfo )

탭을 추가합니다.

* **Parameters**: 
	* **`tabInfo`** {Object} 탭정보 ex) {name:'개인외국인기관', url:'lay/view/Mhmts01000_T01.lay', tabId:'Mhmts01000_T01', data: 'data'}

<br/>

### afterTabChanged( oldTab, newTab, reload )

탭이 변경된 후의 이벤트입니다.

* **Parameters**: 
	* **`oldTab`** {Object} 변경전 탭
	* **`newTab`** {Object} 변경된 탭
	* **`reload`** {Boolean} 다시 로드되는지 여부(true: 다시로드 / false: 처음로드)

<br/>

### beforeTabChanging( oldTab, newTab, reload )

탭이 변경되기전의 이벤트입니다.

* **Parameters**: 
	* **`oldTab`** {Object} 변경전 탭
	* **`newTab`** {Object} 변경될 탭
	* **`reload`** {Boolean} 다시 로드되는지 여부(true: 다시로드 / false: 처음로드)

<br/>

### changeTab( tabId, data )

탭 선택을 변경합니다.

* **Parameters**: 
	* **`tabId`** {String} 변경할 탭Id
	* **`data`** {Object} 탭변경시 전달할 data

<br/>

### getActiveTab()

활성화된 탭을 가져옵니다.

* **Returns**: Object:

<br/>

### getActiveView()

활성화된 탭의 뷰를 가져옵니다.

* **Returns**: Object:

<br/>

### initManager( tabView, rbManager )

탭매니저를 init합니다.

* **Parameters**: 
	* **`tabView`** {ATabView} 탭뷰
	* **`rbManager`** {RadioBtnManager} 탭뷰를 컨트롤할 라디오버튼매니저

<br/>

### tabChanging( oldTab, newTab, reload )

탭이 변경되는중의 이벤트입니다.

* **Parameters**: 
	* **`oldTab`** {Object} 변경전 탭
	* **`newTab`** {Object} 변경되는 탭
	* **`reload`** {Boolean} 다시 로드되는지 여부(true: 다시로드 / false: 처음로드)

<br/>
<br/>
