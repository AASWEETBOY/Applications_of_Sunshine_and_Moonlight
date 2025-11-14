# Applications_of_Sunshine_and_Moonlight
Sunshine+Moonlight+ParsecVDisplay实现**Android平板**成为**Windows电脑**的副屏（**平板与电脑在局域网内**）

**本教程写于2025/11/13(Sunshine：Version 2025.924.154138、Moonlight：v12.1、ParsecVDisplay：v0.45)**
## 参考教程
[sunshine+moonlight+ParsecVDisplay实现平板成为电脑的第二屏幕](https://blog.csdn.net/wwiyou/article/details/147354084)

## 第一步：下载并安装相关软件
1. [SUNSHINE串流工具服务端](https://github.com/LizardByte/Sunshine/releases)
2. [MOONLIGHT串流工具客户端](https://github.com/moonlight-stream/moonlight-android/releases)
3. [ParsecVDisplay虚拟显示器驱动](https://github.com/nomi-san/parsec-vdd/releases)

## 第二步：设置相关软件
1. 安装好Sunshine，鼠标双击主程序。初次打开，默认直接打开浏览器访问其web后台localhost地址（若不小心关闭了网站，请在托盘鼠标右键点击sunshine图标，再点击open sunshine也可进入sunshine网页端后台）。仅初次打开：需设置登陆密码，然后再输入自己设置的账户名与密码登录后台。以后打开，直接默认登陆后台。<br>
<img width="425" height="202" title="在托盘鼠标右键点击sunshine图标，再点击open sunshine即可进入sunshine网页端后台" alt="image" src="https://github.com/user-attachments/assets/3c424c60-db8d-4a92-82dc-73c62c476687" /><br>
<br>
2. 设置本地化语言，保存并应用（可选）<br>
<img width="936" height="455" title="设置本地化语言" alt="image" src="https://github.com/user-attachments/assets/eb0b4c6f-473e-46bd-8ee5-c8d89ea32500" /><br>
<br>
3. 请确保平板和电脑连接了同一WiFi（此WiFi必须没有AP隔离，所以本教程排除校园网用户），再打开Moonlight软件，此时检测到可连接的电脑设备。若没有，请点击加号，输入已安装sunshine软件的电脑的ip地址，试试是否能连接上。<br>
<img width="639" height="322" title="手动加入要串流的电脑设备" alt="image" src="https://github.com/user-attachments/assets/8133c256-8fdf-474a-8f95-7521ecdc823f" /><br>
<br>
4. 连接上后，点击电脑设备，点击第一个desktop按钮。首次连接，输入连接的PIN码，即可连接成功。平板和电脑都显示电脑画面，并且平板也可以操作电脑。（到此步，完成基本的<b>复制屏幕</b>的效果，而<b>非副屏之效果</b>）<br>
<img width="651" height="281" title="点击Desktop按钮" alt="image" src="https://github.com/user-attachments/assets/a3c60ea0-85fe-4d7b-982f-2fd96d01b93b" /><br>
<br>
5. 打开ParsecVDisplay，设置特定分辨率——点击Custom Display Modes，根据平板的分辨率对应设置slot1的数值，再点击Apply，关闭重启程序<br>
<img width="967" height="533" title="设置特定的分辨率" alt="image" src="https://github.com/user-attachments/assets/b2ab99b4-b4d4-4a4b-9ff1-9e540f8601b9" /><br>
<br>
6. 接上一步，新建并设置对应的虚拟显示器，并记住其名称（图中示例为\\.\DISPLAY8）<br>
<img width="962" height="527" title="新建虚拟显示器" alt="image" src="https://github.com/user-attachments/assets/0eb3e38b-a808-491a-8a60-40951b163b2a" /><br>
<img width="577" height="506" title="选择对应的分辨率与刷新率（以我的平板2560*1600@60Hz为例）" alt="image" src="https://github.com/user-attachments/assets/6e950973-2eec-4835-a4a3-6b3420c02e6b" /><br>
<br>
7. 回到sunshine的后台，在图中位置（配置-Audio/Video-config.output_name_windows）把名称输入，并取消勾选“安装 Steam 音频驱动程序”与“流音频”两项（保证副屏的声音走电脑端，避免副屏播放视频无声），保存并应用。<br>
<img width="542" height="813" title="配置-Audio/Video的相关设置" alt="image" src="https://github.com/user-attachments/assets/71340c01-5e97-4f67-b6c2-a58fa90413e0" /><br>
<br>
8. 打开<b>电脑的设置</b>，必须设置添加的虚拟显示器为主显示器，屏幕设置为扩展模式（设置为“扩展这些显示器”）<br>
<img width="857" height="636" title="电脑上需做的必要设置" alt="image" src="https://github.com/user-attachments/assets/f2d8d544-c6ee-4c7a-a197-83f824878b63" /><br>
<br>
9. 打开Moonlight软件首页左侧栏中的设置，完成对视频分辨率的设置（设置为“本地”分辨率）、帧数（例如为“60帧”，与自己先前设置的刷新率一致）、码率（拉到最高即可）、帧速调节（设置为“优先最低延迟”即可）<br>
<img width="2560" height="1526" title="设置客户端接收的分辨率为本地分辨率" src="https://github.com/user-attachments/assets/aec32fae-7679-4408-a22c-61acf65a9f72" /><br>
<br>
10. 完成以上步骤，再点击Moonlight软件串流列表中的可连接的电脑设备，点击Desktop，即可<b>使平板变为副屏</b>。<br>
