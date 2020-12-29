# Ref

[Home page](https://cs50.harvard.edu/summer/2020/weeks/0/)

[pdf](https://cdn.cs50.net/2019/fall/lectures/0/lecture0.pdf)

<img src='./images/chp_1.png'></img>

* 2/3 of people never take cs lesson before.
* If you feel unsafe, It's okay.

# Introduction / Computer Science / Representation

* A process of solving problem

<img src='./images/chp_2.png'></img>

* How you present input and output?
* More generally, how you present information?

## binary

* **BINARY** - what computer person infomation

## Numbers

* count people in the room, perple use 單語言, 有就count 1, 沒有就沒有, 用手來比

* people could count, computer only get 0/1 - but they could present image, video, sound, and character!

* `123` means 一百二十三 in our symbol - and we read in a way like below

<img src='./images/chp_3.png'></img>

* It is just a power system of 10

* Then in computer system, they think like that.

<img src='./images/chp_4.png'></img>

* **BINARY** means somebody understanding information using 2 power system

<img src='./images/chp_5.png'></img>

  Wwe need more digit : P

* The digit called **bit**
* 1/0 on/off True/False could represnet the idea

<img src='./images/chp_6.png'></img>

* Bytes just 8 bits

<img src='./images/chp_7.png'></img>

* 晶體管，裡面就是一大堆這種開關XD
* 某個計算機為了表達50，就會在剛剛的這三個位置儲存一點電，那麼他就表達了50
* 真的很好笑XD，互動的部分XD

# What about text and sending email, compose document?

## character

* Ok!, how computer represnet character?

* Representing as nunber XD
* A - 1, B - 2, C - 3 ?
* They is a dictionary!
* This dictionary is ASCII  

<img src='./images/chp_8.png'></img>
<img src='./images/chp_9.png'></img>
<img src='./images/chp_10.png'></img>

* **ASCII** - American System Code II (美國訊息交換標準代碼)
* well..., again, just a well-defined map(dictionary)

<img src='./images/chp_11.png'></img>

<img src='./images/chp_12.png'></img>

* if you want to say `HI!`

<img src='./images/chp_13.png'></img>

# All country around the world?

## Unicode

## and now day emoji?

<img src='./images/chp_14.png'></img>

<img src='./images/chp_15.png'></img>

* They call it **Unicode**
* Again, well defined map(dictionary)

* The difference ascii use 8 bits, Unicode use 8/16/24/32 bits

<img src='./images/chp_16.png'></img>

* The most popular emoji sent on IOS to 2019

<img src='./images/chp_17.png'></img>

* Tear smile emoji -> 128514, hahahahaha
* in binary,         `11111011000000010`

# Color? (yellow dots on emoji)

## RGB

* Again, years ago, people in a room, you know what, we want to represent color but use `0, 1` only

* If you sent a color point, you are actually sending 3 numbers

<img src='./images/chp_19.png'></img>

<img src='./images/chp_20.png'></img>

<img src='./images/chp_21.png'></img>

# images / gif / video

<img src='./images/chp_22.png'></img>
<img src='./images/chp_23.png'></img>

* Basically N point, with a lot of (65, 22, 11) nunmber of tuples!
* gif!? - there are N pictures. Each of one with a lot of (65, 22, 11) number of tuples!

# what about music?

## Sound

<img src='./images/chp_24.png'></img>

* 相同的方法，這次三個值(26, 33, 11)拿來代表音符，持續時間，音量

# The black box

## algorithms

<img src='./images/chp_25.png'></img>

* a step by step maumal for solving problem

## find a name in a phone book, well sorted

<img src='./images/chp_26.png'></img>

* binary search

<img src='./images/chp_27.png'></img>

## Idea, psudo code, function, condition, boolean statement, and loop

* When problem size getting bigger, solving time basically the same.
* Intutively, we get twice size bigger problem, we just one more step to solving probelm

## (psudo code) Tansfer this idea into code

* Basically no standard format
* Use english, or your language, some number, to present your idea

<img src='./images/chp_28.png'></img>

* It will translate into a language called `scratch`,         `python`,         `C`
* the yello highlight word call `function`, it is a verb to do someting!

<img src='./images/chp_29.png'></img>

* Now another highlight word call `condition`

<img src='./images/chp_30.png'></img>

* The word highlight following condition is called `boolean statement`, just named by a mathmatician Bool

<img src='./images/chp_31.png'></img>

* the word highlight is `loop`, which make things going again and again.

<img src='./images/chp_32.png'></img>

## Summary

<img src='./images/chp_32.png'></img>

## And More!

<img src='./images/chp_33.png'></img>

* We will use scratch which is develop by MIT lab

## scratch

<img src='./images/chp_33.png'></img>

You could try it, it is very easy to use : P

<img src='./images/chp_34.png'></img>

<img src='./images/chp_35.png'></img>

* Computer Science like start with zero because it means all the digits are off

* Computer can do parallelly, can listening a event
* Abstraction - make block as function

# learning log

session 1

start : 0530
end : 0630
read : 28 mins

session 2

start : 0530
end : 0640
read : 30 mins

Total : 2hr

Actual : 1hr
