# Ref

[Home page](https://cs50.harvard.edu/summer/2020/weeks/10/)

[pdf](https://cdn.cs50.net/2019/fall/lectures/10/lecture10.pdf)

# Review

* homework review
* compare with yourself, not other guy
* CS -> problem solving
* searching -> binary searching
* precision, correctness are important and hard
* program is like talk-draw game

# Information

* all the thing we discussed in previous weeks is `Information` , how to represent it, how to process it? how to transform it, 

then solve real world problem.

# PIN(personal identification number)

* just like password
* python `zero padding for numbers`

``` Python
for i in range(0000, 1000):
print(f'checking {i:04}')
```

* crash others password - iterate a big dictionary!

# Cookies

* a place you allow website to leave a information in your computer.
* Developer tools - set-cookie
* let's the website to know that
  + have you been here before?
  + what action have done in the past in my website/other websites. (user behavior!!!)

## 無痕模式!?

* use 無痕模式 + developer tools
* `Network` -> `www.google.com` -> `All` -> `Response Headers` -> google still put cookies on my computer but as long as this window open
* `Response header` : 對方server傳給你的內容
* `Request header` : 你傳給對方server的內容
* 網頁內容，一些js code，圖片會在Response內

## Snapcheat

* delete photos after 10 secs
* DELETE or UPDATE to another table!?
* hard delete / soft delete(backup mode )
* not recoverable / make database know that, oh you want to delete it. we erease the data from user screen, but keep it in computer somewhere.
* Don't trust the application ad XD

## Tracks

web programming - html, css, js, python , sql- cs50 finance
mobile app development, Swift (IOS), Java(Android) - pikemon decks, note tracking app
game development - Lua, super mario brothers(two dimensional side scrolling game)

# Stats

session 1
start 1800
end 1830
course 23:07
factor 1

session 2
start 1730
end 1830
course 75
factor 1.2

session 3
start 1930
end 1945
course 90
factor 0.5

total  60 mins (1hr)

course 120 mins (2hr)
