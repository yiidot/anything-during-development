```java
WebSettings settings = webView.getSettings();
settings.setUseWideViewPort(true);  // 设置使用h5中的viewport设置
settings.setLoadWithOverviewMode(true); 
settings.setLayoutAlgorithm(LayoutAlgorithm.SINGLE_COLUMN); 

webview.getSettings().setTextZoom(100); // 设置字体不随系统字体大小变化

// 当webview可返回上一页时，禁用安卓默认的返回键
@Override
public boolean onKeyDown(int keyCode, KeyEvent event) {
   if(keyCode==KeyEvent.KEYCODE_BACK&&webView.canGoBack()){
       webView.goBack();
       return true;
   }
    return super.onKeyDown(keyCode, event);
}
```
