# ZeRo_MapCvar 武器CVAR配置指南

## 武器CVAR详细分类

### SMG类武器配置

| 武器 | Count | Bool | Money | Clip | Damage |
|------|-------|------|-------|------|--------|
| **Bizon** | `Bizon_Count` | `Bizon_Bool` | `Bizon_Money` | `Bizon_Clip` | `Bizon_Damage` |
| **Mac10** | `Mac10_Count` | `Mac10_Bool` | `Mac10_Money` | `Mac10_Clip` | `Mac10_Damage` |
| **Mp5** | `Mp5_Count` | `Mp5_Bool` | `Mp5_Money` | `Mp5_Clip` | `Mp5_Damage` |
| **Mp7** | `Mp7_Count` | `Mp7_Bool` | `Mp7_Money` | `Mp7_Clip` | `Mp7_Damage` |
| **Mp9** | `Mp9_Count` | `Mp9_Bool` | `Mp9_Money` | `Mp9_Clip` | `Mp9_Damage` |
| **P90** | `P90_Count` | `P90_Bool` | `P90_Money` | `P90_Clip` | `P90_Damage` |
| **Ump45** | `Ump45_Count` | `Ump45_Bool` | `Ump45_Money` | `Ump45_Clip` | `Ump45_Damage` |

### 步枪类武器配置

| 武器 | Count | Bool | Money | Clip | Damage |
|------|-------|------|-------|------|--------|
| **Ak47** | `Ak47_Count` | `Ak47_Bool` | `Ak47_Money` | `Ak47_Clip` | `Ak47_Damage` |
| **Aug** | `Aug_Count` | `Aug_Bool` | `Aug_Money` | `Aug_Clip` | `Aug_Damage` |
| **Famas** | `Famas_Count` | `Famas_Bool` | `Famas_Money` | `Famas_Clip` | `Famas_Damage` |
| **Galilar** | `Galilar_Count` | `Galilar_Bool` | `Galilar_Money` | `Galilar_Clip` | `Galilar_Damage` |
| **M4a4** | `M4a4_Count` | `M4a4_Bool` | `M4a4_Money` | `M4a4_Clip` | `M4a4_Damage` |
| **M4a4S** | `M4a4S_Count` | `M4a4S_Bool` | `M4a4S_Money` | `M4a4S_Clip` | `M4a4S_Damage` |
| **Sg553** | `Sg553_Count` | `Sg553_Bool` | `Sg553_Money` | `Sg553_Clip` | `Sg553_Damage` |

### 狙击枪类武器配置

| 武器 | Count | Bool | Money | Clip | Damage |
|------|-------|------|-------|------|--------|
| **Awp** | `Awp_Count` | `Awp_Bool` | `Awp_Money` | `Awp_Clip` | `Awp_Damage` |
| **Scar20** | `Scar20_Count` | `Scar20_Bool` | `Scar20_Money` | `Scar20_Clip` | `Scar20_Damage` |
| **G3sg1** | `G3sg1_Count` | `G3sg1_Bool` | `G3sg1_Money` | `G3sg1_Clip` | `G3sg1_Damage` |
| **Ssg08** | `Ssg08_Count` | `Ssg08_Bool` | `Ssg08_Money` | `Ssg08_Clip` | `Ssg08_Damage` |

### 霰弹枪类武器配置

| 武器 | Count | Bool | Money | Clip | Damage |
|------|-------|------|-------|------|--------|
| **Mag7** | `Mag7_Count` | `Mag7_Bool` | `Mag7_Money` | `Mag7_Clip` | `Mag7_Damage` |
| **Nova** | `Nova_Count` | `Nova_Bool` | `Nova_Money` | `Nova_Clip` | `Nova_Damage` |
| **Sawedoff** | `Sawedoff_Count` | `Sawedoff_Bool` | `Sawedoff_Money` | `Sawedoff_Clip` | `Sawedoff_Damage` |
| **Xm1014** | `Xm1014_Count` | `Xm1014_Bool` | `Xm1014_Money` | `Xm1014_Clip` | `Xm1014_Damage` |

### 机枪类武器配置

| 武器 | Count | Bool | Money | Clip | Damage |
|------|-------|------|-------|------|--------|
| **M249** | `M249_Count` | `M249_Bool` | `M249_Money` | `M249_Clip` | `M249_Damage` |
| **Negev** | `Negev_Count` | `Negev_Bool` | `Negev_Money` | `Negev_Clip` | `Negev_Damage` |

