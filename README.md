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

## 実行方法
まず以下のようなコマンドを実行してください。

```
$ git clone https://github.com/Dansato1203/Robosys2020_devicedriver  
$ cd Robosys2020_devicedriver/myled  
$ make  
$ sudo insmod myled.ko  
$ sudo chmod 666 /dev/myled0  
```


