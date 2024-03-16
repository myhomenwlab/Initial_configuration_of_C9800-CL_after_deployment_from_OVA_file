# Initial configuration of C9800-CL after deployment from OVA file

## 概要
Cisco Catalyst 9800-CL を OVA ファイルから展開した直後の初期コンフィグをまとめています。
主にバージョンによる差異を確認する用途の使い方を想定しています。
OVA ファイルを展開する際に Customize template の設定を行っているためチューニングの影響を受ける項目がある点に留意してください。

注意点としてユース ケースを踏まえた設定はしていないため、
例えば「FlexConnect を利用しているので Flex Profile の関連設定の差分を知りたい」ような用途には適していません。
初期コンフィグの取得に焦点を当ててる関係で、明示的な Flex Profile の設定を行っていないですし、デフォルトの設定が存在するわけでもないので差分が表示されないためです。
そのような場合は既存環境の設定を検証機に投入した上でアップグレードするなどして自身で確認してください。


## 取得時の設定
OVA ファイルを展開する際の設定を記載します。

| 設定項目                                                     | 設定値              |
|--------------------------------------------------------------|---------------------|
| Configuration                                                | 3K APs, 32K Clients |
| 1.1 Hostname                                                 | wlc01               |
| 1.2 Enable Password                                          | Pa$$w0rd            |
| 2.1 Device Management/Service Interface                      | GigabitEthernet1    |
| 2.2 Device Management/Service Interface IPv4 Address/Netmask | 192.0.2.101/24      |
| 2.3 Device Management/Service Interface IPv4 Gateway         | 192.0.2.254         |
| 2.4 Remote Device Management/Service Network Route/Netmask   | 0.0.0.0             |
| 3.1 Login Username                                           | admin               |
| 3.2 Login Password                                           | Pa$$w0rd            |
| Serial Number for the C9800-CL Instance                      | 94TSWI79AYW         |
| PnP Token                                                    |                     |


## 設定取得コマンド
設定を取得するためのコマンドを書き残しておきます。  


### show run パターン

```
terminal length 0


show version


show running-config

```

## show run all パターン

```
terminal length 0


show version


show running-config all

```


## 関連ドキュメント
関連するドキュメントのリンクを掲載します。

Cisco Catalyst 9800 Series Wireless Controllers - Release Notes - Cisco
https://www.cisco.com/c/en/us/support/wireless/catalyst-9800-series-wireless-controllers/products-release-notes-list.html


Cisco Catalyst 9800 Series Wireless Controllers - Configuration Guides - Cisco
https://www.cisco.com/c/en/us/support/wireless/catalyst-9800-series-wireless-controllers/products-installation-and-configuration-guides-list.html

