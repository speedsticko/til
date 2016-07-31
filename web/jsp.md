JSPs, JSTLs
===========

Java Server Pages (JSP) make it easier to create HTML content from servlets. 

JSPs allow you to create custom tags but it's kind of tedious, luckily JSP 2.0 Tag Files let you do the same thing but more easliy.

The Java Standard Template Libary (JSTL) is a standard set of tags that you can use in your JSP pages.

How to implement layouts using JSP and tags
-------------------------------------------
0. Get Jars for the JSTL for your Servlet Container. For Tomcat you need at least __taglibs-standard-spec-1.2.5__ and __taglibs-standard-impl-1.2.5__
1. Create a MainLayout.tag file in WEB-INF/tags that has the page HTML and with a <jsp:doBody> tag
```
<%@tag description="Common Screen Layout" pageEncoding="UTF-8"%>
<%@taglib prefix="t" tagdir="/WEB-INF/tags" %>
<%-- The list of normal or fragment attributes can be specified here: --%>
<%@attribute name="message"%>
<%-- any content can be specified here e.g.: --%>
<!DOCTYPE HTML>
<html>
    <head>
        <title>Main Panel</title>
        <link rel="stylesheet" type="text/css" href="css/style.css">
    </head>
    <body>
        <jsp:doBody />
    </body>
</html>
```
2. Create a JSP page that references and uses your tag library
```
<%@page contentType="text/html" pageEncoding="UTF-8" session="true"  %>

<%@taglib prefix="t" tagdir="/WEB-INF/tags" %>
<%@ taglib prefix="c" uri="http://java.sun.com/jsp/jstl/core" %>

<t:MainLayout message="${message}">
    <div class="main" width: 100%;">
        Content ...
    </div>
</t:MainLayout>
```
