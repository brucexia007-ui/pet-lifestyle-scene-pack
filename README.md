# Pet Lifestyle Scene Pack / 宠物生活场景写真套装

根据同一只猫或狗的 3–8 张照片、名字、用户明确提供的性别、性格、穿搭偏好与期望场景，生成身份、个性和场景穿搭一致的柔和生活写真。支持十三个预设场景、健身等自定义场景、单图修复，以及 Codex、Kimi Code、Claude Code 和 WorkBuddy。

## 一段提示词开始

把宠物照片与下面内容一起发给具备看图、生图和 GitHub 访问能力的智能体：

```text
请先读取并执行这个宠物写真 Skill；请自行获取文件，不要让我下载仓库或运行命令：
https://raw.githubusercontent.com/brucexia007-ui/pet-lifestyle-scene-pack/v1.3.0/AGENT_BOOTSTRAP.md

宠物名字：<名字>
宠物性别：<公 / 母 / 未知>
宠物性格：<性格、习惯、喜好，以及不希望出现的形象>
期望场景：<例如健身、旅行、听音乐，或完整十三场景套装>
配色：<可选>
穿搭偏好：<可选，默认自动匹配场景>
装饰配饰：<自动 / 关闭 / 指定>
功能装备：<自动 / 关闭 / 指定>
```

更完整的可复制模板见 [START_HERE.zh-CN.md](START_HERE.zh-CN.md)。智能体会先锁定宠物身份与性格，为每个场景选择不同且合理的功能穿搭，再生成一张校准预览；确认后，每个场景单独生成一张 3:4 竖图。

## 平台入口

- Codex：`$pet-lifestyle-scene-pack`
- Kimi Code：`/skill:pet-lifestyle-scene-pack`
- Claude Code：`/pet-lifestyle-scene-pack`
- WorkBuddy：使用 `compat/workbuddy/SKILL.md`，或运行打包脚本生成专用 ZIP

安装路径、工具映射和豆包兼容边界见 [COMPATIBILITY.md](COMPATIBILITY.md)。

## 构建与验证

```powershell
python scripts/validate_pack.py assets/reference-scenes --check-reference-hashes
python scripts/build_distribution_packages.py --output-dir release
```

验证脚本只使用 Python 标准库。分发脚本会生成通用 ZIP、WorkBuddy ZIP 和 `SHA256SUMS.txt`。

## 许可与隐私

Skill 指令和脚本采用 [MIT License](LICENSE)。十三张饺饺参考图只可按 [非商业参考资产许可](assets/REFERENCE_ASSETS_LICENSE.md) 随本 Skill 使用，不能单独销售、用于训练或加入数据集。用户上传的宠物原图不得写入仓库、示例包或公开目录。
