# CameraManager
**Extends**: 

네이티브 카메라에 대한 라이브러리이다.

<br/>

## Methods

### openFilePicker( callback )

디바이스 앨범에서 이미지를 선택하고 선택된 이미지를 반환한다.

- `callback` \<Function> 콜백함수

```js
CameraManager.openFilePIcker(function(img) {
    console.log(img); //base64 인코딩된 이미지
});
```

<br/>
<br/>
