### 1. jQuery更改DOM属性,比如元素的checked, selected, 或 disabled状态，请使用.prop()方法。attr()不能实现

- //选中
$('#id').prop('select','select');或
$('#id').prop('select','true');
- //取消
$('#id').prop('select','');或
$('#id').prop('select','false');

### 2. 项目里用的bootstrap写的手风琴菜单，当页面正在加载的时候狂点手风琴，结果这个折叠的菜单点不开了

- bootstrap.js 还没有加载完毕

### 3. 使用的bootstrap-Table插件做数据展示，我是用iframe把这个页面引入到主页面的。
我在主页面想获取这个iframe里面的元素对象，结果发现怎么写都没有用
$("#iframe1").contents().find("#age").val();
或者
$(window.frames["iframe1"].document).find("#age").val();
都不行，获取不到里面的数值

- 首先,必须部署到服务器测试,避免跨域问题,其次,你要确定iframe是否已经加载完毕.


### 4.
$("#div").load(url) 这种方式，如果我请求过来的内容有html，js文件和javascript的执行语句，我发现会有影响，因为我用这种方式引入的bootstrap-Table的汉化脚本文件没有起到作用，而直接使用路径访问是可以的

- 建议在 load 之前手动将汉化js追加到head区域,因为load是不影响DOM渲染的

### 5. 
bootstrap-Table的这个iframe页面，我发现它的高度当首次加载后，第一次点击分页时会自动变小，而首次加载后会撑的挺大，我在google下调好了，在火狐下显示的不理想。

- 建议搜索iframe自适应高度,每次load之后动态调整高度