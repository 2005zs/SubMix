# SubMix

🚀 一个强大的代理订阅链接转换器，将单独的代理订阅链接转换为 Mihomo 内核 YAML 配置文件

[![Deploy to Vercel](https://vercel.com/button)](https://vercel.com/import/project?template=https://github.com/YoungLee-coder/SubMix)
[![Deploy to Cloudflare Pages](https://img.shields.io/badge/Deploy%20to-Cloudflare%20Pages-orange?style=for-the-badge&logo=cloudflare)](https://dash.cloudflare.com/?to=/:account/pages/new)

## ✨ 功能特性

- 🔄 **多协议支持**：VLESS、Hysteria2、Shadowsocks、Trojan
- 🎯 **智能解析**：自动解析订阅链接并生成标准 YAML 配置
- 🎨 **现代化界面**：基于 shadcn/ui 的美观界面，支持深色模式
- 📝 **节点管理**：可视化编辑、排序、删除节点
- 🛡️ **完整规则集**：基于 @Loyalsoldier/clash-rules 的高质量规则
- ⚡ **一键操作**：快速生成、复制、下载配置文件

## 🚀 快速开始

### 本地开发

```bash
# 安装依赖
pnpm install

# 启动开发服务器
pnpm dev

# 构建生产版本
pnpm build
pnpm start
```

### 一键部署

点击上方的部署按钮，即可快速部署到 Vercel 或 Cloudflare Pages。

## 📖 使用方法

1. **添加节点**：在左侧输入框粘贴订阅链接，选择单个或批量模式
2. **管理节点**：编辑节点信息，调整排序，删除不需要的节点
3. **配置路由**：选择白名单或黑名单模式
4. **生成配置**：系统自动生成完整的 Mihomo YAML 配置
5. **导出使用**：复制或下载配置文件到您的代理客户端

## 🔧 支持的协议格式

### VLESS
```
vless://uuid@server:port?type=ws&path=/path&security=tls&sni=domain#name
```

### Hysteria2
```
hysteria2://password@server:port?obfs=salamander&sni=domain#name
```

### Shadowsocks
```
ss://method:password@server:port#name
```
支持传统 SS 和 SS2022 新型加密方法

### Trojan
```
trojan://password@server:port?type=ws&path=/path&sni=domain#name
```

## ⚙️ 配置说明

### 代理组
- 🚀 **手动切换**：手动选择节点
- ♻️ **自动选择**：基于延迟自动选择
- 🔯 **故障转移**：主节点故障时自动切换
- 🔮 **负载均衡**：多节点负载平衡

### 路由模式
- **白名单模式**（推荐）：未匹配规则的流量走代理
- **黑名单模式**：只有指定流量走代理

### 规则集
基于 @Loyalsoldier/clash-rules，包含广告拦截、分流规则、GeoIP 数据等完整功能

## 🛠️ 技术栈

- **前端**：Next.js 15 + TypeScript + Tailwind CSS
- **UI**：shadcn/ui + Radix UI
- **协议解析**：自定义解析器
- **配置生成**：YAML 格式输出

## 📁 项目结构

```
├── app/
│   ├── api/convert/route.ts    # 转换 API
│   ├── page.tsx               # 主页面
│   └── layout.tsx             # 布局
├── components/ui/             # UI 组件
├── lib/
│   ├── proxy-parser.ts        # 协议解析器
│   ├── mihomo-config.ts       # 配置生成器
│   └── utils.ts               # 工具函数
└── README.md
```

## 📄 许可证

MIT License

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## ⚠️ 免责声明

本工具仅用于学习和测试目的，请遵守当地法律法规。