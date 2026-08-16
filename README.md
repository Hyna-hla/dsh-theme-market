# dsh-theme-market — DSH Remote 主题包市场

DSH Remote 手机 App 的主题包市场仓库:App 内「设置 → 主题 → 主题市场」直接浏览、预览、一键安装。

**零服务器**:市场数据就是一个 `index.json` 清单 + `themes/` 目录里的主题包,全部走 GitHub raw 分发(App 走镜像加速,国内可用)。

## 投稿自制主题

两种方式:

### 方式一:发 Issue(推荐)

1. 用你的主题制作工具导出 `.dshTheme.zip`(zip 内含 `theme.json`,可选 `preview.png`)
2. 在本仓库发一个 Issue,标题写主题名,把 zip 文件直接拖进 Issue 正文作为附件上传
3. 维护者(或任何有权限的人)下载附件放入 `themes/`、更新 `index.json` 后合并即上架

### 方式二:直接 PR

1. Fork 本仓库,把 `你的主题名.dshTheme.zip` 放进 `themes/`
2. 在 `index.json` 的 `themes` 数组追加一条:

```json
{
  "id": "my-theme",
  "name": "我的主题",
  "author": "你的名字",
  "description": "一句话描述",
  "version": "1.0",
  "palette": ["#背景", "#表面", "#品牌色", "#主文字", "#描边"],
  "zip": "themes/my-theme.dshTheme.zip"
}
```

3. 发 PR,合并后 App 内刷新市场即可看到

## index.json 字段说明

| 字段 | 说明 |
|---|---|
| `id` | 主题唯一 id(与 theme.json 内 id 一致;同 id 安装 = 热替换更新) |
| `name` / `author` / `description` | 展示信息 |
| `version` | 版本号(App 对比本地版本提示更新) |
| `palette` | 5 个色值,市场卡片渲染色板预览(免下载预览图) |
| `zip` | 主题包路径(相对仓库根) |

## 许可

投稿即表示你同意主题包以 MIT 许可发布在本市场仓库中。
