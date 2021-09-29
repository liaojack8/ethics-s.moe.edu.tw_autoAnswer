# 臺灣學術倫理教育資源中心 自動作答程式
[![Netlify Status](https://api.netlify.com/api/v1/badges/b394bd46-f325-4221-9662-defc1b1f9a36/deploy-status)](https://app.netlify.com/sites/fervent-mestorf-4d39a5/deploys)

目標網站：https://ethics-s.moe.edu.tw/exam/

說明：登入完畢之後就可以執行，建議多個人一起合作，不然要拿85%以上的答對率要蠻久的時間

用法提示：在網址列輸入 或是 加入書籤

# 執行畫面
![image](https://i.imgur.com/p6eUWjL.png)

# 執行用程式碼
```javascript
javascript:(function(){var f=document.createElement('script');f.setAttribute('type','text/javascript');f.setAttribute('src','https://fervent-mestorf-4d39a5.netlify.app/main.js');document.getElementsByTagName('head')[0].appendChild(f)})()
```

# CORS問題
![](https://i.imgur.com/xWBIi0N.png)
用了沒反應的應該都是CORS問題, 但我懶得弄了, 畢竟也就用這麼幾次, 大家就服用插件解決吧
https://chrome.google.com/webstore/detail/allow-cors-access-control/lhobafahddgcelffkeicbaginigeejlf

# 手動執行不透過UI 的範例


作答頁面 要執行的函數

```
YEE.readAns('[{"title":"下列何種利益為研究人員之主要利益？","select":"1"}]') // 讀取答案紀錄 沒答案就先忽略跳過
YEE.answer($(document))
YEE.analysis_Apart($(document))
YEE.getJsno_Str_data()
```

測驗結果頁面 要執行的函數

```
YEE.readAns('[{"title":"下列何種利益為研究人員之主要利益？","select":"1"}]') // 如果是第一次執行 那只需 readData 因為你也沒有答案
YEE.readData('[{"title":"研究中的利益衝突有幾種類型，「不」包含下列何種利益衝突類型？","select":"2"},{"title":"下列何種利益為研究人員之主要利益？","select":"1"},{"title":"下列何者不是干擾「科學研究的廉正性」之內涵？","select":"1"},{"title":"下列何者是醫學研究領域常見的次要利益？","select":"1"},{"title":"下列何者不是管理利益衝突的重要性？","select":"4"}]')
YEE.analysis_Bpart($(document))
YEE.getJsno_Str_ans()
```

ansJSON 請妥善保存!
