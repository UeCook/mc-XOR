# MC存档解密工具 (MC Archive Decrypt Tool XOR)

一个基于Web浏览器的Minecraft存档解密工具，支持自动推导密钥并解密加密的存档文件。

## 功能特点

- 无需手动输入密钥，自动从存档文件中推导解密密钥。
- 完全在浏览器中运行，无需后端服务器。
- 自动解密存档中的所有加密文件。
- 所有处理在本地完成，文件不会上传到任何服务器。

## 版本选择建议

**选择仓库版本：**
- 只需要基础的解密功能。
- 代码简洁，易于理解和修改。
- 需要完全开源且无任何外部依赖。
- 追求最小的文件体积。

**选择网页版本：**
- 更好的用户体验。
- 需要手动输入密钥的功能。
- 需要文件完整性检查和错误提示。
- 需要现代化的界面和交互。

## 版本列表

| 功能特性 | 仓库版本 | 网页版本 |
|---------|------------|---------|
| 基础解密功能 | ✅ | ✅ |
| 自动推导解密密钥 | ✅ | ✅ |
| 浏览器本地运行 | ✅ | ✅ |
| 自动解密加密文件 | ✅ | ✅ |
| 本地数据处理 | ✅ | ✅ |
| 更好地UI设计 | ❌ | ✅ |
| 手动密钥解锁 | ❌ | ✅ |
| 文件完整性检查 | ❌ | ✅ |
| 压缩包嵌套路径处理 | ❌ | ✅ |
| 是否开源 | ✅ | ❌ |

## 使用方法

### 在线使用

1. 访问工具网页[mc.uecook.top](https://mc.uecook.top)
2. 点击上传区域或拖拽加密的存档文件（.zip格式）
3. 点击"解密"按钮
4. 等待处理完成
5. 下载解密后的存档文件

### 本地运行

1. 克隆或下载项目文件
2. 在浏览器中打开 `mcXOR-MIT.html`
3. 按照在线使用方法操作

## 技术说明

### 工作原理

1. 读取上传的ZIP存档文件。
2. 使用JSZip库解压缩存档。
3. 从MANIFEST和CURRENT文件中自动推导XOR密钥。
4. 使用推导出的密钥解密db文件夹中的加密文件。
5. 将解密后的文件重新打包为ZIP格式。

### 技术栈

- [JSZip](https://github.com/Stuk/jszip) - JavaScript ZIP文件处理库
- JavaScript - 无需任何框架
- HTML5 File API - 文件读取处理

## 加密算法说明

本工具使用XOR加密算法对Minecraft存档进行加密。密钥通过以下方式推导：

1. 读取存档中的 `MANIFEST-数字` 文件和 `CURRENT` 文件
2. 提取文件名和内容的特征信息
3. 通过XOR运算推导出8字节密钥
4. 使用推导出的密钥解密所有加密文件


## 致谢

本项目基于以下开源项目：

- [JSZip](https://github.com/Stuk/jszip) - 由 Stuart Knightley, David Duponchel, Franz Buchinger, António Afonso 开发的JavaScript ZIP库
- [XOR-MC-Archive-Decrypt](https://github.com/HTMonkeyG/XOR-MC-Archive-Decrypt) - 由 HTMonkeyG 开发的Minecraft存档解密工具


## 依赖库许可证

### JSZip - MIT License

```
The MIT License

Copyright (c)2009-2016 Stuart Knightley, David Duponchel, Franz Buchinger, António Afonso

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

### XOR-MC-Archive-Decrypt - MIT License

```
The MIT License

Copyright (c)2023 HTMonkeyG

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 免责声明

本工具仅供学习和研究目的使用。请确保您有权解密目标存档文件。作者不对因使用本工具造成的任何数据丢失或损坏负责。

## 联系方式
uecook@outlook.com

---

如果这个项目对你有帮助，请给个星标支持一下！
