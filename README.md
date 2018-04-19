# barrage
弹幕（适用于评论，留言，打赏等）

## 默认数据格式为

        var data = [
          {href : 'http://fy.035k.com',text : '我的博客http://fy.035k.com'},
          {href : 'http://www.baidu.com',text : '百度'},
          {href : 'http://www.imooc.com',text : '慕课网'},
          {href : 'http://www.jq22.com',text : 'jquery插件网'},
          {href : 'http://www.035k.com',text : '苏打绿可根据历史'},
          {href : '',text : '死垃圾管理数据管理'},
          {href : '',text : '另外今年光缆和并购水晶宫老师'}
        ]
data为数据，数据格式可调换，更改数据格式时，记得去改源码中的36行

## 数据初始化
        var Obj = $('body').barrage({
                data : data, //数据列表
		row : 5,   //显示行数
		time : 2500, //间隔时间
		gap : 20,    //每一个的间隙
		position : 'fixed', //绝对定位
		direction : 'bottom right', //方向
		ismoseoverclose : true, //悬浮是否停止
		height : 30, //设置单个div的高度
        })

## 开始弹幕方法

        Obj.start(); 

## 添加弹幕方法

       //添加评论
      $("#submit_barraget").click(function(){

        var val = $("#barrage_content").val();
        //此格式与data.js的数据格式必须一致
        var addVal = {
          href : '',
          text : val
        }
        //添加进数组
        Obj.data.unshift(addVal);
        alert('评论成功');

      })

## 关闭弹幕方法
      Obj.close();
