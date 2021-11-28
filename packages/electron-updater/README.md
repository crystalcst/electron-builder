# electron-updater

This module allows you to automatically update your application. You only need to install this module and write two lines of code!
To publish your updates you just need simple file hosting, it does not require a dedicated server.

See [Auto Update](https://electron.build/auto-update) for more information.

Supported OS:
 - macOS ([Squirrel.Mac](https://github.com/Squirrel/Squirrel.Mac)).
 - Windows (NSIS).
 - Linux (AppImage).


## 增加对tencentOS的支持 用法如下
```typescript
// 注意：你必须把baseUrl放在urls的首位， name明明遵循 estension + Url
// 主要在resolveFiles和newUrlFromBase里面做了处理，如果找到文件name,直接替换当前url，不走原来的拼接方法
// 原因：tencentos 私有读写 如果使用预签名url，需要在服务端一次性得到一批预签名后的url，不能根据baseUrl直接拼接，因为sign会不正确
 const urls = [
   {
     name: 'baseUrl',
     url: 'xxxxx'
   },
   {
     name: 'exeUrl,
     url: 'xxxxx',
   }
 ]
 const options: AllPublishOptions | null | undefined = {
      // requestHeaders: {
      //   authorization,
      // },
      provider: 'generic-tencent-cos',
      urls,
      // url: urls.baseUrl,
    } as unknown as AllPublishOptions;
```
## Credits

Thanks to [Evolve Labs](https://www.evolvehq.com) for donating the npm package name.
