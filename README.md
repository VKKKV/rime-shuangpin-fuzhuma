# Moqi Rime (墨奇音形)

A sophisticated Rime input method configuration for the **Moqi (墨奇)** schema.

This project is a fork of [gaboolic/rime-shuangpin-fuzhuma](https://github.com/gaboolic/rime-shuangpin-fuzhuma).

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
