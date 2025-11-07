# Unity WebGL Game - GitHub Pages

这是一个用于托管 Unity WebGL 游戏构建的 GitHub Pages 仓库。

## 使用方法

### 1. 从 Unity 导出 WebGL 构建

1. 在 Unity 中打开你的项目
2. 选择 `File > Build Settings`
3. 选择 `WebGL` 平台
4. 点击 `Build` 或 `Build and Run`
5. 选择一个输出目录

### 2. 将构建文件复制到仓库

Unity 构建后，你会得到一个包含以下内容的文件夹：
- `index.html` (Unity 自动生成)
- `Build/` 目录（包含 .loader.js, .framework.js, .wasm, .data 文件）
- `TemplateData/` 目录（包含样式和资源文件）

**选项 A：使用 Unity 生成的 index.html**
- 直接用 Unity 生成的 `index.html` 替换本仓库的 `index.html`
- 将 Unity 构建的 `Build/` 和 `TemplateData/` 目录复制到仓库根目录

**选项 B：使用自定义的 index.html**
- 修改本仓库的 `index.html` 中的构建路径配置
- 将 `[YourBuildName]` 替换为你的实际构建文件名（不包含扩展名）
- 将 Unity 构建的 `Build/` 和 `TemplateData/` 目录复制到仓库根目录

### 3. 启用 GitHub Pages

1. 将代码推送到 GitHub
2. 进入仓库的 `Settings > Pages`
3. 在 `Source` 中选择 `Deploy from a branch`
4. 选择 `main` (或 `master`) 分支和 `/ (root)` 目录
5. 点击 `Save`

你的游戏将在 `https://[你的用户名].github.io/[仓库名]` 上运行。

## 文件结构

```
.
├── index.html          # 主 HTML 文件
├── Build/              # Unity 构建输出文件（需要从 Unity 构建中复制）
│   ├── *.loader.js
│   ├── *.framework.js
│   ├── *.wasm
│   └── *.data
├── TemplateData/       # Unity 模板资源（需要从 Unity 构建中复制）
│   ├── style.css
│   └── ...
├── StreamingAssets/    # 流式资源（可选）
├── .gitignore
├── .nojekyll          # 确保 GitHub Pages 正确处理所有文件
└── README.md
```

## 注意事项

- `.nojekyll` 文件确保 GitHub Pages 不会使用 Jekyll 处理，这对于 Unity WebGL 构建是必需的
- 确保 Unity WebGL 构建的文件大小在 GitHub 的限制范围内
- 如果文件较大，考虑使用压缩或 CDN

