# 錯誤排除紀錄 debug

| 錯誤訊息 | 解決辦法 | 錯誤畫面 |
|---------|--------|---------|
| Failed to load bundle(URL) with error:(Unable to resolve module '../img.png') ... | **< Root Cause >**<br/>讀取的圖片路徑錯誤<br/>**< Solve >**<br/>確認圖片路徑，要以 **讀取圖片的檔案所在路徑** 為起始位置，而要加入的圖片路徑為 **讀取圖片的檔案所在路徑**/圖片路徑，而 **讀取圖片的檔案所在路徑** 可以用 **.** 表示。<br/>e.g.: 圖片路徑為`doc/pj/image/img.png`，讀取圖片的檔案所在路徑為`doc/pj/App.js`，所以圖片路徑就標示為`./image/img.png` | ![Fail Load image](/images/debug/fail_load_bundle.png) |
| No bundle URL present... | **< Root Cause >**<br/>不明錯誤造成無法找到.jsbundle檔案<br/>**< Solve >**<br/>刪除`pj/ios/build/`資料夾後重build專案 | ![no bundle url](/images/debug/no_bundle_url_present.png) |
