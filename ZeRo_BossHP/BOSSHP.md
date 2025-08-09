# ZeRo_BossHP BOSS血量系统配置指南

## 目录
- [配置文件位置](#配置文件位置)
- [配置文件结构](#配置文件结构)
- [配置参数详解](#配置参数详解)
- [实体类型支持](#实体类型支持)
- [完整配置示例](#完整配置示例)
- [使用方法](#使用方法)
- [功能特性](#功能特性)
- [调试方法](#调试方法)

## 配置文件位置

配置文件位于: `configs/plugins/ZeRo_ZEModule/ZeRo_BossHP/`

文件命名格式: `地图名.json` (例如: `ze_minecraft_adventure.json`)

## 配置文件结构

```json
{
  "实体HammerID": {
    "Name": "BOSS显示名称",
    "BOSSbar": 是否启用BOSS血条,
    "BossEnd": BOSS死亡时是否显示排行榜,
    "MAXHP": 自定义最大血量,
    "BoolMONEY": 是否启用金钱奖励,
    "BMONEY": 击打BOSS获得的金钱数量
  }
}
```

## 配置参数详解

### BOSS配置参数

| 参数 | 类型 | 描述 | 示例 |
|------|------|------|------|
| `Name` | string | BOSS在游戏中的显示名称 | `"末影龙"` |
| `BOSSbar` | boolean | 是否启用BOSS血条显示 | `true` |
| `BossEnd` | boolean | BOSS死亡时是否显示伤害排行榜 | `true` |
| `MAXHP` | integer | 自定义最大血量(0为使用实体默认) | `10000` |
| `BoolMONEY` | boolean | 是否启用金钱奖励机制 | `true` |
| `BMONEY` | integer | 每次击打BOSS获得的金钱 | `50` |

## 实体类型支持

### 支持的BOSS实体类型

1. **math_counter** - 数学计数器实体
2. **func_physbox** - 物理盒子实体  
3. **func_physbox_multiplayer** - 多人物理盒子
4. **func_breakable** - 可破坏实体
5. **prop_dynamic** - 动态属性实体

### 触发机制

- **math_counter**: 通过 `OutValue` 输出触发
- **其他实体**: 通过 `OnHealthChanged` 或 `OnDamaged` 输出触发

## 完整配置示例

### ze_minecraft_adventure.json

```json
{
  "123456": {
    "Name": "末影龙",
    "BOSSbar": true,
    "BossEnd": true,
    "MAXHP": 15000,
    "BoolMONEY": true,
    "BMONEY": 100
  },
  "123457": {
    "Name": "凋零",
    "BOSSbar": true,
    "BossEnd": false,
    "MAXHP": 8000,
    "BoolMONEY": true,
    "BMONEY": 50
  },
  "123458": {
    "Name": "守卫者",
    "BOSSbar": false,
    "BossEnd": false,
    "MAXHP": 0,
    "BoolMONEY": false,
    "BMONEY": 0
  }
}
```

## 使用方法

### 1. 配置文件创建

1. 进入目录: `configs/plugins/ZeRo_ZEModule/ZeRo_BossHP/`
2. 创建以地图名命名的JSON文件
3. 系统会自动生成基础模板

### 2. 获取Hammer ID

在Hammer编辑器中:
1. 选择BOSS实体
2. 查看属性面板的 "Entity Index"
3. 或使用游戏内调试命令

### 3. 配置BOSS参数

```json
{
  "你的BOSS实体ID": {
    "Name": "BOSS显示名称",
    "BOSSbar": true,
    "BossEnd": true,
    "MAXHP": 自定义血量,
    "BoolMONEY": 是否启用金钱,
    "BMONEY": 金钱数量
  }
}
```

### 4. 功能启用建议

#### 基础BOSS (仅显示血量)
```json
{
  "实体ID": {
    "Name": "基础BOSS",
    "BOSSbar": false,
    "BossEnd": false,
    "MAXHP": 0,
    "BoolMONEY": false,
    "BMONEY": 0
  }
}
```

#### 完整功能BOSS
```json
{
  "实体ID": {
    "Name": "完整功能BOSS",
    "BOSSbar": true,
    "BossEnd": true,
    "MAXHP": 10000,
    "BoolMONEY": true,
    "BMONEY": 50
  }
}
```

## 功能特性

### 1. 血量显示
- 实时显示BOSS当前血量
- 支持百分比显示
- 自动消失机制(5秒无更新后隐藏)

### 2. 伤害统计
- 每个玩家的总伤害记录
- DPS(每秒伤害)计算
- 攻击持续时间(ETA)统计
- 实时伤害显示(-XX)

### 3. 伤害排行榜
- BOSS死亡时显示前6名伤害排行
- 显示每个玩家的总伤害值
- 支持多BOSS独立统计

### 4. 金钱奖励
- 击打BOSS获得金钱奖励
- 自动更新玩家金钱显示
- 可自定义奖励金额

### 5. 音效反馈
- 玩家击打BOSS时播放音效
- 文件: `sounds\jida.vsnd`

## 调试方法

### 1. 查看控制台输出

```
[ZERO] 已加载 3 个BOSS配置到内存
[ZERO] 已更新BOSS配置: 123456
```

### 2. 游戏内显示

#### BOSS血条显示
```
末影龙: 8500 / 15000 [56%]
凋零: 3200
```

#### 个人伤害信息
```
    BOSS:末影龙 (-250)
命中:15次|用时:12秒|秒伤:125
```

#### 伤害排行榜
```
-----|末影龙|-----
 [1250x] Player1
 [890x] Player2
 [650x] Player3
```

### 3. 常见问题解决

#### 配置不生效
```json
// ❌ 错误格式
{
  "BossConfigs": {
    "12345": { ... }
  }
}

// ✅ 正确格式
{
  "12345": {
    "Name": "BOSS名称"
  }
}
```

#### 血量显示异常
```json
// 检查MAXHP设置
{
  "实体ID": {
    "MAXHP": 10000,  // 确保大于实际血量
    "BOSSbar": true
  }
}
```

### 4. 调试命令

```bash
# 重启地图加载配置
map your_map_name

# 查看实体信息
ent_info entity_name

# 启用详细日志
sv_cheats 1
developer 1
```

### 5. 自动配置生成

首次运行时系统会自动生成模板:
```json
{
  "BOSS的id": {
    "Name": "BOSS姓名",
    "BOSSbar": false,
    "BossEnd": false,
    "MAXHP": 0,
    "BoolMONEY": false,
    "BMONEY": 0
  }
}
```

## 最佳实践

### 1. 配置建议

| BOSS类型 | 配置建议 |
|----------|----------|
| 主要BOSS | `BOSSbar:true`, `BossEnd:true`, 自定义血量 |
| 次要BOSS | `BOSSbar:true`, `BossEnd:false` |
| 小怪BOSS | `BOSSbar:false`, `BossEnd:false` |

### 2. 性能优化
- 合理设置BOSS血量上限
- 避免过多同时激活的BOSS
- 及时清理无效配置项

### 3. 平衡性调整
- 根据地图难度调整金钱奖励
- 控制排行榜显示避免刷屏
- 适当设置血量上限避免过长战斗

---
*配置文件会在BOSS首次被攻击时自动创建，你可以根据需要调整各项参数来获得最佳游戏体验。*