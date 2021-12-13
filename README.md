# LEDデバイスドライバ

2021年度のロボットシステム学で作成したデバイスドライバです。数字を入力することで様々なパターンで点滅します。


___


## 環境

- 本体 : Raspberry Pi 4 

- OS  :  ubuntu 20.04 

___

## 実装内容

このデバイスドライバは講義内に作成した[上田先生のデバイスドライバ](https://github.com/ryuichiueda/robosys_device_drivers/blob/master/myled.c)を改良して作成しています。
- 0を入力すると点灯と消灯の間隔が短くなりながら点滅します。
- 1を入力すると一定のリズムで点滅します。
- 2を入力するとモールス信号で「こんにちは」と光ります。

___

## 使用品

- Raspberry Pi 4  
- ユニバーサル基板
- LED     
- 抵抗　220Ω  
- 導線　2本

___

## 回路

回路は以下のようになります。
![S__21946376 (2)](https://user-images.githubusercontent.com/92443822/145701894-01ea27e6-c837-4c5b-ad10-416956416156.jpg)

LEDはアノード側をGPIO25につなぎ、反対側をGNDに接続してあります。

___

### 実行方法
1.まず以下のようなコマンドを実行してください。

```
$ git clone git@github.com:RyotaHama07/robotsystem2021_devicedriver.git
$ cd robotsystem2021_devicedriver/myled
$ make  
$ sudo insmod myled.ko  
$ sudo chmod 666 /dev/myled0  
```
2.目的の動作をさせるために以下のように入力してください。
#### 点灯と消灯の間隔が短くなりながら点滅

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

## 終了するとき
終了する場合は以下のコマンドを実行してください。

```
$ sudo rmmod myled
$ make clean
```
___

## デモ動画

下のリンクよりデモ動画を見れます。

https://youtu.be/-5IIXfJk4Gs
___

## ライセンス

[GNU General Public License v3.0]



