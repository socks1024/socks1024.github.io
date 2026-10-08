<%* let noteTitle = await tp.system.prompt("请输入文章标题");
await tp.file.rename(tp.date.now("YYYY-MM-DD") + "-" + noteTitle); -%>
---
title: <% noteTitle %>
date: <% tp.date.now("YYYY-MM-DD HH:mm:ss +0800") %>
categories: []
tags: []
---