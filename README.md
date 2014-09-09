# 在github建立靜態網站

> 文章發表於 : [在github建立靜態網站](http://blog.kejyun.com/2013/06/Build-Web-Page-On-Github.html)

---

如果有用過Twitter Bootstrap的人應該會發現它們的網址是 http://twitter.github.io/bootstrap/ ，他們將網站放在github下，雖然只支援靜態網站，但對於簡單的小網站我想也夠了，而且還有版本控制，一舉兩得，所以現在開始來玩玩github page吧~

---

## 建立GITHUB PAGE方法

1. 手動建立
2. 使用產生器建立


### 手動建立

clone要建立page的repository

```shell
git clone https://github.com/kejyun/github-page.git
```

建立一個沒有母節點，名字叫gh-pages的分支（branch）

```shell
git checkout --orphan gh-pages
```

在gh-pages分支中，刪除從原本分支複製到gh-pages分支的所有檔案
因為gh-pages沒有了母節點，所以檔案異動不會影響到其他原本的分支

```shell
git rm -rf .
```

建立在github pages的網頁

```shell
echo "<h1>KeJyun's Manually GitHub Page</h1>" > manually.html
git add manually.html
git commit -a -m "KeJyun's First Manually Github Page commit"
git push origin gh-pages
```


檢視github page網頁

github pages的網址結構是`http://帳號.github.io/分支名稱/檔案名稱`

所以我們可以透過下列網址去檢視剛剛推上去的檔案

> http://kejyun.github.io/github-page/manually.html

---

### 使用產生器建立

前往repository頁面點選setting

![前往repository頁面點選setting](http://4.bp.blogspot.com/-QQtphuHfNhA/Ua6WKWFiXJI/AAAAAAAAAQM/yYHJ5MwfpaU/s1600/01.png)

找到GitHub Pages的功能，點選Automatic Page Generator

![找到GitHub Pages的功能，點選Automatic Page Generator](http://4.bp.blogspot.com/-L7Wg4uSdCKM/Ua6WQ8rAF7I/AAAAAAAAAQU/Z9LiAw5BOJ4/s1600/02.png)

填入你的專案名稱（Project Name）、專案下標（Tagline）以及內文（Body）

![填入你的專案名稱（Project Name）、專案下標（Tagline）以及內文（Body）](http://1.bp.blogspot.com/-w7HbH-ocjb0/Ua6Wdpxt_UI/AAAAAAAAAQc/wcF-VZfJXtE/s1600/03.png)

填入Google Analytics Tracking ID（選填）並產生Github Page樣板
若需要使用GA（Google Analytics）追蹤分析頁面活動則填入你的GA追蹤編號，不需要則不必填寫

填寫完畢後點選Continue to Layouts觀看產生的預覽畫面

![填入Google Analytics Tracking ID（選填）並產生Github Page樣板](http://1.bp.blogspot.com/-4QOCcRFyxHA/Ua6WyfLIAlI/AAAAAAAAAQk/u3ctmomX9-k/s1600/04.png)

檢視預覽畫面
這裡可以挑選不同的樣板，若挑選好預設樣板，可以點選PUBLIS產生Github Page

![檢視預覽畫面](http://3.bp.blogspot.com/-nTRz7KBxYOg/Ua6Xm3BMzvI/AAAAAAAAAQw/haHSsLiEFdI/s1600/05.png)

檢視自動產生Github Pages成果
可以在github上看到自動產生的github pages

> https://github.com/kejyun/github-page/tree/gh-pages

github pages自動產生器會將剛剛的預覽畫面產生為index.html

我們也可以看到手動產生的manually.html

github pages的網址結構是`http://帳號.github.io/分支名稱/`

而Github Page預設會讀取index.html的檔案

所以我們可以透過下列網址去檢視自動產生的GitHub Pages

> http://kejyun.github.io/github-page/


![檢視自動產生的GitHub Pages](http://3.bp.blogspot.com/-ESlxyOOm7eI/Ua6YX9tNC9I/AAAAAAAAAQ4/uDEgHxxmMTE/s1600/06.png)

---

## 參考網站

* [Creating Pages with the automatic generator · GitHub Help](https://help.github.com/articles/creating-pages-with-the-automatic-generator)
* [Creating Project Pages manually · GitHub Help](https://help.github.com/articles/creating-project-pages-manually)
* [如何建立一個沒有 Parent 的獨立 Git branch](http://ihower.tw/blog/archives/5691)
* [Creating Pages with the automatic generator · GitHub Help](https://help.github.com/articles/creating-pages-with-the-automatic-generator)
