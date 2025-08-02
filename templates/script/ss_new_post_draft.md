<%*
const today = tp.date.now("YYYY-MM-DD_HH-MM-SS")
const inputTitle = await tp.system.prompt("输入 title：",today) 
const inputTags = await tp.system.prompt("输入 tags（以英文逗号分隔）：", "")
const inputLink = await tp.system.prompt("输入短链接（可选）：", "")
const inputCategories = await tp.system.suggester(["题目记录", "工具", "前端", "笔记", "项目集锦"], ["题目记录", "工具", "前端", "笔记", "项目集锦"])
const createTime = tp.file.creation_date("YYYY-MM-DD hh:mm:ss")
const tags = inputTags.split(",").reduce((prev, curv) => prev + `- ${curv}\n`,"")
const obTags = inputTags.split(",").reduce((prev, curv) => prev + `#${curv} `,"")
-%>
---
title: <% inputTitle %>
link: <% inputLink %>
catalog: true
date: <% createTime %>
tags:
<% tags %>
categories:
- <% inputCategories %>   
---
%% <% obTags %> %%

## 以二级标题开始 

Hello, World

<%*
await tp.file.move("/_drafts/" + inputTitle)
tp.file.cursor()
-%>