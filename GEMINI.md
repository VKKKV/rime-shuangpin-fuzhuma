# Moqi Rime Input Method (墨奇音形)

This project is a highly customized Rime input method configuration for the **Moqi (墨奇)** schema. It is designed for efficient Chinese input using **Xiaohe Shuangpin (小鹤双拼)** combined with **Moqi Auxiliary Codes (墨奇辅助码)**.

## Project Overview

- **Core Schema**: Moqi (墨奇), which uses a combination of Shuangpin (double pinyin) and auxiliary codes (fuzhuma) for precise character selection.
- **Engine**: Primarily utilizes the **Wanxiang (万象)** engine/model (`wanxiang-lts-zh-hans.gram`) for improved sentence-level prediction and grammar.
- **Language**: Rime Configuration (YAML) and Lua.
- **Main Features**:
  - Support for Xiaohe Shuangpin + Moqi aux codes.
  - Multi-variant support (e.g., Colemak keybinding variant).
  - Extensive Lua-based extensions: date/time translators, calculators, Unicode input, emoji filters, and "super comments" for learning aux codes.
  - Character decomposition (chaifen) hints via OpenCC.
  - Large vocabulary support with split dictionary files (base, common, specialized).
  - Simplified/Traditional conversion and "Mars" (martian) text support.

## Project Structure

- **`*.schema.yaml`**: Entry points for different input schemes (e.g., `moqi_wan_flypymo.schema.yaml`).
- **`moqi.yaml`**: The foundational configuration shared across Moqi schemas (engines, switches, filters, etc.).
- **`moqi_speller.yaml`**: Defines spelling rules, including Xiaohe Shuangpin and auxiliary code mappings.
- **`default.yaml`**: Global Rime settings (switcher, key bindings, page size).
- **`lua/`**: Contains all Lua extensions.
  - `pro_comment_format.lua`: Handles "super comments" for aux code hints.
  - `date_translator.lua`, `calculator.lua`, etc.: Functional translators.
  - `sbxlm/`: Sub-directory for complex logic (key bindings, editors).
- **`cn_dicts/`, `cn_dicts_common/`, `cn_dicts_cell/`**: Dictionary files organized by frequency and category.
- **`opencc/`**: Configuration for OpenCC-based conversions (S2T, Emoji, Chaifen).
- **`program/release/`**: Python scripts for generating or preparing schema releases.
- **`recipes/`**: Plum recipes for installing/updating specific components.

## Development & Maintenance

### Building and Updating
This project appears to use Python scripts for generating some of the schema files.
- **Command**: `python3 program/release/generate_moqi_wan_schema.py` (Inferred from file list).
- **Rime Deployment**: Standard Rime deployment process (usually "Deploy" or "Re-deploy" in the Rime menu) is required after changing YAML or Lua files.

### Key Conventions
- **Modularity**: Extensive use of `__include` and `__patch` to keep configurations DRY (Don't Repeat Yourself). Most core logic is in `moqi.yaml`.
- **Lua Integration**: Many features are implemented via `lua_translator`, `lua_filter`, and `lua_processor`. Always check the `lua/` directory when investigating behavioral logic.
- **Dictionary Management**: `moqi_wan.extended.dict.yaml` is the main entry for dictionaries, importing various sub-dictionaries from the `cn_dicts*` folders.

### Testing
Testing is typically performed by deploying the schema to a Rime installation and verifying input behavior, especially:
- Correct Shuangpin mapping.
- Auxiliary code filtering and hints.
- Lua translator triggers (e.g., typing `date` or `V1+1`).
- Switch functionality (Simplified/Traditional, Emoji, etc.).