### 手枪类武器配置

| 武器 | Count | Bool | Money | Clip | Damage |
|------|-------|------|-------|------|--------|
| **Deagle** | `Deagle_Count` | `Deagle_Bool` | `Deagle_Money` | `Deagle_Clip` | `Deagle_Damage` |
| **Elite** | `Elite_Count` | `Elite_Bool` | `Elite_Money` | `Elite_Clip` | `Elite_Damage` |
| **Fiveseven** | `Fiveseven_Count` | `Fiveseven_Bool` | `Fiveseven_Money` | `Fiveseven_Clip` | `Fiveseven_Damage` |
| **Glock18** | `Glock18_Count` | `Glock18_Bool` | `Glock18_Money` | `Glock18_Clip` | `Glock18_Damage` |
| **P2000** | `P2000_Count` | `P2000_Bool` | `P2000_Money` | `P2000_Clip` | `P2000_Damage` |
| **P250** | `P250_Count` | `P250_Bool` | `P250_Money` | `P250_Clip` | `P250_Damage` |
| **Tec9** | `Tec9_Count` | `Tec9_Bool` | `Tec9_Money` | `Tec9_Clip` | `Tec9_Damage` |
| **Usp9** | `Usp9_Count` | `Usp9_Bool` | `Usp9_Money` | `Usp9_Clip` | `Usp9_Damage` |
| **Cs75a** | `Cs75a_Count` | `Cs75a_Bool` | `Cs75a_Money` | `Cs75a_Clip` | `Cs75a_Damage` |

### 无Damage/Clip配置的武器

| 武器类型 | 配置参数 | 说明 |
|----------|----------|------|
| **R8 Revolver** | `R8_Clip`, `R8_Damage` | 仅Clip和Damage |
| **防弹衣** | `Vest_Count`, `Vest_Bool`, `Vest_Money` | 无Clip和Damage |

### 投掷物配置

| 投掷物 | Count | Bool | Money | 说明 |
|--------|-------|------|-------|------|
| **高爆手雷** | `He_Count` | `He_Bool` | `He_Money` | 无Clip和Damage |
| **燃烧弹** | `Fire_Count` | `Fire_Bool` | `Fire_Money` | 无Clip和Damage |
| **闪光弹** | `Flash_Count` | `Flash_Bool` | `Flash_Money` | 无Clip和Damage |
| **破片手雷** | `Frag_Count` | `Frag_Bool` | `Frag_Money` | 无Clip和Damage |
| **烟雾弹** | `Smoke_Count` | `Smoke_Bool` | `Smoke_Money` | 无Clip和Damage |
| **医疗针** | `Xz_Count` | `Xz_Bool` | `Xz_Money` | 无Clip和Damage |

### 特殊武器配置

| 武器 | 可配置参数 | 不支持配置 |
|------|------------|------------|
| **R8 Revolver** | `R8_Clip`, `R8_Damage` | Count, Bool, Money |
| **所有投掷物** | Count, Bool, Money | Clip, Damage |
| **防弹衣** | Count, Bool, Money | Clip, Damage |

### 配置示例

#### 完整SMG配置示例
```cfg
Bizon_Count 2
Bizon_Bool true
Bizon_Money 1400
Bizon_Clip 80
Bizon_Damage 26

Mac10_Count 0
Mac10_Bool true
Mac10_Money 1050
Mac10_Clip 60
Mac10_Damage 28
```

#### 特殊武器配置示例
```cfg
// R8 Revolver (仅支持Clip和Damage)
R8_Clip 1
R8_Damage 1

// 高爆手雷 (无Clip和Damage)
He_Count 3
He_Bool true
He_Money 3000

// 防弹衣 (无Clip和Damage)
Vest_Count 0
Vest_Bool true
Vest_Money 1000
```

#### 投掷物完整配置示例
```cfg
He_Count 50      // 高爆手雷
He_Bool true
He_Money 3000

Fire_Count 10    // 燃烧弹
Fire_Bool true
Fire_Money 5000

Flash_Count 0    // 闪光弹
Flash_Bool false
Flash_Money 5000

Frag_Count 5     // 破片手雷
Frag_Bool true
Frag_Money 1400

Smoke_Count 5    // 烟雾弹
Smoke_Bool true
Smoke_Money 1400

Xz_Count 10      // 医疗针
Xz_Bool true
Xz_Money 1000
```