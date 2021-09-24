# baidu-submit-github-action

> 使用 API 提交方式向百度搜索主动推送 URL 的 **Github Actions** 模版

## 使用方法

1. Fork 这个项目
2. 添加一个叫 `BAIDU_TOKEN` 的 Actions secrets

   关于如何获取 token 点[这里](https://ziyuan.baidu.com/college/courseinfo?id=267&page=2#h2_article_title14)。

3. 重命名 `.github/workflows/baidu-submit.yml.sample` 文件为 `.github/workflows/baidu-submit.yml`
4. 替换 `example.com` 为你的网站域名并修改 `sitemap` 路径

```sh
echo "SITE_URL=http://example.com" > .env \
&& echo "SITEMAP_URL=http://example.com/sitemap.xml" >> .env \
```

5. 修改要提交的 schedule 时间

```
schedule:
  - cron: "30 12 * * *"
  - cron: "30 23 * * *"
```

6. 保存，提交，完成配置

每次 action 执行后，可以在 baidu-submit.log 查看执行结果。

如果有多个网站要提交，可以复制一份 `baidu-submit.yml` 保存为 `baidu-submit2.yml` ，并修改新的文件里的网站域名和 `sitemap` 路径。如果新的网站的 baidu token 不同，添加一个新的 Actions secrets，命名为 `BAIDU_TOKEN2`，并修改 `baidu-submit2.yml` 里的内容。

## Related

- [baidu-submit.sh](https://github.com/PipecraftNet/baidu-submit.sh) - 使用 API 提交方式向百度搜索主动推送 URL 的 shell 脚本

## License

Copyright (c) 2021 [Pipecraft][my-url]. Licensed under the [MIT license][license-url].

## >\_

[![Pipecraft](https://img.shields.io/badge/https://-pipecraft.net-brightgreen)](https://www.pipecraft.net)
[![PZWD](https://img.shields.io/badge/https://-pzwd.net-brightgreen)](https://pzwd.net)

[my-url]: https://www.pipecraft.net
[license-url]: LICENSE
