# Ref

[REST wiki](https://zh.wikipedia.org/wiki/%E8%A1%A8%E7%8E%B0%E5%B1%82%E7%8A%B6%E6%80%81%E8%BD%AC%E6%8D%A2)

[WebRTC](https://zh.wikipedia.org/wiki/WebRTC)

[發佈/訂閱模式 vs 觀察者模式](https://notfalse.net/11/pub-sub-pattern)

[ZeroMQ wiki](https://zh.wikipedia.org/wiki/%C3%98MQ)

[RabbitMQ wiki](https://zh.wikipedia.org/wiki/RabbitMQ)

[hadoop wiki](https://zh.m.wikipedia.org/zh-tw/Apache_Hadoop)

[spark wiki](https://zh.m.wikipedia.org/zh-tw/Apache_Spark)

Book - 精通Python Chp11 並行處理與網路

# RTSP applications

1. 即時串流協定rtsp是一個應用層協定，專為娛樂和通訊系統而設計
2. RTSP server一般使用即時傳輸協定RTP，和即時傳輸控制協定(RTCP)
3. RTSP server可以賺錢，像是Netflix，高流量，高品質影像串流伺服器
4. RTSP協定是誰搞出來的? RealNetwork, Netscape, 哥倫比雅大學，1998年發布，最新的更版是RTSP 2.0 - 2016年發布
5. 請求部分可以參考[notework/rtsp](./network.md)
6. 由於RTSP傳輸協定的response沒有被多數瀏覽器所接受，因此有一批人做了一個應用軟體，裡面使用RTSP來傳輸影片，聲音，讓瀏覽器透過他們的API可以即時渲染畫面，聽到聲音，這群人來自google，他們這套軟體稱作Web Real-Time Communication(WebRTC)

## WebRTC

[WebRTC original source code](https://github.com/webrtc/apprtc)

[WebRTC and ORTC python github](https://github.com/aiortc/aiortc)

Web Real-Time Communication，實作了RTSP，TCP，HTTP，UDP等協定，並提供API，讓所有瀏覽器軟體可以透過WebRTC來即時渲染高品質影像及音訊，google這幫人在2011年開源了WebRTC這套軟體，開源之後，瀏覽器公司(Google, Mozilla, Opera)大力支持，被全球資訊網路協會納入W3C推薦標準

幾乎所有瀏覽器都支援，以下是細節列表

| device/os     | browser            | note           |
|---------------|--------------------|----------------|
| PC            | Microsoft Edge     |                |
| PC            | Google Chrome 23   |                |
| PC            | Mozilla Firfox 22  |                |
| PC            | Opera 18           |                |
| PC            | Safari 11          | in development |
| Android       | Google Chrome 28   |  |
| Android       | Mozilla Firefox 24 |  |
| Android       | Opera Mobile 12    |  |
| chrome os     |                    |                |
| firefox os    |                    |                |
| ios 11        |                    |                |
| blackberry 10 |                    |                |

2010年，Google以6820萬美元收購VoIP軟體開發商Global IP Solutions的GIPS引擎，改名為WebRTC，然後魔改它

以遠端通訊服務為主的公司基本上都會Based on WebRTC去增進效能，新增功能，並作為自己公司的核心技術

例如Microsoft Team(Skype)，Facebook，Netflix，以及我隨便找到的這間[Flashphoner](https://flashphoner.com/screen-sharing-from-a-web-browser/)

# Design pattern in network application

網路的應用程式設計上，非常常使用一種設計模式，稱為pub-sub pattern(piblisher-subscriber pattern)，這種作法很像一種廣播或是電視傳輸，而一般的HTTP是[server - client]模式，有一對一關係，pub-sub pattern在多人觀看多種資源時是個特別有用的軟體設計模式，以下的軟體是透過pub-sub pattern進行設計，用於網路溝通及並行，當然，我們找使用Python的軟體

| name                                          | start from | note  |third-party guide|
|-----------------------------------------------|------------|-------|-----------------|
| [PyZMQ](https://zeromq.org/languages/python/) | 2010      | 超輕量分佈式訊息傳送軟體 <br> 和socket很像，ZMQ的明確目標是，成為標準網路協議棧的一部分，之後進入Linux核心，現在還未看到他的成功，但是極具前景 |[zeromq的三種簡單模式（python實現）](https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/116655/)|
|[Pure Python RabbitMQ](https://github.com/pika/pika)|2010|實現進階訊息佇列協定（AMQP）的python軟體|[以 RabbitMQ 實作工作佇列（Work Queues）（Python 版本）](https://blog.gtwang.org/programming/rabbitmq-work-queues-in-python/)|

通常這些軟體可以處理

1. 交換整個訊息
2. 重試連結
3. 傳送方與接收方的時間點沒有對上時，暫存資料

# MapReduce and Hadoop

隨著網路網路公司的業務成長，他們發現傳統演算法的解決方案並沒有辦法跟上他們想解決的問題難度，開發者發現可以把資料丟到多個機器上用很簡單的演算法進行運算，比起設計一個困難的演算法，然後讓他在單機算，有效率很多，且具有可規模性，因此就把腦筋動到通訊的發展

[MapReduce: Simplified Data Processing on Large Clusters](https://dl.acm.org/doi/pdf/10.1145/1327452.1327492?casa_token=JPg8egx5usMAAAAA:YmdO8ZWSZ203tqQDUEMOxzdGVsGxunLAN5k6mTO2RFZXhm_5iCiwOBjVZ7vb08AZmU4IutRt_VnEmto)就是google發表的一篇論文，演算法MapReduce，說明他們怎麼透過網路通訊，讓一大堆電腦處理大量資料

Google發表了MapReduce演算法之後，Yahoo把Google File System以及MapReduce兩篇論文用Java實作出來，把它開源，稱為Hadoop(以程式設計領導人兒子的填充大象玩具來命名XD)，Google File System? Google 2003年發表的檔案系統，是公司內部的實作，具有高容錯性

[The Google File System](https://dl.acm.org/doi/pdf/10.1145/945445.945450?casa_token=O3FWvnWulfYAAAAA:JCasMRhWHFtmm9AHHELnsTAsv-l8lSRbYjVMbblc2yRqxTofez9fLwIKKTLfTzFTe9A_gpQzZ7xylYk)

以串流聞名的公司Spotify也將公司內部開發Hadoop串流的source code開源，稱之為Luigi

# Spark

Spark是Hadoop的競爭對手，它的設計比Hadoop快10-100倍，並且兼容Hadoop的所有資料來源以及格式，有Python，Java，Scala，R API。
