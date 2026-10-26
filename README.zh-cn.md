# demo 示范语音包

简体中文 | [English](README.md)

VIR Signals 编辑器扩展的双事件示范语音包——也是你复制去做自己包的模板。

## 这个包是什么

只映射两个槽位：`error`（报错行触发；这个共享槽位同时覆盖 errorAtPosition、noInlayHints、terminalCommandFailed 三个事件）和 `save`（手动保存触发）。其余一切保留编辑器原声——这是故意的：**包只替换它映射的，没映射的槽位留官方原声**。`sourceLicense` 如实填 `third-party-cc0`，因为音频来自 Kenney；来源声明随包携带在 `SOURCE.txt`。

## 听它

1. 安装 VIR Signals 扩展。
2. 运行 **VIR: 打开语音包文件夹**，把本仓库的 `pack/` 文件夹放进去（或把本仓库直接克隆进包文件夹）。
3. 运行 **VIR: 选择语音包**，选 *Demo save+err*，替换。
4. 触发一行报错、再手动保存——两个声音都出自这个包。

## 改造成你自己的包（核心节）

1. **复制本仓库。** 包本体在 `pack/` 目录——那个目录就是包，其余都是文档。
2. **改 `id`**（`pack/manifest.json`）：你的包名，全小写短横线，全宇宙唯一（`my-cool-pack`）。
3. **改 `name` / `version` / `author`**——`name` 显示在选包器里，宜短（14 字符内放得进状态栏）。
4. **换音频**：把 `pack/sounds/` 换成你的 WAV/MP3。限制：单条 ≤20MB，建议 ≤2 秒（progress 类 ≤1 秒）。文件名用全小写，manifest 里写的路径与实际文件名**大小写逐字符一致**——Linux 上大小写对不上会直接找不到文件。
5. **改 `slots` 映射**：键=槽位名。全部 28 个槽位：error、warning、break、quickFixes、taskCompleted、taskFailed、voiceRecordingStarted、voiceRecordingStopped、save、format、clear、progress、foldedAreas、confetti、terminalBell、terminalCommandSucceeded、diffLineInserted、diffLineModified、diffLineDeleted、chatEditModifiedFile、chatUserActionRequired、codeActionTriggered、codeActionApplied、editsKept、editsUndone、nextEditSuggestion、requestSent、responseReceived（末位还接受编号子键 responseReceived1–4）。`error` 这类共享槽位会同时换掉它名下全部事件的声音。没映射的槽位保留原声——两个槽位就是一个完整的包。
6. **如实填 `license` 与 `sourceLicense`。** `sourceLicense` 声明音频从哪来：`original`（自己做的）、`game-asset`、`third-party-cc0`、`unknown` 四选一；来源要求署名时加一份 `SOURCE.txt`。

## 发布

把你自己的包仓库 push 到你的 GitHub，复制想发布的**完整 40 位** commit SHA，按 registry 仓的 CONTRIBUTING 投稿——一条 JSON 条目指向你的仓库、锁死那个 SHA。

## 素材来源

两条音频来自 **Kenney Interface Sounds**（作者 Kenney Vleugels，kenney.nl），以 **CC0 1.0** 发布。CC0 不要求署名，但本包照样如实携带声明——见 `pack/SOURCE.txt`。
