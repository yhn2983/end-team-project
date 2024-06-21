## 前端班結訓專題    
我負責的部分為結帳功能、評價功能、訂單的呈現  
### 使用前需求  
需要先安裝 MySQL和Node.js
### 資料庫使用MySQL  
project_end(1).sql為資料庫的sql，將其匯入MySQL中即可使用。
### 後端使用Express.js    
透過SQL語法和資料庫作互動，進行CRUD。  
後端的檔案為 express-team  
將檔案下載後，先在主控台輸入 npm install，安裝所需要的node_module，  
接著在主控台輸入 npm run dev 讓程式開始運行 
### 前端使用Next.js   
使用fetch獲取後端API，來與後端進行互動  
前端的檔案為 next-team  
將檔案下載後，先在主控台輸入 npm install，安裝所需要的node_module，  
接著在主控台輸入 npm run dev 讓程式開始運行，  
注意，運行時請記得先運行後端程式，否則網站無法運行  

## 網站頁面   
### 一、結帳功能  
用useState將購物車取得商品的基本資料儲存成物件，用useState的setData將填寫的訂單資料儲存進Data中。  
用useEffect追蹤是否有優惠卷以及點數折抵，如果有使用優惠卷或點數作價格折抵，則對價格進行修改。
點選"議價按鈕"，則用fetch方式將資料送去後端，並存入議價資料表。  
點選"結帳按鈕"，用fetch方式將資料送去後端，並存入訂單資料表。
![image](https://github.com/yhn2983/end-team-project/blob/main/%E7%B5%90%E5%B8%B3%E9%A0%81%E9%9D%A2.png)  
### 二、買家議價功能    

![image](https://github.com/yhn2983/end-team-project/blob/main/%E8%B2%B7%E5%AE%B6%E8%AD%B0%E5%83%B9%E9%A0%81%E9%9D%A2.png)  
### 三、賣家議價功能   
![image](https://github.com/yhn2983/end-team-project/blob/main/%E8%B3%A3%E5%AE%B6%E8%AD%B0%E5%83%B9%E9%A0%81%E9%9D%A2.png)   
### 四、訂單呈現
![image](https://github.com/yhn2983/end-team-project/blob/main/%E8%A8%82%E5%96%AE%E9%A0%81%E9%9D%A2.png)   
