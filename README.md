我是光年实验室高级招聘经理。
我在github上访问了你的开源项目，你的代码超赞。你最近有没有在看工作机会，我们在招软件开发工程师，拉钩和BOSS等招聘网站也发布了相关岗位，有公司和职位的详细信息。
我们公司在杭州，业务主要做流量增长，是很多大型互联网公司的流量顾问。公司弹性工作制，福利齐全，发展潜力大，良好的办公环境和学习氛围。
公司官网是http://www.gnlab.com,公司地址是杭州市西湖区古墩路紫金广场B座，若你感兴趣，欢迎与我联系，
电话是0571-88839161，手机号：18668131388，微信号：echo 'bGhsaGxoMTEyNAo='|base64 -D ,静待佳音。如有打扰，还请见谅，祝生活愉快工作顺利。

# qr-filetransfer

Transfer files over wifi from your computer to your mobile device by scanning a QR code without leaving the terminal.

![screenshot](demo.gif)

## Install

```
go get github.com/claudiodangelis/qr-filetransfer
```

## How does it work?

This tool binds a web server to the address of your wifi network interface on a random port, and sets a default handler for it. The default handler serves the content and quits the program when the transfer is complete.

The program prints a QR code that encodes the text:

```
http://{address}:{port}
```

Most QR apps can detect URLs in decoded text and act accordingly (i.e.: open the URL with the default browser), so when QR the code is scanned the content starts being downloaded by the mobile browser.

## Usage
![Screenshot](screenshot.jpg)


**Note**: Both computer and device must be on the same wifi network.

On its first run, `qr-filetransfer` will ask you to choose which **network interface** you want to use to transfer the files. Choose the network interface that is connected to your wifi:

```
$ qr-filetransfer /tmp/file
Choose the network interface to use (type the number):
[0] enp3s0
[1] wlp0s20u10
```

_Note: On Linux it usually starts with `wl`._

The choice will be remembered and you will never be prompted again, unless you pass the `-force` argument, or delete the `.qr-filetransfer.json` file that the program stores in the home directory of current user.



---


Transfer a single file

```
qr-filetransfer /path/to/file.txt
```

Zip the file, then transfer it

```
qr-filetransfer -zip /path/to/file.txt
```

Transfer a full directory. Note: the **directory gets zipped** before being transfered

```
qr-filetransfer /path/to/directory
```


## Arguments

- `-debug` increases verbosity
- `-force` ignores saved configuration
- `-zip` zips the content before transferring it


## Authors

- [Claudio d'Angelis](claudiodangelis@gmail.com) ([@daw985](https://twitter.com/daw985) on Twitter)

- [You?](https://github.com/claudiodangelis/qr-filetransfer/fork)
