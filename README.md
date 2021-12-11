# LEDデバイスドライバ

2021年度のロボットシステム学で作成したデバイスドライバです。


___


## 環境

- 本体 : Raspberry Pi 4 

- OS  :  ubuntu 20.04 

___

## 実装内容

このデバイスドライバは講義内に作成した[上田先生のデバイスドライバ](https://github.com/ryuichiueda/robosys_device_drivers/blob/master/myled.c)を改良して作成しています。
- 0を入力すると加速しながら点滅します。
- 1を入力すると一定のリズムで点滅します。
- 2を入力するとモールス信号で「こんにちは」と光ります。

___

## 使用品

- Raspberry Pi 4  
- 基盤  
- LED     
- 抵抗　220Ω  
- 導線　2本

___

## 回路

回路は以下のようになります。

LEDはアノード側をGPIO25につなぎ、反対側をGNDに接続してあります。

___

### 実行方法
1.まず以下のようなコマンドを実行してください。

```
$ git clonehttps://github.com/RyotaHama07/robotsystem2021_devicedriver 
$ cd robotsystem2021_devicedriver/myled/myled.c
$ make  
$ sudo insmod myled.ko  
$ sudo chmod 666 /dev/myled0  
```
2.目的の動作をさせるために以下のように入力してください。
#### 加速しながら点滅

```
$ echo 0 > /dev/myled0
```

#### 一定のリズムで点滅

```
$ echo 1 > /dev/myled0
```

#### モールス信号で「こんにちは」

```
$ echo 2 > /dev/myled0
```
___

## デモ動画


___

## ライセンス

[GNU General Public License v3.0]



