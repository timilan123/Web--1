# 项目结构

![image-20210726003223529](https://github.com/timilan123/Web-StudentManagement1/tree/main/pic/image-20210726003223529.png)

# 效果展示

## 前端效果

![image-20210726003358946](C:\Users\lan\AppData\Roaming\Typora\typora-user-images\image-20210726003358946.png)

## 后台显示



![image-20210726003412836](C:\Users\lan\AppData\Roaming\Typora\typora-user-images\image-20210726003412836.png)

# 前端代码

## web.xml设置

```html
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd"
         version="4.0">
    <welcome-file-list>
        <welcome-file>/Home.html</welcome-file>
    </welcome-file-list>
</web-app>
```



## 主页代码

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>主页</title>
</head>
<body>
<form action="destination" method="get" autocomplete="off">
	姓名：<input type="text" id="1" name="name"/> <br/>
	年龄：<input type="text" id="2" name="age"/> <br/>
	<input type="submit" id="3"/>
</form>
</body>
</html>
```

# servlet代码

```java
package com.swun.servlet;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/destination")
public class servlet01 extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        String name = req.getParameter("name");
        String age = req.getParameter("age");
        System.out.println("姓名是:"+name+"，年龄是:"+age);
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        super.doGet(req, resp);
    }
}

```

