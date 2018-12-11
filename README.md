# travel

## -用vue写去哪儿网 ---移动端
## *项目介绍*：
数据：完全来自于json数据-----用axios接收数据渲染 

```
import axios from 'axios'

 methods:{
      getDtailInfo(){
          axios.get('/api/detail.json?' ,{
              params:{
                    id: this.$route.params.id
              }
          }).then(this.handleGetDateSucc)
      },
      handleGetDateSucc(res){
             res=res.data
             if(res.ret && res.data){
                const data=res.data
                this.sightName=data.sightName
                this.bannerImg=data.bannerImg
                this.gallaryImgs=data.gallaryImgs
                this.categoryList=data.categoryList
             }
      }
  },
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20181211114048711.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80Mzk0OTc4OA==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181211114615863.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80Mzk0OTc4OA==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/2018121111360384.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80Mzk0OTc4OA==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181211114750237.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80Mzk0OTc4OA==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181211114859380.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80Mzk0OTc4OA==,size_16,color_FFFFFF,t_70)

```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
