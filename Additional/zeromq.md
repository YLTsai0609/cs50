# Ref

[快速且高效能的分散式非同步通訊函式庫-ZMQ](http://www.runpc.com.tw/content/content.aspx?id=109829)

[ØMQ wiki](https://zh.wikipedia.org/wiki/%C3%98MQ)

1. ZeroMQ支援了多client對多worker的分散式連線模式，並且能夠以不需要中繼站(message broker)的方式進行訊息傳輸

2. 具有message broker訊息中樞的通訊模型有其缺點，當broker死掉時，服務停擺，因此ZeroMQ實作了一套去中心化的通訊模型(但ZeroMQ library本身仍然支援borker的通訊模型，如果你想要建立的話)

3. ZeroMQ的吞吐量非常驚人，類似功能的通訊框架有MSMQ, ActiveMQ, RabbitMQ，ZeroMQ完全屌打這三者，接收量為10倍，傳輸量為20倍

4. [ZeroMQ官方QA回答了"為什麼基於TCP建立的框架"會比TCP本身速度還要快?](http://wiki.zeromq.org/area:faq#toc6) - ZeroMQ官方表示，避免冗余的封包封裝/拆解可以加速很多，換句話說，只要你先把要拆的跟要封的存起來，你就可以快超多，這招術叫做message batching

5. ZeroMQ致力於發展自己的通訊協定，雖然還沒成功，但library已經到了大版號19版，且有一間公司專門做這個提供技術服務，客戶跨足Facebook, Microsoft

6. ZeroMQ除了幾乎支援任何程式語言之外，除了網路通訊，連進程/線程之間的通訊也處理了，可以看出平行化運算的野心

7. 歷史故事的部分，2010年3月30日，AMQP的最初設計者iMatix公司的執行長Pieter Hintjens宣布iMatix將退出AMQP工作群組，而且為了簡單得多，快的多的ZeroMQ，將不支援 可能發布的AMQP/1.0，AMQP是其他分散式訊息傳輸框架都會實作的通訊協定(RabbitMQ, ActiveMQ, ...)

8. ZeroMQ致力於發展自己的通訊協定，因此可以想像ZeroMQ把TCP, UDP拆開，做成自己想要的樣子，他們的通訊協定還在發展中，但基本上已經比TCP還要快了，ZeroMQ的官方文件也放置了截至目前為止關於[通訊協定的草案及歷史](https://rfc.zeromq.org/)

9. 正如第8點所說，ZeroMQ擷取了部分TCP的優點，並讓其更簡單易用，其中一項就是client與server的啟動順序不再重要，client先啟動也可以，大不了就是連不到server，內容會站存在zeromq中
