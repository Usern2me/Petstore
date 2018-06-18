# Petstore
宠物商店 施工中。。。<br />
前端：`semanticUI | JQuery | Ajax | jsp ` <br /> 
后端：`Spring | SpringMVC | Mybatis | MybatisGenerator | Mysql` <br /> 
整个项目用 maven管理，但还是有点大，等写完了我优化一下前端的资源<br /> 

-------------------------------------------------------------------------
###### 总结
1. 用mybatis自动生成mapper的时候最好分离开，自己去继承它的接口再扩展，不要直接改动它生成的源码最好也不要改动XML文件，不然想修改数据库的时候会发现很痛苦。<br /> 
2. 数据库一定要提前设计好！分析好系统的功能再完整的编写表，不然后面改起来要改不少地方。<br /> 
3. 本来不想用jsp想尝试纯html和后端通信，但是文件的位置我怎么试也找不到，只能用pageContent.request来取资源和页面的地址了，对于这个问题还是保留疑问，希望以后能找到好的不用把java和html混在一起的写法，或者已经有了只是我见识的太少了还不知道。<br /> 
4. 项目开始前设置好tomcat和webContent的位置，tomcat设置一下artifact就行了，这个是帮你告诉汤姆猫你的项目的位置，好让它进行部署，webcontent在项目设置那里进行设置，设置了之后文件夹上有有一个蓝色的点，代表它已经知道了这个就是你的web资源，顺便一提，在文件夹上右键可以设置基本的文件夹的类型，比如source，这个就是放java代码的地方，resource就是放资源的地方，xml什么的配置文件都要放在这里面，不然它找不到，还有一些其他的资源也可以放进去，用的时候可以方便一点，然后还有test文件夹，就是放测试代码的地方。<br /> 
5. 一开始写配置文件的时候不要在网上找一大堆一起复制，最好能搞清楚每个配置的意义，注意他们的顺序有时候会影响，最重要的一点就是注意你用的jar包的版本，有一些不兼容的时候出现bug很难排除出来。<br /> 

-------------------------------------------------------------------------
###### Tips:
1. 前后台用json传数据的步骤，在前台里，可以使用JSON.stringify()函数，把对象转成json的string，也可以使用JSON.parse()函数，把json的string转成一个js里的对象；后台里，有JSONObject和JSONArray两个对象，转string就用它们的toString()函数，转对象，就用toBean()和toArray()函数。需要注意的是JSONObject必须是string的键。
2. window.location.href不能正常跳转，window.open也没有用，在这后面加上window.event.returnValue=false,放在提交表单中的onclick事件中则不会提交表单，如果放到超链接中则不执行超链接，也就是它禁止了或取消了请求。个人理解是我的非异步（async==false）请求成功后跳转了页面，就不在当前页面了，就不会在执行这个跳转了，加上这句之后这次ajax的返回值就不计了，于是请求就能成功了。
3. 多个子card想绑定一个div的onclick事件，在父div上绑定getValue(event),然后子元素上赋给自定义属性data-value,在getValue(e)里用e.target.getAttribute("data-value")就可以获得当前被click的子元素的值，而且还可以自定义任何值。

