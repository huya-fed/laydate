日期控件
=========

> 简介：你是时候换一款日期控件了，而layDate非常愿意和您成为工作伙伴。她致力于成为全球最用心的web日期支撑，为国内外所有从事web应用开发的同仁提供力所能及的动力。她基于原生JavaScript精心雕琢，兼容了包括IE6在内的所有主流浏览器。她具备优雅的内部代码，良好的性能体验，和完善的皮肤体系，并且完全开源，你可以任意获取开发版源代码，一扫某些传统日期控件的封闭与狭隘。layDate本着资源共享的开发者精神和对网页日历交互无穷的追求，延续了layui一贯的简单与易用

参考 ： 

[http://laydate.layui.com/](http://laydate.layui.com/)


##先看个实例

	【外部js调用】
	<input id="hello" class="laydate-icon">
	<script>
	laydate({
	  elem: '#hello', //目标元素。由于laydate.js封装了一个轻量级的选择器引擎，因此elem还允许你传入class、tag但必须按照这种方式 '#id .class'
	  event: 'focus' //响应事件。如果没有传入event，则按照默认的click
	});
	</script>
	
	【图标触发日期】
	<input id="hello1">
	<span class="laydate-icon" onclick="laydate({elem: '#hello1'});"></span>


	【自定义日期格式】
	<div id="test1" class="laydate-icon"></div>
	<script>
	laydate({
	  elem: '#test1',
	  format: 'YYYY/MM', // 分隔符可以任意定义，该例子表示只显示年月
	  festival: true, //显示节日
	  choose: function(datas){ //选择日期完毕的回调
	    alert('得到：'+datas);
	  }
	});
	</script>
	
	【日期范围限定在昨天到明天】
	<div id="hello3" class="laydate-icon"></div>
	<script>
	laydate({
	  elem: '#hello3',
	  min: laydate.now(-1), //-1代表昨天，-2代表前天，以此类推
	  max: laydate.now(+1) //+1代表明天，+2代表后天，以此类推
	});
	</script>



	【日期范围限制】
	var start = {
	  elem: '#start',
	  format: 'YYYY/MM/DD hh:mm:ss',
	  min: laydate.now(), //设定最小日期为当前日期
	  max: '2099-06-16 23:59:59', //最大日期
	  istime: true,
	  istoday: false,
	  choose: function(datas){
	     end.min = datas; //开始日选好后，重置结束日的最小日期
	     end.start = datas //将结束日的初始值设定为开始日
	  }
	};
	var end = {
	  elem: '#end',
	  format: 'YYYY/MM/DD hh:mm:ss',
	  min: laydate.now(),
	  max: '2099-06-16 23:59:59',
	  istime: true,
	  istoday: false,
	  choose: function(datas){
	    start.max = datas; //结束日选好后，重置开始日的最大日期
	  }
	};
	laydate(start);
	laydate(end);
	</script>
    