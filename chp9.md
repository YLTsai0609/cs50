# Ref

[Home page](https://cs50.harvard.edu/summer/2020/weeks/9/)

[pdf](https://cdn.cs50.net/2019/fall/lectures/9/lecture9.pdf)

# Flask

HTML + CSS : static content
In nowdays, Dynamic content

Flask實作， Flask, dynamic route, render_template

# render_template

1. html可以用 `{{}}` 就像f-string依樣替代html裡面的值
2. condition - 不會被html source code看到

```{% if number == 1%}

    You coin flip is HEADS.

   {%else%}

    You coin flip is TAILS.

   { %end if%}
```

3. form submit action to another html file via flask(also sanity check)

4. `layout.html`

templates中的各個html看起來是可以有一個base.html來擴展
因為有很多重複的，因此可以建立一個layout.html

5. good practice : 先建立很多個route，都return一個字串，表明這個頁面你要做什麼，就像先寫function，但是pass一樣

6. `{{}}` 在html中經由flask可以使用 `if else` ,   `variable` ,   `for loop` ，讓我們可以動態的建立網頁內容，對應到C#可以想成 `ASP.NET` ，這個功能稱作 ` Jinja2 Template`

[Jinja2 Template Documentation](https://jinja.palletsprojects.com/en/2.11.x/templates/)
小八卦 flask, jinja2是同一個開發者做的，所以這也是使用jinja2的語法以及 `render_template` 來動態渲染html算是flask的一個特色

# Databases

## cookies

* cookies : websites can ask your web browser to store on your computer
* websites use cookies to recognize you when you visit again.

## Session

* every time you visit thr website, it is a unique session.
* global variable in flask is not `session separated` , it is in `application` level - like counting people who visited the website.
* how to create a `session seperated variable?`
* how can we test different session? - use a private google chrome page

## sqlite3

若有Flask, database的需求，再回來上課即可。

# Other resource

[模板引擎Jinja2语法介绍](https://zhuanlan.zhihu.com/p/108288226)

# Stats

session 1
start 1420
end 1520
course 26.27
factor 0.5

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
