# 部署说明（2026-11-18 起）

这个仓库是 **Source 分支**（Hexo 源码），发布产物推到 `master`，GitHub Pages 从 `master` 出。

## 站点定位

本站在 2026-11-18 收口为**学生时期归档**（2021–2023）：

- 新文章一律写进主站：<https://liegu0317.top/writing/>
- 这里的旧文保留原样，不再更新
- 全站左下角挂了一条归档提示，**它是注入到构建产物 `js/events.js` 里的**（见下）

## 重新构建后必须补的一步

`hexo generate` 会覆盖 `master` 的 `js/events.js`，归档条随之丢失。构建后把下面这段追加到
`public/js/events.js` 末尾再推送（原实现见 `master` 分支该文件的末尾）：

```js
/* 2026-11-18 站点收口：正文迁至主站 /writing/，此处为学生时期归档 */
(function () {
  if (document.querySelector('.lg-archive-bar')) return;
  var css = '.lg-archive-bar{position:fixed;left:12px;bottom:12px;z-index:9999;max-width:calc(100vw - 24px);'
    + 'background:rgba(0,47,167,.94);color:#fff;font:12px/1.55 -apple-system,BlinkMacSystemFont,"Segoe UI","Noto Sans SC",sans-serif;'
    + 'padding:7px 12px;border-radius:3px;box-shadow:0 2px 10px rgba(0,0,0,.16);letter-spacing:.02em}'
    + '.lg-archive-bar a{color:#fff;text-decoration:underline;text-underline-offset:2px}'
    + '@media(max-width:768px){.lg-archive-bar{font-size:11px;left:8px;bottom:8px;padding:6px 10px}}';
  var st = document.createElement('style'); st.textContent = css; document.head.appendChild(st);
  var bar = document.createElement('div');
  bar.className = 'lg-archive-bar';
  bar.innerHTML = '2021–2023 学生时期归档　新文章在 <a href="https://liegu0317.top/writing/">liegu0317.top/writing</a>';
  document.body.appendChild(bar);
})();
```
