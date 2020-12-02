






# Ref

[http wiki](https://zh.wikipedia.org/wiki/%E8%B6%85%E6%96%87%E6%9C%AC%E4%BC%A0%E8%BE%93%E5%8D%8F%E8%AE%AE)

[mime 多用途網際網路郵件擴展 wiki](https://zh.wikipedia.org/wiki/%E5%A4%9A%E7%94%A8%E9%80%94%E4%BA%92%E8%81%AF%E7%B6%B2%E9%83%B5%E4%BB%B6%E6%93%B4%E5%B1%95)

[無狀態協議 wiki](https://zh.wikipedia.org/wiki/%E6%97%A0%E7%8A%B6%E6%80%81%E5%8D%8F%E8%AE%AE)

[如何理解HTTP協議的 「無連接，無狀態」 特點？](https://kknews.cc/zh-tw/code/9nxbmj8.html)

[HTTP是一个无状态的协议。这句话里的无状态是什么意思?](https://www.zhihu.com/question/23202402)

[REST wiki](https://zh.wikipedia.org/wiki/%E8%A1%A8%E7%8E%B0%E5%B1%82%E7%8A%B6%E6%80%81%E8%BD%AC%E6%8D%A2)

[What is a REST API](https://www.youtube.com/watch?v=SLwpqD8n3d0)

[REST API concepts and examples](https://www.youtube.com/watch?v=7YcW25PHnAA)

Book - 精通Python Chp9 Web開展

# 專有名詞

縮寫(全名)|中翻|備註
-----|-----|-----
HTTP(Hypertext Transfer Protocol)|超文字傳輸協議||
HTML(Hypertext Makeup Language)|超文字標記語言|現今網頁表示法|
URL(Uniform Resource Locator)|統一資源定位器|server所開放的資源，供client使用(CRUD)|
# http actions

http的8種操作

| action | meaning |note|
|-------|-------|----|
| GET | 向指定資源發出**顯示**請求，讀取資料，不應有副作用，參數需透過qeury string帶入 |Read|
|HEAD|向指定資源發出**顯示**請求，但伺服器不回傳資源的本文||
|POST|向指定資源提交資料(例如表單、檔案)|Create|
|PUT|向指定資源位置上傳最新內容|Update|
|DELETE|請求伺服器刪除標誌資源|Delete|
|TRACE|回顯伺服器收到的請求|
|OPTIONS|使日福氣回傳該資源所支援的所有HTTP請求方法||
|CONNECT|HTTP/1.1協定中預留給能夠將連接改為隧道方式的代理伺服器，通常用於SSL加密伺服器||

http server至少應該實作GET以及HEAD方法，其他方法都是可選

基本資料操作應包含Create, Read, Update, Delete
合稱為(CRUD Operations)

# http version

大部分都是向下相容的

| version number | note  |
|----------------|-------|
| 0.9          | 已過時，只接受GET |
|1.0|第一個在通訊中指定版本號的HTTP協定版本|
|1.1|預設採持續連接，優化快取處理，頻寬最佳化，安全性等|
2|2015年5月作為網際網路標準正式發佈|

持續連線 : 0.9和1.0 TCP連線在每次請求/回應之後關閉，1.1中，一個連接可以重複多個請求，可以大大減少等待時間(建立連線)，因為雙方不需要重新執行TCP三項交握

``` 

TCP 傳輸控制協定(Transmisson Control Protocol) 是一種通訊傳輸協定，在OSI模型中，他完成第4層傳輸層所指定的功能

三項交握(Three way handshake)，是一種建立虛擬連線的方式
```

# http features

1. 支持client/server模式
2. 簡單快速
3. 靈活
4. 無連接
5. 無狀態

## 無連接

無連接的含義是限制每次連接只處理一個請求。伺服器處理完客戶的請求，並收到客戶的應答後，即斷開連接。採用這種方式可以節省傳輸時間。

why?

早期這麼做是因為HTTP產生於網際網路，HTTP server胥杳同時面向全世界數十萬，數百萬的網頁訪問，但client端與server端之間交貨數據的間歇性較大(傳輸具有突發性，瞬時性)，並且網頁瀏覽行為非常發散，因此大部分通道實際上會很閒，因此衍生出一種設計理念 **請求時連接，請求玩釋放，以盡快將資源釋放出來服務其他client**

keep alive in http 1.1?

由於網頁日益複雜，有很多嵌入圖片，美訪問都要建立一次TCP連接，很慢，所以有了keep alive，市面上大部分的Web server(iPlanet, IIS, Apache)都支持Http Keep-Alive

## 無狀態

無狀態指的是協議對事務處理沒有記憶能力，server不知道client是什麼狀態，缺少狀態意味著如果後續處理需要前面的訊息，就要重傳，這樣導致每次連接傳送的資料量增大，然而，好處是server不需要先前的資訊，他就可以快速應答，然而client及server進行動態互動的Web應用程式出現之後，HTTP無狀態的特性就阻礙了這類的應用程式，例如簡單的購物車，也必須知道使用者之前選了什麼商品，因此各種保持HTTP連線狀態的技術就誕生了，**Cookie**, **Session**, **cache**

### Cookie

可以保持資訊到下一次使用者server之間的session，例如

1. 判斷使用者是否已經登陸過網站
2. 購物車應用，知道你在不同網頁之間點擊了什麼
3. 這玩意兒存在client端

### Session

1. 可以做到cookie做得到的事
2. 這玩意兒存在server端

## MIME

MIME(Multipurpose Internet Mail Extension) 多用途網際網路郵件擴展，原先只是聲明電子郵件裡面可以放什麼，之後因為太實用被納入HTTP協定中，以下是常用的Content-Type

`Content-Type: [type]/[subtype]; parameter`

type : 

1. Text
2. Multipart
3. Application
4. Message
5. Image
6. Audio
7. Video

subtype : 

1. text/plain 
2. text/html
3. application/xhtml+xml
4. image/gif
5. image/jepg
6. image/png
7. video/mpeg
8. application/octet-stream(任意的二進位數據)
9. application/pdf
10. application/msword(microsoft文件)
11. application/vnd.wap.xhtml+xml
12. application/xhtml+xml
13. message/rfc822
14. multipart/alternative(html mail & html 純文本)
15. application/x-www-form-urlencoded(使用HTTP的POST提交的表單)

[更多可參閱MIME wiki](https://zh.wikipedia.org/wiki/%E5%A4%9A%E7%94%A8%E9%80%94%E4%BA%92%E8%81%AF%E7%B6%B2%E9%83%B5%E4%BB%B6%E6%93%B4%E5%B1%95)

# REST

1. Representational State Transfer，由Roy Thomas Fielding博士提出，是一種全球資料訊網軟體架構**風格**

2. REST是一種風格，http是一種通訊協定

3. 符合這種風格的網路服務，我們會稱為REST 網路服務 or Restful 網路服務

4. 由於REST模式和SOAP以及XML-RPC比起來更簡潔，因此越來越多Web服務採用REST風格設計與實現，例如Amazon.com以及yahoo.com的web服務

5. 透過Restful API，可以輕易的透過HTTP request進行CRUD(正常的HTTP server是不允許client端進行寫入，更新，刪除的)

6. 在Rest出現之前，每個公司/開發者寫API的方式不一，都有自己的風格，直到Roy Thomas提出一種容易維護的設計風格

可以透過Postman以及Restclient在Twitter上Po文, check 

[What is a REST API](https://www.youtube.com/watch?v=SLwpqD8n3d0)

[REST API concepts and examples](https://www.youtube.com/watch?v=7YcW25PHnAA)


CRUD

restful action|http action|note
-----|-----|-----
Read|HEAD|get information about the source, not the content
Read|GET|get whole bunch of html response
Create|POST|create infor to the server
Update|PUT|update infor with existing key in server
Delete|DELETE|delete information in server
















