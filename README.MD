## 1. pnpm yarn npm的区别

npm 2.x 存在 一个包里面还有 node_modules 层层嵌套的问题，因为包和包之间存在依赖

- 占用磁盘空间
- 超过了windows的地址栏的限制

yarn出现，解决了这个问题，通过`铺平`的方式

- 但是如果是一个包的不同版本 还是有可能会出现嵌套的问题



yarn和npm后来都解决了这个问题

- 但是还是存在 幽灵依赖的问题。明明没有在dependencies里面声明这个依赖，但是却可以require到
- 万一下回，A包不依赖B包，但是你上一回依赖了，现在就不能用了



pnpm

- 软连接和硬链接。
- 全局只有一个 store存储文件，，其余都是软硬链接，没有多余的文件了。
- .pnpm内容 通过硬链接 指向 store
- .pnpm里面如果有重复的包，就通过软链接互相引用。



优点：

1. 节省空间
2. 速度快



![image-20220908185524408](C:/Users/huawei/AppData/Roaming/Typora/typora-user-images/image-20220908185524408.png)

