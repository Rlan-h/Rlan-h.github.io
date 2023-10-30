---
title: 关于tsconfig.json
date: 2023-10-27 17:12:10
tags:
  - Ts
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

## 常用选项概览
```json
{
  "compilerOptions": {

    /* 基本选项 */
    "target": "es5", // 生成代码的 ECMAScript 目标版本
    "module": "commonjs", // 生成代码的模块标准
    "lib": ["es6", "dom"], // 编译过程中需要引入的库文件的列表
    "allowJs": true, // 是否编译 JS 文件
    "checkJs": true, // 是否在 JS 文件中报告错误
    "jsx": "preserve", // 在 .tsx 文件里支持 JSX: 'preserve', 'react-native', or 'react'
    "declaration": true, // 是否生成 .d.ts 类型定义文件
    "emitDeclarationOnly": true, // 只生成类型声明文件，不生成js
    "declarationMap": true, // 为每个 .d.ts 文件生成 sourcemap
    "sourceMap": true, // 是否生成 .map 文件
    "outFile": "./dist/main.js", // 将多个输出文件合并为一个文件
    "outDir": "./dist", // 输出文件夹
    "rootDir": "./", // 指定 TypeScript 编译器查找 TypeScript 文件的根目录，通常用于控制输入文件的搜索路径。假设你的 TypeScript 文件存储在项目的根目录下，你可以配置为 './'
    "composite": true, // 生成额外的元数据文件，这些文件可以帮助构建工具（包括TypeScript自身的--build模式）更快地确定项目是否已经被构建。
    "removeComments": true, // 删除注释
    "noEmit": true, // 不输出文件
    "importHelpers": true, // 通过 tslib 引入辅助工具函数
    "downlevelIteration": true, // 是否添加对迭代器和生成器的补丁（es6+无需关注）
    "useDefineForClassFields": true, // 是否使用 Object.defineProperty 定义类实例属性

    /* 严格的类型检查 */
    "strict": true, // 启用所有严格类型检查
    "noImplicitAny": true, // 不允许隐式的 any 类型
    "strictNullChecks": true, // 不允许把 null、undefined 赋值给其他类型变量
    "strictFunctionTypes": true, // 严格检查函数的类型
    "strictBindCallApply": true, // 严格检查 bind、call 和 apply 的参数规则
    "strictPropertyInitialization": true, // 类的实例属性必须初始化
    "noImplicitThis": true, // 不允许 this 有隐式的 any类型
    "noUnusedLocals": true, // 检查未使用的局部变量
    "noUnusedParameters": true, // 检查未使用的参数
    "noImplicitReturns": true, // 每个分支都会有返回值
    "noFallthroughCasesInSwitch": true, // 检查 switch 语句包含正确的 break

    /* 模块解析 */
    "isolatedModules": true, // 控制是否将每个文件作为单独的模块处理。
    "moduleResolution": "node", // 模块解析策略
    "allowImportingTsExtensions": true, // 允许从没有默认导出的模块中导入类型定义(.d.ts)文件
    "baseUrl": "./", // 解析使用非相对路径导入模块时的基地址
    "paths": {}, // 模块名称到基于 baseUrl 的路径映射表
    "rootDirs": [], // 将多个文件夹放在一个虚拟目录下，合并多个源文件目录
    "typeRoots": [], // typeRoots用来指定声明文件或文件夹的路径列表，如果指定了此项，则只有在这里列出的声明文件才会被加载
    "types": [], // types用来指定需要包含的模块，只有在这里列出的模块的声明文件才会被加载进来
    "allowSyntheticDefaultImports": true, // 允许从没有默认导出的模块默认导入
    "esModuleInterop": true, // 通过创建命名空间实现 CommonJS 兼容性
    "resolveJsonModule": true, // 自动解析JSON文件

    /* Source Map */
    "sourceRoot": "", // TypeScript 源代码所在的目录
    "mapRoot": "", // mapRoot用于指定调试器找到映射文件而非生成文件的位置，指定map文件的根路径，该选项会影响.map文件中的sources属性
    "inlineSourceMap": true, // 生成单个 sourcemaps 文件,而不是将 sourcemaps 生成不同的文件
    "inlineSources": true, // 将代码与 sourcemaps 生成到一个文件中

    /* 实验性 */
    "experimentalDecorators": true, // 启用实验性的装饰器特性
    "emitDecoratorMetadata": true // 为装饰器提供元数据支持
  },

    "files": [], // files可以配置一个数组列表,里面包含指定文件的相对或绝对路径,编译器在编译的时候只会编译包含在files中列出的文件,如果不指定,则取决于有没有设置include选项,如果没有include选项,则默认会编译根目录以及所有子目录中的文件。这里列出的路径必须是指定文件,而不是某个文件夹,而且不能使用* ? **/ 等通配符
    "include": [], // include也可以指定要编译的路径列表,但是和files的区别在于,这里的路径可以是文件夹,也可以是文件,可以使用相对和绝对路径,而且可以使用通配符,比如"./src"即表示要编译src文件夹下的所有文件以及子文件夹的文件
    "exclude": [], // exclude表示要排除的、不编译的文件,它也可以指定一个列表,规则和include一样,可以是文件或文件夹,可以是相对路径或绝对路径,可以使用通配符
    "extends": "", // extends可以通过指定一个其他的tsconfig.json文件路径,来继承这个配置文件里的配置,继承来的文件的配置会覆盖当前文件定义的配置。TS在3.2版本开始,支持继承一个来自Node.js包的tsconfig.json配置文件
    "compileOnSave": true, // compileOnSave的值是true或false,如果设为true,在我们编辑了项目中的文件保存的时候,编辑器会根据tsconfig.json中的配置重新生成文件,不过这个要编辑器支持
    "references": [], // 一个对象数组,指定要引用的项目
}

```