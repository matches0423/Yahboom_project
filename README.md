# Raspbot

[官方文件](https://www.yahboom.net/study/Raspbot)

[Pi Headless Setup]()

## 初步設置

1. 將Pi連接到網路後，打開終端機輸入```ip a```，會得到以下輸出。
	```
	...
	```
	> 若使用筆電、手機的熱點會方便一些，可以直接在熱點管理頁面看到Pi的網路位置，就不用再連接鍵盤、滑鼠、螢幕到Pi。

2. 將你的裝置連線到與Pi相同的網路後，開啟瀏覽器連線到Pi的jupyter notebook中測試。
	```
	192.168.xxx.xxx:8888
	```

3. 使用ssh做開發。
	```shell
	ssh 192.168.xxx.xxx
	code .
	```
	> ```code```指令可以在 本地端(電腦) 的vscode中開啟 遠端(Pi) 的資料夾，操作會方便一些，不用多學cli的文字編輯器(vim/nano)。

## GitHub設置

可以在[這邊](https://github.com/settings/ssh/new)把Pi上的ssh公鑰加入你自己的GitHub帳號中方便開發。
```shell
ssh-keygen -t rsa
ls ~/.ssh
cat ~/.ssh/id_rsa.pub
```

## Python設置

在程式碼最上方可加入下面的引入就好，不用每次都複製```YB_Pcb_Car.py```。
```python
import raspbot.YB_Pcb_Car as YB_Pcb_Car
```

## Wifi有問題?

修改Pi上的```/etc/wpa_supplicant.conf```，直接貼上以下內容，或是參考[wpa_supplicant.conf](https://w1.fi/cgit/hostap/plain/wpa_supplicant/wpa_supplicant.conf)。

```conf
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=TW
network={
	ssid="網路名稱"
	psk="網路密碼"
}
```

## GPIO有問題?

嘗試修正Pi 5的Python API。
```
...
```
