`🩸 a small tool to help categorize your dayz server types`

## 🚀 Usage

- Download the latest binary executable from the [releases](https://github.com/agorushkin/DayZ-Types-Categorization/releases).
- When running the executable, pass the path to the `types.xml` folder of the mission you wish to categorize.
- The executable will create a new folder called `output` which will contain the separated type files, `types.xml` replacement, and an extract from `cfgeconomycore.xml` with the new fields.

## 📦 Installation

- Copy the `types` folder generated inside `output` and insert it into a corresponding mission's `db` folder. (If you wish to change that, look into the extract of cfgeconomycore.xml).
- Copy the extract of `cfgeconomycore.xml` within the `<economycore>` tags and paste it inside `cfgeconomycore.xml`. (The `<ce>` tag's `folder` field corresponds to where the `types` folder should be located).
- Replace the `types.xml` folder in the `db` folder with the one generated inside `output`.

## 📝 Notes

- If any of the values shown in base `types.xml` are missing from the `categories.json`, the script will notify you after the completion and output the missing values in `output/unused.xml`.

### 📜 Editing the `categories.json`

- In `categories.json`, a field inside the base of the object stands for the group. The name is written as follows `[t = types | e = events]-[name]`.
  It's important to get the types right, as if for example the `infected` are given the spawn type of `types` it will not work.

- The value of the field should be a string array. An array should contain the Id names of the items that should be in that group.
  If the string begins with `#`, it means it's a comment, and when generating the type files, it will be written in the file as a comment to help distinguish between groups.

- The `categories.json` file is read from the `./` folder, so it is important to keep in mind that the binary is located in the same folder as the `categories.json` file.