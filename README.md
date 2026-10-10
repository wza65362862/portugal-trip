# 🇵🇹 葡萄牙4日游 · 旅行手册

单个 HTML 文件，零外部依赖，手机打开快、离线也能看。

## 文件结构

```
portugal-trip/
├── public/
│   └── index.html    ← 旅行手册页面（全部内容都在这一个文件里）
├── wrangler.toml     ← Cloudflare Workers 配置
├── package.json
└── README.md
```

## 如何更新页面

修改 `public/index.html` 后 push 到 GitHub，Cloudflare Workers Builds 会自动重新部署。

## GitHub + Cloudflare Workers 自动部署步骤

### 必须在电脑上操作的步骤

1. **克隆代码到本地**
   - 在电脑终端粘贴上方卡片的 clone 命令
   - 进入项目目录：`cd portugal-trip`

2. **在 GitHub 创建仓库**
   - 登录 github.com → New repository → 命名如 `portugal-trip` → Private 或 Public 均可
   - 按提示 push 代码到你的新仓库

3. **在 Cloudflare 连接 GitHub 仓库**
   - 登录 dash.cloudflare.com
   - 左侧菜单 → Workers & Pages → Create → Workers → 连接 GitHub
   - 授权 Cloudflare 访问你的 GitHub
   - 选择 `portugal-trip` 仓库
   - 构建命令留空（静态资源项目无需构建）
   - 部署目录：`/`（wrangler.toml 在根目录）
   - 点击 Deploy

4. **完成**
   - 部署成功后会得到一个 `xxx.workers.dev` 公开网址
   - 以后每次 push 代码到 GitHub，自动重新部署
   - 任何人打开网址就能看，无需登录