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
先用useState將預設的議價資料設為空陣列，  
使用useEffect使進入頁面時，去後端fetch符合買家id的議價資料，   
當點選個筆議價資料的"結帳"按鈕時，使用動態路由[id].js連結到個別議價資料的結帳頁面進行結帳。  
當點選"取消"按鈕時，進入fetch後端的delete api，將該筆議價資料刪除。  
![image](https://github.com/yhn2983/end-team-project/blob/main/%E8%B2%B7%E5%AE%B6%E8%AD%B0%E5%83%B9%E9%A0%81%E9%9D%A2.png)  
### 三、賣家議價功能    
先用useState將預設的議價資料設為空陣列，  
使用useEffect使進入頁面時，去後端fetch符合賣家id的議價資料，   
當點選個筆議價資料的"回覆"按鈕時，使用動態路由[id].js連結到個別商品議價資料的結回覆頁面進行回覆(如下圖)。    
當點選"同意"/"不同意"按鈕做回覆後，用fetch連結至後段的put api，去修改議價資料。
![image](https://github.com/yhn2983/end-team-project/blob/main/%E8%B3%A3%E5%AE%B6%E8%AD%B0%E5%83%B9%E9%A0%81%E9%9D%A2.png)   
### 四、訂單呈現   
用useState預設訂單資料(data)，  
使用useEffect使進入頁面時，去後端fetch符合賣家id的定訂單資料，在抓取到資料後，用setData修改useState的預設資料。   
最後用array.filter()將資料以未寄送、未完成、已完成等條件做篩選，最後用array.map()將資料呈現。  
![image](https://github.com/yhn2983/end-team-project/blob/main/%E8%A8%82%E5%96%AE%E9%A0%81%E9%9D%A2.png)     
### 五、評價功能   
使用Array(5).fill(1).map((v, i)=>{})生出五個星星，並設定每個星星的分數為i+1   
用const [rating, setRating] = useState(0)來記錄評分  
用const [hoverRating, setHoverRating] = useState(0)來記錄滑鼠懸停在第幾個星星   
用const [formData, setFormData] = useState({})來儲存最終的表單資料
設定兩個事件，分別為 onMouseEnter和onClick。  
當滑鼠onMouseEnter某個星星時，取得該星星的分數(setHoverRating)，並且讓分數小於該星星的呈現黃色  
當滑鼠onClick某個星星後，取得該星星的分數(setRating)，設定為評價的分數，並且同時更新表單資料(setFormData)
最後，當點選"送出評論"按鈕時，將formData用fetch送去後端。  
![image](https://github.com/yhn2983/end-team-project/blob/main/evaluateFlexClip.gif)
