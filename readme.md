<h1 align="center"> 自然龙 Rime 输入方案 </h1>

<p align="center">
<a href="https://qm.qq.com/q/yj4E0tBrOg"><img src="https://img.shields.io/badge/%E7%82%B9%E5%87%BB%E5%8A%A0%E5%85%A5%E7%BE%A4%E8%81%8A-%E9%BE%99%E7%A0%81%E9%9F%B3%E5%BD%A2-blue?logo=qq"/></a>
<a href="https://my-rime.vercel.app/?plum=Elflare/rime-zrlong:zrlong,zrlong_sentence"><img src="https://img.shields.io/badge/%E7%BA%BF%E4%B8%8A%E8%AF%95%E7%94%A8-black?logo=rime"/></a>
<!-- <a href="https://github.com/Elflare/rime-zrlong"><img src="https://img.shields.io/badge/GitHub-%E9%93%BE%E6%8E%A5-blue?logo=github"/></a> -->
</p>

---

**免责声明**：本仓库为自用分享，可能存在诸多不足和错误。如果您选择使用此仓库，请自行承担可能产生的风险和责任。感谢您的理解和支持！

---

## 目录

- [简介](#简介)
- [安装](#安装)
  - [使用 `Git` 安装](#使用-git-安装)
  - [手动安装](#手动安装)
- [用法](#用法)
  - [键位图](#键位图)
  - [辅助码字根图](#辅助码字根图)
  - [编码方式](#编码方式)
    - [单字编码](#单字编码)
    - [词编码](#词编码)
  - [实用功能](#实用功能)
    - [自定义短语](#自定义短语)
    - [反查](#反查)
    - [手动造词](#手动造词)
    - [工具](#工具)
  - [飞键](#飞键)
- [性能测评](#性能测评)
- [鸣谢](#鸣谢)

## 简介

**自然龙** 是一种在传统双拼基础上进行创新的输入法，它**使韵母带调**，采用**四码定长**的方式进行输入。

- **韵调统一**：传统双拼往往不区分声调，导致编码信息利用率低下，离散弱，重码多；传统带调输入方案往往又码长太长。自然龙将**韵母带上声调**并统一在**一个**键上，高效利用编码空间，单字能力和词组能力均大幅提高。
- **静态码表**：使用静态码表，确定性 100%，所有字词尽在掌握，可随意盲打，安全感拉满。
- **四码定长**：单字和词组最大码长为 4，打 2 字词**声韵声韵**有节奏感，输入体验舒适。
- **双拼加形**：结合了双拼的高效率和形码的高准确性，形码部分采用自然码的辅助码，首码**义部优先，次码取大**，直观自然。
- **手感优化**: 韵母分布利用程序算法 + 人工设计，**重码率**和**手感**皆超过传统音形、形码输入法。
- **字词库大**: 目前已包含 **4.5 万 +** 单字和 **16 万 +** 词组。

以下是传统双拼常见的重码词组，自然龙可以**全部离散**：
| 重码词组 | 自然龙编码 |
| ---------------------------- | ---------------------------- |
| 哪里、那里 | nmlg、nilg |
| 不对、部队 | bldf、bhdf |
| 同时、同事 | tjub、tjut |
| 教室、教师 | jlut、jluj |
| 使用、试用、实用 | ugyy、utyy、ubyy |
| 事件、时间、实践、世间 | utja、ubjr、ubja、utjr |
| 事实、试试、实时、实事 | utub、utut、ubub、ubut |
| 消失、消逝、小事、小时 | xmuj、xmut、xlut、xlub |
| 物理、屋里、无力、武力 | whlg、walg、wllt、wmlt |
| 知识、只是、智识、指使、芝士 | vjub、vgut、vtub、vgug、vjut |

**欢迎线上试用体验**：[自然龙线上试用](https://my-rime.vercel.app/?plum=Elflare/rime-zrlong:zrlong,zrlong_sentence)。更多性能测评详见[性能测评](#性能测评)

> 本仓库基于 Rime 平台。

---

**NEW**:

- 2024 年 4 月 25 日增加了整句模式，和普通双拼打法一样，不再赘述。(Thanks to [冰雪拼音](https://github.com/hanzi-chai/rime-snow-pinyin))
    - 若想用万象词库，可以移步 [万象拼音](https://github.com/amzxyz/rime_wanxiang)
- 2024 年 5 月 13 日新增带辅的整句模式。由于内容太多，未合并至本仓库，详情见 [魔龙](https://github.com/jack2game/rime-molong)。
- 2025 年 1 月 19 日新增字词动态模式。1 - 3 码静态，4 码所有字词动态调频，包括自造词。若想固定某个字词，有两种方式：
    1. 在 `zrlong_custom_phrases.txt` 中添加，以自定义短语方式固定。
    2. 在 `zrlong_fixed.dict.yaml` 中添加，以码表方式固定。

## 安装

**注意**：

- 首先确保已经装了 [Rime](https://rime.im/)
- 若已有 Rime 的配置文件，请先备份

### 使用 `Git` 安装

> 如果您还没有安装 Git，需要先下载并安装 [Git](https://git-scm.com/)，或使用[手动安装](#手动安装)。

1. **打开命令行工具**

2. **克隆仓库**：
   - 使用 `git clone` 命令克隆仓库。如果您已经安装了 Git，可以直接执行以下命令：
     ```bash
     git clone --depth=1 https://github.com/Elflare/rime-zrlong.git "您的 Rime 用户目录"
     ```

### 手动安装

1. **下载Release文件**：

   - 点击[Releases](https://github.com/rimeinn/rime-zrlong/releases)。
   - 在最新的 Release 条目中，找到压缩包点击下载（例如：zrlong_v<版本号>.zip）

2. **将下载的文件解压到rime目录**：

   - 打开文件资源管理器。
   - 在您下载文件夹中找到下载的 ZIP 文件。
   - 将**里面的所有文件，包含文件夹**解压到`您的 Rime 用户目录`（若不知道，可右键电脑状态栏右下角的 Rime 图标，选择 `用户文件夹`）。

## 用法

### 键位图

![键位图片](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/jianwei.jpg)

### 辅助码字根图

![辅助码字根](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/fuzhuma.jpg)

> This picture is from [℞ 魔然](https://github.com/rimeinn/rime-moran)

> 部首主要参考自 [汉典](https://www.zdic.net/) 和 [百度百科](https://baike.baidu.com/)

### 编码方式

#### 单字编码

| 单字编码      | 演示编码         |                                                 演示图片                                                  |
| ------------- | ---------------- | :-------------------------------------------------------------------------------------------------------: |
| 声            | d                |  ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/refs/heads/main/zrlong/sample/d.jpg)   |
| 声韵          | di               |  ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/refs/heads/main/zrlong/sample/di.jpg)  |
| 零声母一简    | a                |  ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/refs/heads/main/zrlong/sample/a.jpg)   |
| 零声母 + 韵母 | ao (aì 在 o 上)  |  ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/refs/heads/main/zrlong/sample/ao.jpg)  |
| 零声母 + 韵母 | aw (áng 在 w 上) |  ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/refs/heads/main/zrlong/sample/aw.jpg)  |
| 声韵辅        | usu              | ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/refs/heads/main/zrlong/sample/usu.jpg)  |
| 声韵辅辅      | ytdy             | ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/refs/heads/main/zrlong/sample/ytdy.jpg) |

#### 词编码

> 数字代表第几个字（`0` 代表最后一个字），`S` 代表声母，`Y` 代表韵母

| 多字编码     | 编码方式      | 演示编码 |                                            演示图片                                            |
| ------------ | ------------- | -------- | :--------------------------------------------------------------------------------------------: |
| 2 字词       | `S1 Y1 S2 Y2` | jidf     | ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/jidf.jpg) |
| 3 字词       | `S1 S2 S3 Y3` | jsjj     | ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/jsjj.jpg) |
| 4 字及以上词 | `S1 S2 S3 S0` | bnmz     | ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/bnmz.jpg) |

### 实用功能

#### 自定义短语

在 `zrlong_custom_phrases.txt` 中配置，具体请参考该文件中的说明。

#### 反查

自然龙具有四种反查方式：

- 通配符反查：用自然码双拼反查，其中 `SYF` 分别代表：声母、韵母和辅码
- 虎码反查：用 \` 引导，`X` 代表任意字母，`+` 代表需要一个或多个字母
- 笔画反查：用 `obh` 引导，`hpszd` 分别代表横撇竖折点，`+` 代表需要一个或多个字母
- 两分反查：用 `olf` 引导，自然码双拼编码，`+` 代表需要一个或多个字母
  > 在反查时，上述前缀会被隐藏，以避免干扰。

|  反查方式  |       规则       | 演示编码 |                                             演示图片                                              |
| :--------: | :--------------: | :------: | :-----------------------------------------------------------------------------------------------: |
| 通配符反查 |      SY\`F       |   ka\`   |  ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/kj%60.jpg)  |
| 通配符反查 |      SYF\`       |  iik\`   | ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/iik%60.jpg)  |
|  虎码反查  |       \`X+       |   \`j    |  ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/%60j.jpg)   |
|  笔画反查  |   obh[hpszd]+    |  obhhs   |  ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/obhhs.jpg)  |
|  两分反查  | olf[自然码编码]+ | olfhoho  | ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/olfhoho.jpg) |

#### 手动造词

自然龙具有两种手动造词方法：

| 造词方式                     | 演示编码     |                                              演示图片                                               |
| ---------------------------- | ------------ | :-------------------------------------------------------------------------------------------------: |
| `'` 开头（前缀会被隐藏）     | `'ztp'rp'lj` | ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/zrl_zaoci.jpg) |
| 打出一个字，上屏之前再按 `'` | `ztp'rp'lj`  | ![示例图片](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/zrl_zaoci.jpg) |

> 造的词排在默认编码之后。存储在 `zrlong.txt` 中。

#### 工具

- **时间**：直接打 `sj`
- **日期**：`orq`
- **时间和日期**：`ors`
- **中文数字小写转大写**：`S` 开头，后面接数字，如 `S123`，则变为：一百二十三
- **Emoji**：`Ctrl + e` 切换 Emoji 表情滤镜，在 `zrlong.schema.yaml` 中的 `key_binder` 处配置
- **分号次选**：在 `zrlong.schema.yaml` 中的 `key_binder` 处配置
- **英文输入**：
  - 默认没开启空码自动清屏，所以空码时可直接输入英文
  - 首字母大写，用回车上屏自动转为小写：如 `Zrlong`，按回车后变为 `zrlong`
  - 首字母大写，用空格上屏则不变：如 `Zrlong`，按空格则为 `Zrlong`
- **简码提示**：可显示字或词的简码：
  ![简码提示](https://raw.githubusercontent.com/Elflare/images-repo/main/zrlong/sample/jianmatishi.jpg)
- **二简词补全**：将 `自然龙二简补全.txt` 中的内容复制到 `zrlong.dict.yaml` 中（thanks to 西金石）
- **辅码部首**：用 `ob` 引导，如 `obc` ，则出现 `艹` 等部首（thanks to 西金石）
- **出简让全**：默认是出简让全，若想出简不出全，可以在 `zrlong.schema.yaml` 中，注释掉 `table_translator@zrlong_full`

### 飞键

- 仅将声母 y 飞到了 e，原因是 e 的英文发音和 y 的拼音很像。韵母不受影响。
- 飞键的权重更低，不影响正常编码。

## 性能测评

- **单字**：自然龙单字 2 码 1500 常用字覆盖 500 多个（双拼是 300 ），2 码一共约 600 个键位。单字前 3000 字 1 个重（颂，取了特取码后 0 重）。
- **词组**：自然龙词重 10000 多个（五笔词重 13000 左右，传统双拼 18000 左右）。

**单字测评**：

![字测评](https://raw.githubusercontent.com/Elflare/images-repo/refs/heads/main/zrlong/bench/zi.jpg)

**词组测评**：

![词测评](https://raw.githubusercontent.com/Elflare/images-repo/refs/heads/main/zrlong/bench/ci.jpg)

## 鸣谢

原作者: [晡时之光](https://hanxinma.gitlab.io/longma/zrl)

- Rime 项目所发布的高品质输入法程序和词库
- [℞ 魔然](https://github.com/ksqsf/rime-moran)：反查、造词、中文数字小写转大写、Emoji、简码提示等均借鉴自魔然
- [℞ 地球拼音](https://github.com/rime/rime-terra-pinyin)：很多字的音调信息
- [℞ 冰雪拼音](https://github.com/hanzi-chai/rime-snow-pinyin)：整句模式使用的冰雪拼音数据
- [虎码](https://tiger-code.com/)：词频信息
- [测评工具](https://yb6b.github.io/#/)

<!-- --- -->

<!-- ## [![Star History Chart](https://api.star-history.com/svg?repos=rimeinn/rime-zrlong&type=Date)](https://star-history.com/#rimeinn/rime-zrlong&Date) -->

协议：方案主体依 [CC-BY 4.0](http://creativecommons.org/licenses/by/4.0/) 协议，除非对应文件中另有说明。
