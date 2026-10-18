# oil-skills

在 Claude Code 中安装 oil-tone、oil-ui 和 oil-motion。此仓库由 larryboiNEUQ 做社区打包，不是上游官方发行，也不代表已收录于 Anthropic 官方插件目录。

## 安装并使用

在 Claude Code 中依次运行：

```text
/plugin marketplace add larryboiNEUQ/oil-skills
/plugin install oil-suite@oil-skills
```

安装完成后重启 Claude Code。按任务调用技能，例如：

```text
/oil-suite:oil-tone 润色下面的产品介绍，保留事实和数字，删掉空泛表达。
/oil-suite:oil-ui 为课程预约页面探索三种不同的设计方向，做成对比页。
/oil-suite:oil-motion 把已有产品视频接成随滚动变化的网页动画，先做一段可验收的小样。
```

本仓库有意只提供一个插件 `oil-suite`，一次安装三个技能，不分别发布插件。插件使用标准 `skills/` 目录发现，技能正文、脚本、资源和相对路径保留上游原样。插件清单没有声明 hooks、权限或 MCP 服务。

## 准备任务所需依赖

安装插件不会自动安装上游脚本依赖。需要运行脚本时，再按对应目录的说明准备环境。

- oil-tone 的写作规范不需要额外服务。可选的 `scripts/tone_lint.py` 使用 Python 3。
- oil-ui 的版本检查和对比页构建使用 Python 3。截图工具需要 Node.js 22 及 Chrome、Chromium 或 Edge。具体用法见[工具说明](plugins/oil-suite/skills/oil-ui/references/tools.md)。
- oil-motion 的本地媒体处理需要 Python 3.10+、Pillow、ffmpeg 和 ffprobe。凭据组件需要 Node.js 22.18+ 及其锁定依赖。详见[技能说明](plugins/oil-suite/skills/oil-motion/SKILL.md)和[凭据配置](plugins/oil-suite/skills/oil-motion/references/api-key-setup.md)。

生成图片和视频默认使用 ZenMux，需要用户自己的 `ZENMUX_API_KEY`，调用可能产生费用。处理已有素材不需要生成服务的 Key。不要把密钥贴进聊天、提交到仓库或写进插件目录。按上游流程使用本机凭据配置页，或使用可信环境已有的密钥注入。安装插件不表示授权调用收费服务。

## 更新整个插件

不要对 marketplace 管理的副本执行 oil-ui 上游自更新命令，即使上游技能提示有新版本。`scripts/check_update.py --update` 调用的更新命令会把 `--path` 指向嵌套的技能目录，不能依赖仓库根目录的 git 检查阻止替换。上游版本提醒不等于本打包仓库已有新版本。

要更新本插件，在 Claude Code 中依次运行：

```text
/plugin marketplace update oil-skills
/plugin update oil-suite@oil-skills
```

更新完成后重启 Claude Code。可在启动 Claude Code 前设置环境变量 `OIL_NO_UPDATE_CHECK=1`，关闭 oil-ui 的上游版本检查。此变量不负责更新插件，也不会修改技能文件。

## 核对来源与许可

- [oil-tone](https://github.com/oil-oil/oil-tone) 和 [oil-ui](https://github.com/oil-oil/oil-ui) 的 MIT 版权持有人为 oil-oil。
- [oil-motion](https://github.com/oil-oil/oil-motion) 的 MIT 版权持有人为 Lin Zhihuang。
- Instrument Serif 字体保留 SIL OFL 1.1，Alpine.js 保留文件内的 MIT 声明。

[第三方声明](THIRD_PARTY_NOTICES.md)列出固定提交与许可证位置。[provenance.json](provenance.json)记录源目录、目标目录和排除规则。[根许可证](LICENSE)保留上游版权及打包维护者署名，不替代字体 OFL 或各文件的许可声明。

## 校验打包格式

在仓库根目录运行已安装的 Claude CLI：

```sh
claude plugin validate .claude-plugin/marketplace.json --strict
claude plugin validate plugins/oil-suite --strict
```

GitHub Actions 使用相同命令，只检查打包格式，不运行上游媒体生成、凭据操作或测试套件。格式校验通过不代表这些功能已完成端到端验证。
