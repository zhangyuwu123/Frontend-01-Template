# 每周总结可以写在这里
# 知识地图整理
![](https://github.com/zhangyuwu123/Frontend-01-Template/blob/master/week01/jishu.png)
# url匹配
```
var str ='https://developer.mozilla.org/en-US/docs/Web/CSS/calc?a=1&b=2'
var vars ={}
str.replace(/[?&]+([^=&]+)=([^&]*)/gi,function(str,p1,p2,offset,m){
    console.log(str+':'+p1+' - '+p2)
    vars[p1] = p2
})
```
# 心得
以前也死记硬背过dom、bom等，但是时间长不用就忘了，试了试老师的追溯法，先搞清楚标准，然后去看定义，再用法，时间长了即使用法忘了，但是标准，api所处的知识结构是清晰的，用的时候找一下就ok了，
# 反思
   但是也返现了些问题，使用追溯法的时候，某一个知识点比如node 的range 查了一下mdn 分abstractRange、staticRange、range三者的关系，但是看这些标准还是挺花时间的，不知道大家有什么好的建议没
