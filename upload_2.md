The webservice module of mountain flood Disaster monitoring and warning system 2.0 has arbitrary file upload vulnerability

official website:http://www.cdwanjiang.com/

version:2.0

Vulnerability location:

/Service/ImageStationDataService.asmx

![WPS图片(1)](https://github.com/GUIqizsq/cve/assets/139303407/032bd955-cc43-46e8-b74c-fc7821410f33)

Trace class

// MFCW.Web.Service.ImageStationDataService

![WPS图片(2)](https://github.com/GUIqizsq/cve/assets/139303407/4a161657-e616-4393-a580-3e090cb802dc)
![WPS图片(3)](https://github.com/GUIqizsq/cve/assets/139303407/8842b36b-2888-41aa-a7eb-487d46b42a4c)

Enter the SaveImage function:

Unfiltered file types are saved, there is a file upload vulnerability, but a prerequisite for incoming monitorCode must exist in the database. After Upload location/Upload/ImageData/convert the value/getTime monitorCode yyyyMMddHHmmssffff. ImgName suffix.
![WPS图片(4)](https://github.com/GUIqizsq/cve/assets/139303407/2f9540a0-4e49-41f0-8751-1b3772194ea7)

![WPS图片(5)](https://github.com/GUIqizsq/cve/assets/139303407/b7aaa58f-fad6-4f32-9bed-da27fba82979)

Get webshell:/Upload/ImageData/000000/202201290112100000.aspx

![WPS图片(6)](https://github.com/GUIqizsq/cve/assets/139303407/0fe4970c-0091-4071-8b70-dbdd47638c82)
