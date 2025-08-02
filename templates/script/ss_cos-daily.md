<%*
const today = tp.date.now("YYYY-MM-DD")
const inputDate = await tp.system.prompt("输入示例："+today, today)
const titleName = window.moment(inputDate, "YYYY-MM-DD", true).format("YYYY-MM-DD_ddd")
// date
const todayDate = window.moment(today, "YYYY-MM-DD", true)
const year = todayDate.format("YYYY")
const mouth = todayDate.format("MM")
const day = todayDate.format("DD")
const before_date = window.moment(inputDate, "YYYY-MM-DD", true).add(-1,"days").format("YYYY-MM-DD_ddd")
const after_date = window.moment(inputDate, "YYYY-MM-DD", true).add(1,"days").format("YYYY-MM-DD_ddd")
const createTime = tp.file.creation_date()
const modificationDate = tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss")
-%>
---
date: <% createTime %>
lastModify: <% modificationDate %>
---

<< [[<% before_date %>]] | [[<% after_date %>]] >>

<% tp.web.daily_quote() %>

<% tp.web.random_picture("200x200", "landscape,water") %>

#### 今日小结
%% #今日小结 %%

说点什么吧~

#### 博文阅读
%% #博文阅读 %%

- 今天什么文章都没有读喵！

#### 资源发现
%% #资源发现%%

- 今天没有发现宝藏呢！

#### 日常娱乐
%% #日常娱乐 %%

- 今天摸鱼了一天喵！

<%*
await tp.file.move(`/_daily/${year}/${mouth}/` + titleName)
tp.file.cursor()
-%>