# 训练营演示-快团团素材生成器

已导入原版源码，并完成两处海报样式调整。本次发布目标为以下公开仓库和 GitHub Pages；实际发布结果以构建及在线页面检查为准。

- 仓库：[duuhuang-ai/xunlianying-demo-ktt-template-generator](https://github.com/duuhuang-ai/xunlianying-demo-ktt-template-generator)
- 在线工具：[训练营演示-快团团素材生成器](https://duuhuang-ai.github.io/xunlianying-demo-ktt-template-generator/)

## 源码来源

- 原仓库：[duuhuang-ai/ktt-template-generator](https://github.com/duuhuang-ai/ktt-template-generator)
- 原网页：[快团团商品海报生成器](https://duuhuang-ai.github.io/ktt-template-generator/outputs/ktt-template-generator.html)
- 导入日期：2026-10-11。
- 导入提交：`faacaf6845060a51aff311554dcd0c46c4911a25`，保留原仓库历史。
- `upstream` 指向原仓库，用于追溯来源；`origin` 在本次发布时设置为新的训练营演示仓库，发布分支为 `main`。

## 本地预览

在项目目录启动，不需要安装依赖：

```sh
python3 -m http.server 8765 --bind 127.0.0.1
```

打开 [本地预览](http://127.0.0.1:8765/)。首页会跳转到工具页面。启动服务的终端按 `Ctrl+C` 可停止服务。

原版支持单商品编辑、三种海报模板、主图与二维码选择，以及单张 PNG 导出。页面刷新后输入不保留。

## 修改位置

- `outputs/ktt-template-generator.html`：主要源文件，包含页面结构、样式和交互代码。
- `index.html`：入口跳转页。
- `AGENTS.md`：工作规则。
- `docs/superpowers/specs/2026-10-11-ktt-template-generator-v1-design.md`：已有批量版需求评审稿，尚未实施。

修改 HTML 后保存，再刷新本地预览即可看到效果，无需构建。

## 本地修改

2026-10-11：顶部标签改为黄色底、深灰字；居中促销和大图爆款模板的主图下方卖点向下移动 32 像素。预览和 PNG 导出共用同一绘制函数。

## 本次验证

2026-10-11 已确认两份 HTML 与导入的上游提交一致、本地 HTTP 返回 200 且内容一致、内联 JavaScript 通过 `node --check`，并在浏览器确认首页跳转及示例海报渲染。

样式修改后，JavaScript 语法检查和 `git diff --check` 通过；已在浏览器检查三种模板的示例预览，并检查居中促销模板的两行标题、六条卖点组合，底部内容仍完整显示，浏览器未捕获到错误或警告。

尚未验证真实图片上传、PNG 文件下载完成、实际二维码识别或批量版需求验收。内置浏览器的 PNG 下载事件等待超时，不能据此声称下载已通过；此项需在普通浏览器进一步确认。

## 发布方式

GitHub Pages 使用 `main` 分支的根目录作为发布源，入口为 `index.html`，无需安装依赖或本地构建。`.nojekyll` 让 Pages 按普通静态文件发布。

后续修改先完成本地验证，再获得推送与发布授权。发布后核对远程提交 SHA、Pages 构建状态和线上文件内容，不能只以 `git push` 成功判断发布完成。
