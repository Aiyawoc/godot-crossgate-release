# CrossGate (Godot)

## 项目简介

CrossGate 是基于 Godot 4.5 引擎开发的复古像素风网络 RPG 客户端，致力于还原与扩展经典《魔力宝贝》玩法。项目采用模块化架构，支持本地资源索引、事件总线解耦、GBK 编解码网络通信等特性。

---

## 主要特性
- **Godot 4.5** 引擎，跨平台支持
- 入口场景：`scenes/UI/loading.tscn`，加载后进入主界面
- 全局单例（Autoload）：CG、core、EventBus、SM、CutScene、TM/AM 等
- 事件驱动架构，模块间通过 EventBus 解耦通信
- TCP 网络通信，GBK 编解码，兼容原版封包格式
- 本地资源自动索引，支持 bin/dat/cut/aut/cgp 等格式
- 地图寻路、等距网格渲染、AStarGrid2D
- UI/世界分层，支持遮罩过场、可见性快照

---

## 目录结构

- `scenes/`         Godot 场景文件
- `scripts/`        GDScript 脚本
- `assets/`         图片、音频等资源
- `docs/`           协议、封包、本地数据结构说明
- `dicts/`          词典、映射表
- `ai/`             AI 行为树与任务
- `themes/`         主题与样式

---

## 快速开始

1. **环境准备**
   - 安装 [Godot 4.5](https://godotengine.org/download)
   - 获取本地资源（如 bin/map/pal），并在 `scripts/loading.gd` 中设置 `CG.workPath` 为你的资源目录

2. **运行项目**
   - 用 Godot 打开本项目根目录
   - 运行主场景 `scenes/UI/loading.tscn`

3. **调试建议**
   - 若资源加载失败，请检查 `CG.workPath` 路径与本地资源完整性
   - 网络协议与封包详见 `docs/封包.md`

---

## Native C++（GDExtension）

- 原生工程目录：`native/crossgate_core`
- 构建说明：`native/crossgate_core/README.md`
- 实施计划：`docs/Godot_C++核心重构实施计划.md`

常用开关（`project.godot`）：
- `crossgate/native/enabled`
- `crossgate/native/resource_enabled`
- `crossgate/native/protocol_enabled`
- `crossgate/native/shadow_compare`

默认发布配置：
- `enabled/resource/protocol = true`
- `shadow_compare = false`
- macOS 发布脚本：`scripts/release/build_macos_release.sh`
  - 需要本机安装对应版本导出模板（默认检查 `~/Library/Application Support/Godot/export_templates/4.6.stable/macos.zip`）

一键回退：
- 将 `crossgate/native/enabled` 设为 `false`，即可全量回退 GDScript 路径。

当前约定：
- 战斗演绎与战斗解析链路已先回退为纯 GDScript，等待重新规划 battle GDE 化范围。

---

## 关键模块说明

- **CG**：全局游戏状态、地图/坐标转换、资源索引
- **core**：二进制读取、base62、工具函数
- **EventBus**：事件总线，模块解耦通信
- **SM**：场景管理，切换与过场动画
- **CutScene**：遮罩过场层
- **TM/AM**：纹理与动画管理
- **GbkUtil**：GBK 编解码网络通信

---

## 贡献与开发规范

- 事件名统一用字符串常量（如 `socket_world_*`、`SM_*`）
- 坐标/方向/计数多用 base62 编码
- UI 输入需兼容中文 IME 与焦点管理
- 详细开发约定见 `.github/copilot-instructions.md`

---

## 参考文档
- [docs/封包.md](docs/封包.md)：网络协议与封包格式
- [docs/自定义封包.md](docs/自定义封包.md)：自定义的网络协议与封包格式
- [docs/Bin文件结构.md](docs/Bin%E6%96%87%E4%BB%B6%E7%BB%93%E6%9E%84.md)：本地资源文件结构
- Godot 官方文档：https://docs.godotengine.org/

---

## TODO:
### 窗口面板
- 名片和家族名片面板
- 发送邮件面板
- 留言板框
- 埋起物品选择框
- 家族兽框
- 捏脸框
- 宠物选择框(未知, 小男生cg与4.0cg均未唤起该面板)

- BZ且window_type为 6/7/s/v/k/m/K 时，创建商店面板. 商店面板包含7种状态: 买/卖/交换/交出/鉴定/修理/水晶币商店
   - 买: 已完成
   - 卖: 已完成, v1封包只能卖第一页背包, 封包v2时支持
   - 交换: 已完成
   - 交出: 
   - 鉴定: 已完成, v1封包只能处理第一页背包, 封包v2时支持
   - 修理: 已完成, v1封包只能处理第一页背包, 封包v2时支持
   - 水晶币商店: 未完成, 封包v2时支持, 待协议补全

银行面板/家族保险箱面板/家族兽饲料箱面板共同使用银行面板: 已完成, 家族保险箱面板/家族兽饲料箱面板待验证. 家族兽饲料箱只可用第一个tab_0, 隐藏另外两个tab, 和所有的tab_btn. 

### 战斗
- 常规封包已完成, 待实现封包v2支持

### 环境特效
- 雨 已完成
- 雪 已完成
- 彩带 已完成
- 云

### 生产技能
- 刻印

### 邮件系统

### 摆摊

### 音效

### Lua UI

### 核心代码C++重写
- 基础数据类库(Graphic等)
- 封包处理
- world场景
- 战斗场景

## 移动端适配
