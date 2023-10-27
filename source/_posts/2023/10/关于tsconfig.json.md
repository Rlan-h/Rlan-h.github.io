---
title: 关于tsconfig.json
date: 2023-10-27 17:12:10
tags:
categories:
cover:
description:
password:
swiper_index:
swiper_desc:
swiper_cover:
---

## 概述

如果一个目录下存在一个 `tsconfig.json` 文件，那么它意味着这个目录是 `TypeScript` 项目的根目录。 `tsconfig.json` 文件中指定了用来编译这个项目的根文件和编译选项。

## 使用 tsconfig.json

- 不带任何输入文件的情况下调用 `tsc`，编译器会从当前目录开始去查找 `tsconfig.json` 文件，逐级向上搜索父目录。
- 不带任何输入文件的情况下调用 `tsc`，且使用命令行参数 `--project` （或 `-p` ）指定一个包含 `tsconfig.json` 文件的目录。

当命令行上指定了输入文件时，`tsconfig.json` 文件会被忽略。

## tsconfig.json各配置属性详解

- `compilerOptions`: 编译器的选项，如语言版本、目标 JavaScript 版本、生成的 sourcemap 等。
- `include`: 指定需要编译的文件路径或文件夹路径。
- `exclude`: 指定不需要编译的文件路径或文件夹路径。
- `files`: 指定需要编译的文件列表。
- `extends`: 指定继承自另一个 tsconfig.json 文件。
- `compileOnSave`: 指定是否在保存时编译文件。
- `buildOnSave`: 指定是否在保存时编译文件。
- `target`: 编译目标 JavaScript 版本，可以是 "ES3"，"ES5" 或 "ES2015" 等。
- `module`: 指定模块系统，可以是 "CommonJS"，"AMD" 或 "System" 等。
- `sourceMap`: 是否生成 sourcemap 文件。
- `outDir`: 编译输出目录。
- `rootDir`: 设置项目的根目录。
- `strict`: 是否开启严格类型检查。
- `noImplicitAny`: 是否禁止隐式 any 类型。
- `lib`: 指定要包含在编译中的库文件，如 "es2015"。
- `paths`: 指定模块路径别名。
- `baseUrl`: 指定基础目录。
- `jsx`: 指定 JSX 的处理方式。
- `allowJs`: 是否允许编译 JavaScript 文件。
- `checkJs`: 是否检查 JavaScript 文件。
- `declaration`: 是否生成声明文件。
- `declarationMap`: 是否生成声明文件的 sourcemap。
- `emitDecoratorMetadata`: 是否支持装饰器。
- `experimentalDecorators`: 是否支持实验性装饰器。
- `listEmittedFiles`: 是否列出所有输出的文件。
- `listFiles`: 是否列出所有编译过的文件。
- `locale`: 指定本地化语言。
- `mapRoot`: 指定 sourcemap 文件的根目录。
- `moduleResolution`: 指定模块解析策略。
- `noEmit`: 是否禁止输出 JavaScript 代码。
- `noEmitHelpers`: 是否禁止输出辅助函数。
- `noEmitOnError`: 是否在发生错误时禁止输出 JavaScript 代码。
- `noImplicitReturns`: 是否禁止隐式返回。
- `noUnusedLocals`: 是否检查未使用的局部变量。
- `noUnusedParameters`: 是否检查未使用的参数。
- `preserveConstEnums`: 是否保留 const 枚举。
- `pretty`: 是否格式化输出的 JavaScript 代码。
- `removeComments`: 是否移除注释。
- `skipLibCheck`: 是否跳过检查库文件。
- `sourceRoot`: 指定源文件的根目录。
- `suppressExcessPropertyErrors`: 是否禁止过多属性错误。
- `suppressImplicitAnyIndexErrors`: 是否禁止隐式 any 类型索引错误。
- `typeRoots`: 指定类型声明文件的根目录。
- `types`: 指定需要包含在编译中的类型声明文件。
- `watch`: 是否监视文件变化并重新编译。

需要注意的是，tsconfig.json 中的配置属性并不是编译器的所有选项，有些选项只能在命令行中使用 --flag 的方式传入。