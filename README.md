###项目背景 
鉴于目前有许多非常成熟的教学管理系统，~~由于我们能力有限~~，我们依旧想挑战一下自己，毅然选择教学管理系统作为我们的开发项目。

###项目介绍
名称：teaching-website
特点：没有特点就是最大的特点
功能：实现留言、文件上传下载、课程查询、选课管理、成绩查询等功能，方便学生教师的日常使用

###环境依赖
编译器：myeclipse2014
服务器：apache-tomcat-7.0.42
数据库：MySQL
持久层框架：MyBatis
构建工具：apache-maven-3.6.3
前端技术：Vue、Bootstrap、JQuery

###项目运行截图
![Image](https://gitee.com/HandSomeTaoA/teaching-website/raw/master/image4.png)
<center>图1.登录界面</center>
![Image](https://gitee.com/HandSomeTaoA/teaching-website/raw/master/image3.png)
<center>图2.学生界面</center>
![Image](https://gitee.com/HandSomeTaoA/teaching-website/raw/master/image2.png)
<center>图3.教师界面</center>
![Image](https://gitee.com/HandSomeTaoA/teaching-website/raw/master/image1.png)
<center>图4.管理员界面</center>


###目录结构描述
│  pom.xml		#Maven项目中的文件
├─src
│  ├─main
│  │  ├─java
│  │  │  ├─com
│  │  │  │  └─team
│  │  │  │      └─website
│  │  │  │          ├─dao		#数据访问层
│  │  │  │          │  ├─api
│  │  │  │          │  │      AdminDao.java		       #管理员的数据访问接口
│  │  │  │          │  │      StudentDao.java		#学生的数据访问接口
│  │  │  │          │  │      TeacherDao.java		#教师的数据访问接口
│  │  │  │          │  │      
│  │  │  │          │  └─impl
│  │  │  │          │          AdminDaoImpl.java		#管理员数据层访问接口实现类
│  │  │  │          │          StudentDaoImpl.java		#学生数据层访问接口实现类
│  │  │  │          │          TeacherDaoImpl.java		#教师数据层访问接口实现类
│  │  │  │          │          
│  │  │  │          ├─entity		#实体类
│  │  │  │          │      Admin.java			#管理员实体类
│  │  │  │          │      AdminExample.java
│  │  │  │          │      Clazz.java			#班级实体类
│  │  │  │          │      ClazzExample.java
│  │  │  │          │      Course.java			#课程实体类
│  │  │  │          │      CourseInfo.java		#课程信息实体类
│  │  │  │          │      Message.java			#消息实体类
│  │  │  │          │      MessageExample.java
│  │  │  │          │      SCinfo.java			#选课信息实体类
│  │  │  │          │      Score.java			#成绩实体类
│  │  │  │          │      SelectCourseInfo.java
│  │  │  │          │      Student.java			#学生实体类
│  │  │  │          │      StudentExample.java
│  │  │  │          │      StuSelectCourse.java		#学生选课实体类
│  │  │  │          │      Teacher.java			#教师实体类
│  │  │  │          │      TeacherExample.java
│  │  │  │          │      
│  │  │  │          ├─mapper     #Mapper接口
│  │  │  │          │      AdminMapper.java
│  │  │  │          │      ClazzMapper.java
│  │  │  │          │      MessageMapper.java
│  │  │  │          │      StudentMapper.java
│  │  │  │          │      TeacherMapper.java
│  │  │  │          │      
│  │  │  │          ├─service
│  │  │  │          │  ├─api
│  │  │  │          │  │      AdminService.java		#管理员处理业务逻辑接口
│  │  │  │          │  │      MessageService.java		#消息处理业务逻辑接口
│  │  │  │          │  │      StudentService.java		#学生处理业务逻辑接口
│  │  │  │          │  │      TeacherService.java		#教师处理业务逻辑接口
│  │  │  │          │  │      
│  │  │  │          │  └─impl
│  │  │  │          │          AdminServiceImpl.java		#管理员处理业务逻辑实现类
│  │  │  │          │          MessageServiceImpl.java		#消息处理业务逻辑实现类
│  │  │  │          │          StudentServiceImpl.java		#学生处理业务逻辑实现类
│  │  │  │          │          TeacherServiceImpl.java		#教师处理业务逻辑实现类
│  │  │  │          │          
│  │  │  │          ├─servlet		#运行在Web服务器上的程序
│  │  │  │          │      AdminServlet.java
│  │  │  │          │      StudentServlet.java
│  │  │  │          │      TeacherServlet.java
│  │  │  │          │      webServlet.java
│  │  │  │          │      
│  │  │  │          └─util
│  │  │  │                  DBUtil.java			#学生数据库管理
│  │  │  │                  TeachingUtil.java		#教学数据库管理
│  │  │  │                  
│  │  │  ├─teacher
│  │  │  │      Controller.java			#教师控制层
│  │  │  │      EncodingFilter.java		#编码配置器
│  │  │  │      Process.java
│  │  │  │      score.java		#成绩类
│  │  │  │      
│  │  │  └─uploadFiles
│  │  │          addNewDir.java		#新增文件夹实体类
│  │  │          DownLoad.java		#下载文件实体类类
│  │  │          IdGenertor.java
│  │  │          LShowAllFiles.java	      #显示目录（文件夹）
│  │  │          ShowAllFiles.java		#学生端显示全部文件实体类
│  │  │          TDownLoad.java			#老师下载文件实体类
│  │  │          TeacherGetDir.java		#老师获取文件夹实体类
│  │  │          TShowAllFiles.java		#老师端显示全部文件实体类
│  │  │          TUpload.java		#老师上传实体类
│  │  │          Upload.java		#学生上传实体类
│  │  │          
│  │  ├─resources
│  │  │  │  conf.xml		#MyBatis生成的全局配置文件
│  │  │  │  db.properties		#连接池配置文件
│  │  │  │  
│  │  │  └─mybatis
│  │  │      └─mapper		#对象持久化映射层
│  │  │              AdminMapper.xml
│  │  │              ClazzMapper.xml
│  │  │              MessageMapper.xml
│  │  │              StudentMapper.xml
│  │  │              TeacherMapper.xml
│  │  │              
│  │  └─webapp
│  │      │  add-user.jsp			#新增用户页面
│  │      │  addCourseInfo.jsp		#添加/修改课程信息页面
│  │      │  admin-edit.jsp			#管理员编辑用户信息页面
│  │      │  admin-main.jsp		#管理员登录成功后进入的主页面
│  │      │  Classroom.jsp			#教师查询页面
│  │      │  courseinfolist.jsp		#课程详细信息列表
│  │      │  courselist.jsp			#显示课程列表页面
│  │      │  edit.jsp				#课程编辑页面
│  │      │  editcourse.jsp			#修改课程详细信息
│  │      │  error.jsp				#出错页面
│  │      │  homework.jsp			#学生上传作业界面
│  │      │  index.jsp                         #网站首页界面
│  │      │  list.jsp
│  │      │  listFiles.jsp
│  │      │  login.jsp				#登录页面
│  │      │  message.jsp			#学生第一次发送留言界面
│  │      │  score.jsp				#成绩查询界面
│  │      │  sfifth.jsp				
│  │      │  sfirst.jsp
│  │      │  sforth.jsp
│  │      │  ssecond.jsp
│  │      │  sthird.jsp
│  │      │  student-get-teacherlist.jsp		#学生获取老师资源列表
│  │      │  student-message.jsp			#学生获得留言界面
│  │      │  student-score.jsp				#学生成绩页面
│  │      │  student-send-message.jsp		#学生回复消息页面
│  │      │  student-upload.jsp				#学生上传页面
│  │      │  student.jsp		     			#学生第一次登录界面
│  │      │  stu_SelectCourse.jsp			#学生选课页面
│  │      │  teacher-add-homework.jsp		#老师新增作业页面
│  │      │  teacher-edit-score.jsp			#教师修改成绩页面
│  │      │  teacher-file.jsp				#教师文件页面
│  │      │  teacher-get-homework-dir.jsp		#教师获取作业目录
│  │      │  teacher-list-homework-files.jsp		#教师获取学生提交文件
│  │      │  teacher-message.jsp                      #教师留言界面
│  │      │  teacher-send-message.jsp		#教师发送消息
│  │      │  teacher.jsp					#教师登录成功后的主页面
│  │      │  tfifth.jsp
│  │      │  tfirst.jsp					#显示所有老师
│  │      │  tforth.jsp					#显示老师资源浏览下的目录（包含创建目录的链接)
│  │      │  tlistFiles.jsp					#列出目录下所有文件（包含上传文件的链接)
│  │      │  tsecond.jsp					#显示老师的资源浏览和下载作业链接
│  │      │  tthird.jsp						#显示老师资源浏览下不同科目下的具体文件
│  │      │  
│  │      ├─bootstrap                     #引入的bootstrap库
│  │      │  ├─css
│  │      │  │      bootstrap-theme.css
│  │      │  │      bootstrap-theme.css.map
│  │      │  │      bootstrap-theme.min.css
│  │      │  │      bootstrap-theme.min.css.map
│  │      │  │      bootstrap.css
│  │      │  │      bootstrap.css.map
│  │      │  │      bootstrap.min.css
│  │      │  │      bootstrap.min.css.map
│  │      │  │      
│  │      │  ├─fonts
│  │      │  │      glyphicons-halflings-regular.eot
│  │      │  │      glyphicons-halflings-regular.svg
│  │      │  │      glyphicons-halflings-regular.ttf
│  │      │  │      glyphicons-halflings-regular.woff
│  │      │  │      glyphicons-halflings-regular.woff2
│  │      │  │      
│  │      │  └─js                  
│  │      │          bootstrap.js
│  │      │          bootstrap.min.js
│  │      │          npm.js
│  │      │          
│  │      ├─css                 #学生和教师界面有关样式
│  │      │  │  carousel.css
│  │      │  │  doc.min.css
│  │      │  │  font-awesome.min.css
│  │      │  │  index.css
│  │      │  │  login.css
│  │      │  │  main.css
│  │      │  │  message-stu.css
│  │      │  │  message.css
│  │      │  │  student-message.css
│  │      │  │  student-score.css
│  │      │  │  student.css
│  │      │  │  theme.css
│  │      │  │  
│  │      │  └─teacher       #老师界面有关样式
│  │      │          notice.css
│  │      │          result.css
│  │      │          teacher.css
│  │      │          
│  │      ├─fonts		#网站显示字体
│  │      │  │  fontawesome-webfont.eot
│  │      │  │  fontawesome-webfont.svg
│  │      │  │  fontawesome-webfont.ttf
│  │      │  │  fontawesome-webfont.woff
│  │      │  │  FontAwesome.otf
│  │      │  │  glyphicons-halflings-regular.eot
│  │      │  │  glyphicons-halflings-regular.svg
│  │      │  │  glyphicons-halflings-regular.ttf
│  │      │  │  glyphicons-halflings-regular.woff
│  │      │  │  
│  │      │  └─fontawesome4.2
│  │      │          fontawesome-webfont.eot
│  │      │          fontawesome-webfont.svg
│  │      │          fontawesome-webfont.ttf
│  │      │          fontawesome-webfont.woff
│  │      │          FontAwesome.otf
│  │      │          
│  │      ├─images		#网站所有图片
│  │      │      back.jpg
│  │      │      back1.jpg
│  │      │      back2.jpg
│  │      │      back4.jpg
│  │      │      back5.jpg
│  │      │      blue.jpg
│  │      │      blue2.jpg
│  │      │      classroom.png
│  │      │      dang.jpg
│  │      │      denglu.png
│  │      │      denglumima.png
│  │      │      download.png
│  │      │      file-input.png
│  │      │      homework.png
│  │      │      huojiang.jpg
│  │      │      kecheng.png
│  │      │      laba.jpg
│  │      │      lanqiu.jpg
│  │      │      lianjie.jpg
│  │      │      message.jpg
│  │      │      message.png
│  │      │      mkdir.png
│  │      │      notice.png
│  │      │      one-shot.png
│  │      │      picture.jpg
│  │      │      sanjiao.png
│  │      │      scan.png
│  │      │      score-management.png
│  │      │      score.png
│  │      │      send-message.png
│  │      │      sky.jpg
│  │      │      timg.jpg
│  │      │      wenda.jpg
│  │      │      xingxing.jpg
│  │      │      zhibu.jpg
│  │      │      
│  │      ├─jquery                   #引入的jQuery库
│  │      │      jquery-2.1.1.min.js
│  │      │      jquery-form.min.js
│  │      │      jquery.pagination.js
│  │      │      
│  │      ├─layer
│  │      │  │  layer.js
│  │      │  │  
│  │      │  ├─mobile
│  │      │  │  │  layer.js
│  │      │  │  │  
│  │      │  │  └─need
│  │      │  │          layer.css
│  │      │  │          
│  │      │  └─theme
│  │      │      └─default
│  │      │              icon-ext.png
│  │      │              icon.png
│  │      │              layer.css
│  │      │              loading-0.gif
│  │      │              loading-1.gif
│  │      │              loading-2.gif
│  │      │              
│  │      ├─lib
│  │      │      vue.min.js		#Vue增量式框架
│  │      │      
│  │      ├─script                     #引入的js文件
│  │      │      back-to-top.js
│  │      │      docs.min.js
│  │      │      echarts.js
│  │      │      index.js
│  │      │      jquery-3.5.1.min.js
│  │      │      
│  │      ├─view-helper                #界面布局左边栏框架内容
│  │      │      admin-left-sidebar.jsp
│  │      │      student-left-sidebar.jsp
│  │      │      teacher-left-sidebar.jsp
│  │      │      
│  │      └─WEB-INF
│  │              web.xml		#JavaWeb配置文件
│  │              
│  └─test		#测试类
│      ├─java
│      └─resources
└─target		#是用来存放项目构建后的文件和目录、jar包、war包、编译的class文件，所有都是Maven构建时生成的。
