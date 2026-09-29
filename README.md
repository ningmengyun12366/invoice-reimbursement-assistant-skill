# 柠檬云发票整理、查验及报销助手

本公开源码包只包含 `invoice-reimbursement-assistant` 业务 Skill。公共的 Go 实现、Node.js 打包脚本和依赖代码保留在 `go-script/` 中，便于查看、构建和维护。

## 描述

**名字：** 发票整理_发票归档_发票识别_发票查验_发票采集_发票报销助手_财务会计报销归档助手_柠檬云发票

**描述：**

柠檬云AI财税开放平台：专为财税、财务、会计及企业员工打造的电子发票自动化工具。支持对接邮箱自动抓取收集电子发票，智能识别发票票面数据，实时查验发票真伪、校验票据状态、自动查重；智能完成发票分类、整理、归档，按开票日期、费用项目、金额排序，快速输出标准化报销清单与归档资料。覆盖发票采集、识别、查验、去重、整理、归档、报销全链路，简化会计做账、财务审核、企业报销等财税日常工作，降低发票处理工作量。
✅发票自动收集：链接各种邮箱，自动提取邮箱里的电子发票文件；
✅发票真伪核验：实时连接发票查验系统，自动提取发票关键信息并校验真伪与票据状态；
✅智能整理归档：按费用类型、金额、日期自动分类排序，生成标准化发票报销清单；

详细的 Skill 规则、使用前准备和安装更新流程见 [`invoice-reimbursement-assistant/README.md`](./invoice-reimbursement-assistant/README.md)、[`invoice-reimbursement-assistant/SKILL.md`](./invoice-reimbursement-assistant/SKILL.md) 和 [`invoice-reimbursement-assistant/invoice-reimbursement-assistant-install.md`](./invoice-reimbursement-assistant/invoice-reimbursement-assistant-install.md)。

## 目录结构

- `invoice-reimbursement-assistant/`：当前 Skill 的说明、安装文档、引用资料和资源。
- `go-script/`：Go 命令行实现、公共库和生产打包脚本。

## 生产构建

构建要求 Node.js 20+ 和 Go 1.24+。请在仓库根目录执行：

```powershell
npm ci
node go-script/build.js --env prod invoice-reimbursement-assistant
```

生产发布物生成在 `dist/Skills/invoice-reimbursement-assistant/`。运行时 ZIP 包不包含 `bin/**` 二进制文件，安装时按安装文档下载当前平台对应的二进制。

## 配置与数据安全

- API 凭据由使用者在本地工作区配置，不应写入源码、文档或日志。
- 生产接口通过 `go-script/config/prod.json` 注入发布包。
- 安全问题请按照 [SECURITY.md](SECURITY.md) 私下报告。

## 许可证

本项目自有代码、文档和资源文件采用 [MIT License](LICENSE)；第三方组件与字体许可见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
