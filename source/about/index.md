---
menu_id: about
title: 「About」
date: 2024-08-21 10:50:19
banner: /assets/cover/cover_about.jpg
banner_info: 
    subtitle: 梦想仗剑走天涯
comments: true
---

{% paper style:underline title:欢迎 author:乘风 footer:VicoGao %}
<!-- line left -->
旅行者，
<!-- paragraph -->
你好呀，等候你多时了！我在这里记录生活的点滴与感悟。嗯~，作为一个i人，其实不太想将自己的生活内容开放展示出来。算了，也不知道有没有人能看到。如果你对其中的文章内容有想法，欢迎评论！
{% endpaper %}

{% emoji blobcat ablobcatwave %}{% emoji blobcat ablobcatattentionreverse %}{% emoji blobcat ablobcatrainbow %}{% emoji blobcat blobcatalt %}  

#### 文章总览
{% echarts 90% 400 %}
{
  title: {
    text: '优缺点雷达图'
  },
  legend: {
    data: ['缺点', '优点']
  },
  radar: {
    // shape: 'circle',
    indicator: [
      { name: 'Sales', max: 6500 },
      { name: 'Administration', max: 16000 },
      { name: 'Information Technology', max: 30000 },
      { name: 'Customer Support', max: 38000 },
      { name: 'Development', max: 52000 },
      { name: 'Marketing', max: 25000 }
    ]
  },
  series: [
    {
      name: 'Budget vs spending',
      type: 'radar',
      data: [
        {
          value: [4200, 3000, 20000, 35000, 50000, 18000],
          name: '优点'
        },
        {
          value: [5000, 14000, 28000, 26000, 42000, 21000],
          name: '缺点'
        }
      ]
    }
  ]
}
{% endecharts %}