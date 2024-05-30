pifield-monitor
====================

Pi-field のインターフェースを監視するためのツール類を提供します。  

## 提供ファイル  
次のファイルとディレクトリがパッケージに含まれています。  

### /usr/bin/pifieldstat
取得したデータを表示するための実行ファイルです。  
オプション無しで実行した場合にはステータス一覧を表示します。  
使用可能なオプションを次に示します。  

* capacity  
  蓄電池の容量を表示します。  
  単位は[mAh]です。  

* current  
  蓄電池の充放電電流を表示します。  
  単位は[mA]です。  
  正の値は充電、負の値は放電を表しています。

* percentage  
  蓄電池の容量を表示します。  
  単位は[%]です。  

* temperature  
  蓄電池の温度を表示します。  
  単位は[℃]です。   

* voltage  
  蓄電池の電圧値を表示します。  
  単位は[mV]です。  

* -d, debug  
  デバッグ情報を含むすべてのデータを json 形式で表示します。  

* -h, help  
  ヘルプを表示します。  

* -v, version  
  バージョンを表示します。  

### /usr/sbin/pifieldmon
Pi-field のインターフェースを監視するための実行ファイルです。  
/run/pifield-monitor/monitor.sock に取得したデータを出力します。  

### /etc/pifield-monitor/monitor.yml  
Pi-field の監視動作を設定するための YAML ファイルです。  
設定可能な項目は各セクションに分かれています。  

* serial  
  シリアルインターフェースのセクションです。  

  - type  
    監視対象の製品名です。  

    - pifieldmini  
      デフォルトは pifieldmini です。  

  - port  
    監視するシリアルインターフェースのポート名です。  
    デフォルトは /dev/ttyPIFIELD です。  

### /etc/udev/rules.d/99-pifield-usb-serial.rules  
Pi-field のシリアルインターフェースを設定するためのファイルです。  

### /lib/systemd/system/pifield-monitor.service  
Pi-field の監視サービスを実行するためのファイルです。  
pifieldmon をデーモンとして動作させます。 

### /usr/share/doc/pifield-monitor/changelog.Debian.gz  
パッケージの変更履歴を記録したファイルです。  

### /usr/share/doc/pifield-monitor/copyright  
著作権とライセンスを記載したファイルです。  

### /usr/share/doc/pifield-monitor/examples/ 
サンプルスクリプトが含まれているディレクトリです。  
