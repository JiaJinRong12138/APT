## Js样本分析

因为自己从来不会Js，今天在荣神的带领下，搞懂了大概的流程



拿到样本的情况

![image-20210902183018092](APT_Fin7_JS/image-20210902183018092.png)

https://lelinhtinh.github.io/de4js/ : for remove obfuscation of strings and hexa format, you can use de4js

Lots of attackers use [http://obfuscator.io](https://t.co/npCUdfpTvF?amp=1) as packer, that's based on a single array and some logical op (bitwise, rot...)



de4js解密出的样子:

![image-20210902183211401](APT_Fin7_JS/image-20210902183211401.png)



如果产用调试功能的话：

```html
<html>
<body>
<script>

.....

</script>
</body>
</html>
```



就可以在chrome里面进行调试了

![image-20210902183402272](APT_Fin7_JS/image-20210902183402272.png)



可以console来动态跑来获取解密的字符串（因为这里都在_0x3edc位置进行解密了）

![image-20210902183708091](APT_Fin7_JS/image-20210902183708091.png)

因为顺序是4 0 5 3 1 2



一般js中的执行都是eval，所以尽量去这里来观察附近的参数等等



![image-20210902183816703](APT_Fin7_JS/image-20210902183816703.png)

获取第二层的代码

![image-20210902183914400](APT_Fin7_JS/image-20210902183914400.png)

利用第二层的代码和第一层的代码进行解密

运行后发现最后的解密

![image-20210902184313103](APT_Fin7_JS/image-20210902184313103.png)



脚本：

https://www.cnblogs.com/c-x-a/p/12012665.html
