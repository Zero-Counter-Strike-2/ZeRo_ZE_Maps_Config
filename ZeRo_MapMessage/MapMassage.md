# ZeRo_MapMessage 地图文本系统配置指南

## 目录
- [系统功能](#系统功能)
- [配置文件位置](#配置文件位置)
- [配置文件结构](#配置文件结构)
- [配置参数详解](#配置参数详解)
- [使用方法](#使用方法)
- [文本类型](#文本类型)
- [完整示例](#完整示例)
- [调试方法](#调试方法)
- [最佳实践](#最佳实践)

## 系统功能

### 核心特性
- ✅ **自动翻译**: 汉化地图中的英文文本
- ✅ **倒计时功能**: 自动识别并处理带数字的倒计时文本
- ✅ **屏幕提示**: 在屏幕中央显示重要信息
- ✅ **聊天显示**: 在聊天框中统一显示所有消息
- ✅ **动画效果**: 文本逐字显示的动画效果
- ✅ **智能过滤**: 自动过滤敏感词汇的文本

## 配置文件位置

配置文件位于: `configs/plugins/ZeRo_ZEModule/ZeRo_MapMessage/`

文件命名格式: `地图名.json` (例如: `ze_minecraft_adventure.json`)

## 配置文件结构

```json
{
  "原文本": {
    "Massage": "翻译后的文本",
    "M-Bool": 是否显示屏幕提示,
    "Value": 预留参数(通常为0)
  }
}
```

## 配置参数详解

### 文本配置参数

| 参数 | 类型 | 必填 | 描述 | 示例 |
|------|------|------|------|------|
| `原文本` | string | 是 | 地图中触发的原始英文文本 | `"The door will open in 30 seconds"` |
| `Massage` | string | 是 | 翻译后的中文文本 | `"门将在30秒后开启"` |
| `M-Bool` | boolean | 是 | 是否在屏幕中央显示提示 | `true` |
| `Value` | integer | 否 | 预留参数(通常设置为0) | `0` |

## 使用方法

### 1. 自动配置生成

系统会在检测到新文本时自动创建配置项：

1. 当地图触发新文本时，自动在配置文件中添加该文本
2. 初始配置使用原文本作为翻译文本
3. 管理员需要手动修改翻译内容

### 2. 手动配置

```json
{
  "The door will open in 30 seconds": {
    "Massage": "门将在30秒后开启",
    "M-Bool": true,
    "Value": 0
  }
}
```

### 3. 功能启用

#### 普通文本显示
```json
{
  "Welcome to the map": {
    "Massage": "欢迎来到这张地图",
    "M-Bool": false,
    "Value": 0
  }
}
```

#### 重要提示文本
```json
{
  "!!! Emergency exit opening !!!": {
    "Massage": "紧急出口正在开启",
    "M-Bool": true,
    "Value": 0
  }
}
```

## 文本类型

### 1. 普通文本
不包含数字的普通提示文本：
```json
{
  "Area secured": {
    "Massage": "区域已安全",
    "M-Bool": false,
    "Value": 0
  }
}
```

### 2. 倒计时文本
包含数字的自动倒计时文本：
```json
{
  "Door opens in 60 seconds": {
    "Massage": "门将在60秒后开启",
    "M-Bool": true,
    "Value": 0
  }
}
```

### 3. 重要提示文本
需要屏幕中央显示的重要信息：
```json
{
  "Boss fight begins": {
    "Massage": "BOSS战开始",
    "M-Bool": true,
    "Value": 0
  }
}
```

## 完整示例

### ze_minecraft_adventure.json

```json
{
  "Welcome to Minecraft Adventure": {
    "Massage": "欢迎来到我的世界冒险",
    "M-Bool": false,
    "Value": 0
  },
  "The portal will activate in 30 seconds": {
    "Massage": "传送门将在30秒后激活",
    "M-Bool": true,
    "Value": 0
  },
  "Ender Dragon fight begins in 10 seconds": {
    "Massage": "末影龙战斗将在10秒后开始",
    "M-Bool": true,
    "Value": 0
  },
  "The bridge will collapse in 45 seconds": {
    "Massage": "桥梁将在45秒后坍塌",
    "M-Bool": true,
    "Value": 0
  },
  "Safe zone reached": {
    "Massage": "已到达安全区域",
    "M-Bool": false,
    "Value": 0
  },
  "!!! Zombies incoming !!!": {
    "Massage": "僵尸来袭",
    "M-Bool": true,
    "Value": 0
  },
  "Chest room opens in 20 seconds": {
    "Massage": "宝箱房间将在20秒后开启",
    "M-Bool": true,
    "Value": 0
  }
}
```

## 调试方法

### 1. 查看控制台输出

```
[地图消息] 已创建配置文件: configs/plugins/ZeRo_ZEModule/ZeRo_MapMessage/ze_map.json
[已新增汉化文本]-The door will open.
```

### 2. 游戏内显示效果

#### 聊天框显示
```
|-[地图消息] 门将在30秒后开启 [ 0:30 ]
|-[倒计时] 门将在10秒后开启
```

#### 屏幕中央提示
```
[提示]
门将在30秒后开启
```

#### Instructor提示(右上角)
```
►[门将在30秒后开启]◄
```

### 3. 自动过滤机制

以下关键词的文本会被自动过滤：
- `recharge`
- `recast` 
- `cooldown`
- `cool`

### 4. 倒计时识别规则

系统支持的倒计时格式：
```json
// ✅ 会被识别为倒计时
{
  "Door opens in 60 seconds": {...},
  "Boss appears in 30": {...},
  "Escape in 120 seconds": {...}
}

// ❌ 不会被识别为倒计时
{
  "Recharge in 30 seconds": {...}, // 包含过滤词
  "Just some text": {...} // 不包含数字
}
```

### 5. 调试命令

```bash
# 重新加载配置文件
map your_map_name

# 查看当前玩家
status

# 启用详细日志
sv_cheats 1
developer 1
```

## 最佳实践

### 1. 文本配置建议

#### 普通信息类
```json
{
  "Area cleared": {
    "Massage": "区域已清理完毕",
    "M-Bool": false,
    "Value": 0
  }
}
```

#### 重要提示类
```json
{
  "!!! Final battle !!!": {
    "Massage": "最终战斗开始",
    "M-Bool": true,
    "Value": 0
  }
}
```

#### 倒计时类
```json
{
  "Escape in 60 seconds": {
    "Massage": "60秒后撤离",
    "M-Bool": true,
    "Value": 0
  }
}
```

### 2. 性能优化建议

1. **合理使用屏幕提示**: 重要信息才设置 `M-Bool: true`
2. **及时清理无用配置**: 删除不再使用的文本配置
3. **避免过长文本**: 屏幕提示文本建议控制在20字以内

### 3. 用户体验优化

#### 文本长度控制
- 聊天显示: 无限制
- 屏幕中央: 建议20字以内
- Instructor提示: 建议15字以内

#### 时间节点把控
- 重要信息: 10秒、30秒、60秒等整数时间点显示
- 临近结束: 每秒显示(10秒内)

#### 显示优先级
1. **倒计时**: 优先级最高
2. **重要提示**: 显示屏幕提示
3. **普通信息**: 仅聊天显示

### 4. 常见问题解决

#### 配置不生效
```json
// ❌ 错误格式 - 缺少必需字段
{
  "Welcome": {
    "Massage": "欢迎"
  }
}

// ✅ 正确格式 - 包含所有必需字段
{
  "Welcome": {
    "Massage": "欢迎",
    "M-Bool": false,
    "Value": 0
  }
}
```

#### 倒计时不准确
```json
// 确保原文本包含正确格式的数字
{
  "Open in 30 seconds": {...} // ✅ 正确
  "Open in thirty seconds": {...} // ❌ 无法识别
}
```

---

*系统会自动学习并创建新的文本翻译配置，您只需要根据需要修改翻译内容和显示设置即可。*