---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: 文章html内容导出为Docv和Md文档
date: 2024-7-08 11:00:00
category:
  - Vue
---

#### 导出为Docx

##### 1\. 安装插件包

**html-docx-js**： 将Html格式的字符串转化成纯文本

**file-saver**： 保存文件

  

##### 2.使用
```
import htmlDocx from 'html-docx-js/dist/html-docx'
import FileSaver from 'file-saver'

  

/\*将concept保存为docx文件\*/
  saveConceptToDocx(concept){
   var content = concept.contents
    
   var converted = htmlDocx.asBlob(content)
    
   FileSaver.saveAs(converted, concept.header+'.docx')
  },
```
  

#### 导出为Markdown

##### 1\. 安装插件包

**turndown**： 将Html格式的字符串转化成markdown内容

  

##### 2.使用
```
import TurndownService from 'turndown'

/\*将concept保存为md文件\*/
    saveConceptToMd(concept) {
      
      var turndownService = new TurndownService()
      var markdownContent = turndownService.turndown(concept.contents)


      var converted = new Blob(\[markdownContent\],{type:'markdown'})
      
      FileSaver.saveAs(converted, concept.header + '.md')
    },
```