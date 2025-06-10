---
layout: wiki  # 使用wiki布局模板
wiki: vue # 这是项目名
title: Vue3中使用Googlechart
category:
  - Vue
---

#### Googlechart

##### 1.1 安装vue-google-charts

$npm install vue-google-charts--save

##### 1.3 main中全局导入
```
import VueGoogleCharts from 'vue-google-charts'

const app \= createApp(App)

app.use(VueGoogleCharts)

app.mount('#app')
```

##### 1.4 组件中使用
```

<template\>

 <div style\="width:600px;"\>

  <GChart

   type\="ColumnChart"

   :data\="chartData"

   :options\="chartOptions"

  ></GChart\>

 </div\>

</template\>

<script >

import { GChart } from 'vue-google-charts'

export default{

 components:{

  GChart

 },

 data(){

  return{

   chartData: \[//图表数据

    \['Year', 'Sales', 'Expenses', 'Profit'\],

    \['2014', 1000, 400, 200\],

    \['2015', 1170, 460, 250\],

    \['2016', 660, 1120, 300\],

    \['2017', 1030, 540, 350\]

   \],

   chartOptions: {//图表属性

    chart: {

     title: 'Company Performance',

     subtitle: 'Sales, Expenses, and Profit: 2014-2017',

    }

   }

  }

 }

}

</script\>
```
  

type\="ColumnChart"指定图表为柱状图