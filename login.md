Xiamen Four Letter Communication Technology Co., LtD-Video surveillance management system exists to bypass login verification vulnerability

official website:http://www.four-faith.com/

Vulnerability location

com.fourfaith.dvrplatform.web.mgrcter.usermgr.action.UserInfoAction
Login function:


![WPS图片(1)](https://github.com/GUIqizsq/cve/assets/139303407/35dd186c-d637-4a63-950b-1cf8930f9047)

Tracking JSONUtil toOutputJsonSuccess

If you directly access the login authentication interface without entering the account or password, the system returns true. Then the system enters the background of the system when you access the system again.
![WPS图片(2)](https://github.com/GUIqizsq/cve/assets/139303407/c8f89355-1d5a-4835-ab48-3a05db89c191)

http://122.112.215.131:9280/mgrcter/usermgr/user/Login.action

Returns true, then visit http://122.112.215.131:9280/

Log in to the background successfully and obtain the administrator rights
![WPS图片(3)](https://github.com/GUIqizsq/cve/assets/139303407/8f0f515c-c497-4d3c-990f-9a8de9f3db06)

![WPS图片(4)](https://github.com/GUIqizsq/cve/assets/139303407/e763a76c-6086-4464-ad1e-be5ae9922980)
