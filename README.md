# Moqi Rime (墨奇音形)

A sophisticated Rime input method configuration for the **Moqi (墨奇)** schema.

This project is a fork of [gaboolic/rime-shuangpin-fuzhuma](https://github.com/gaboolic/rime-shuangpin-fuzhuma).

墨奇音形支持自然码、小鹤、搜狗、微软双拼。它基于字形描述信息递归拆分，最后取首末双形音托；拆分码表已覆盖通用规范汉字、常用繁体字，并支持 GB18030-2022。方案支持用 Ctrl+P 切换墨奇辅助码/首末字形显示，用 Ctrl+L 切换墨奇拆字显示。

## Features

- **Primary Schema**: Moqi (墨奇), combining **Xiaohe Shuangpin (小鹤双拼)** with **Moqi Auxiliary Codes (墨奇辅助码)**.
- **Engine**: Powered by the **Wanxiang (万象)** engine for superior sentence-level prediction and grammar.
- **Extensible**: Includes numerous Lua-based features:
  - Date and time translators.
  - On-the-fly calculator (trigger with `V`).
  - Unicode and character decomposition hints.
  - "Super comments" for learning auxiliary codes.
- **Rich Vocabulary**: Integrated with multiple dictionary sources, optimized for performance by removing unreferenced and redundant files.
- **Customizable**: Supports various keybindings (including Colemak) and deep customization via Rime's YAML patch system.

## Project Structure

- `moqi_wan_flypymo.schema.yaml`: Main schema entry point.
- `moqi.yaml`: Shared configuration for engines, switches, and filters.
- `lua/`: Custom functional extensions.
- `cn_dicts/`: Organized dictionary files.
- `opencc/`: Conversion and decomposition data.

## Usage

1. Copy the configuration files to your Rime user directory.
2. Select the "墨奇+小鹤双拼·墨奇" schema.
3. Deploy or re-deploy your Rime installation.

## Recent Changes

- Optimized repository size by removing unreferenced dictionary files and unused configuration templates.
- Added comprehensive project documentation.

## Upstream project and installation

- 原始项目：[gaboolic/rime-shuangpin-fuzhuma](https://github.com/gaboolic/rime-shuangpin-fuzhuma)，词库使用[白霜词库](https://github.com/gaboolic/rime-frost)，支持多种双拼与墨奇码、自然码部首辅、小鹤音形等辅助码。
- 配置参考：[小鹤双拼+自然快手/小鹤双形辅助码](https://github.com/functoreality/rime-flypy-zrmfast)、[魔改自然碼 Rime 方案](https://github.com/ksqsf/rime-moran)。
- 推荐方案：`moqi_wan_flypymo.schema.yaml`；追求 4 码自动上屏时可选 `moqi_single_xh`。
- 默认关闭用户词库以保持词频稳定；需要时在所用 schema 中设置 `enable_user_dict: true`，并编辑 `cn_dicts_common/user.dict.yaml`。
- 支持 Windows、macOS、Linux、Android 和 iOS 的 Rime 前端；复制配置文件后重新部署即可。

### FAQ

更多配置及功能请看：[FAQ.md](md/FAQ.md)

### 输入效果

- 整句输入插入字辅：

![醉洛阳](readmeimg/qimhzly.png)

- 打词时插入辅助码：

![寄宿](readmeimg/jisub.png)

![极速](readmeimg/jimsu.png)

- 整句句中任意辅助码，按`开启
![句中任意辅助码](readmeimg/input-juzhongfuzhuma.gif)

- 整句输入时增强单字性能，增加syffo或者syff/ 5码上屏单字的功能
![zssr](readmeimg/zssr.png)

- 不认识的字可以笔画输入 `ab`引导 hspnz横竖撇捺折

![笔画](readmeimg/bihua.png)

- 也可以部件组字输入 `az`引导

![部件](readmeimg/bujian.png)

![部件](readmeimg/bujian2.png)

- 也可以输入仓颉码 `acj`引导

![仓颉](readmeimg/cangjie5.png)

- 通过opencc支持繁简转换、火星文、首末拆分字形(墨奇音形)

![繁体](readmeimg/fantizi.png)

![火星文](readmeimg/huoxingwen.png)

![拆分](readmeimg/shoumo-chai.png)

![全拆](readmeimg/quanchai.png)

- 超级简拼：1码、2码、3码时，按下Tab（或者是/，或者是。都可以）自动上屏1字、2字词、3字词，不和空格上屏的单字冲突
![等-蛋糕](readmeimg/dg-蛋糕.png)

墨奇音形的方案支持ctrl+p开关显示墨奇辅助码+首末字形,ctrl+l开关显示墨奇拆字的拆分

- 日期时间相关输入：`date time week` `datetime` `timestamp`

  ![datetime](readmeimg/datetime.png)

- 快捷日期输入：N开头

  - ![Nmoshi](readmeimg/Nmoshi.png)

- 符号输入`/fh`，更多符号查看`symbols_caps_v.yaml`

  - ![fh](readmeimg/fh.png)

- 大写数字：`R开头`
  ![R123456](readmeimg/R123456.png)

- 直接输入unicode：U开头
  ![u2ffb](readmeimg/u2ffb.png)

- 计算器功能(V模式) 感谢[ChaosAlphard](https://github.com/ChaosAlphard)的[pr](https://github.com/gaboolic/rime-shuangpin-fuzhuma/pull/41)
  ![alt text](readmeimg/v_jsq.png)

  - [计算器功能介绍](md/calc.md)
  - ![1](md/assets/1.png)
  
- 英文输入：aw开头

  - ![aw](readmeimg/aw.png)

- 日文输入：aj开头

  - ![aj](readmeimg/aj.png)

- 翻译功能：ctrl + E开启英汉、汉英互译。
  
  - ![ink](readmeimg/ink.png)
  - ![奇特](readmeimg/qite.png)

- O符快符：o开头，快速输入各种符号偏旁部件，可以参考[快符](md/fuhao.md)      [部件](md/bujian.md)

  - ![ofu2](readmeimg/ofu2.png)
  - ![ofu](readmeimg/ofu.png)

- 分号符：

  - 因为实现分号符后，分号无法自动上屏，如果希望能使用分号符，可以进行以下操作 [分号符](md/fenhaofu.md)

### 飞键 模糊音相关

```
# `你使用的方案.shema.yaml` 里飞键 可选择性开启
- derive/^([yh])j/$1q/    # yj hj就可以打yq hq
- derive/^qx/qw/  # qx就可以打qw
模糊音同理，也是使用derive把平舌音翘舌音互转、前后鼻音互转，详见issue中的faq
```

### 并击相关

- [并击原理](https://github.com/gaboolic/rime-shuangpin-fuzhuma/wiki/%E5%B9%B6%E5%87%BB%E5%8E%9F%E7%90%86)

### todo

```

4字成语的码表优化 补全

墨奇音形自然码下 e简码问题修复

墨奇音形自动上屏版，4码为词，4码+/自动上屏单字，a-z顶词

出简让全的开关、tab提示的开关

字典功能，反查时生僻字显示读音和释义

```

### 鸣谢

雾凇拼音 <https://github.com/iDvel/rime-ice> 参考了其中很多配置

白霜词库 <https://github.com/gaboolic/rime-frost> 本项目使用的词库和词频来自白霜词库

墨奇码码表 <https://github.com/gaboolic/moqima-tables> 墨奇音形的拆分

小鹤双拼+辅助码 <https://gitee.com/functoreality/rime-flypy-zrmfast>

魔然（自然码双拼辅助码）：<https://github.com/ksqsf/rime-moran>

细胞词库&各个发行版配置 <https://github.com/Bambooin/rimerc>

az部件组字模式使用的词典 <https://github.com/mirtlecn/rime-radical-pinyin>

声笔输入法 <https://github.com/sbsrf/sbsrf> 使用了其中的lua脚本，参考了tab上屏简拼功能

星空键道：<https://github.com/xkinput/Rime_JD>

英汉/汉英字典 <https://github.com/lxs602/Chinese-Mandarin-Dictionaries>

墨奇本猫：

<img src="readmeimg/moqi1.jpg" width=30%>

<img src="readmeimg/moqi2.jpg" width=30%>

## Star History

[![Star History Chart](https://star-history.dera.page/svg?repos=gaboolic/rime-shuangpin-fuzhuma&type=Date)](https://star-history.dera.page/#gaboolic/rime-shuangpin-fuzhuma&Date)
