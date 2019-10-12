[![Package Quality](https://npm.packagequality.com/shield/@oopsunome/latest-gitignore.svg)](https://packagequality.com/#?package=@oopsunome/latest-gitignore)

# `@oopsunome/latest-gitignore`

添加 / 更新 `.gitignore`。直接从 [`github/gitignore`](https://github.com/github/gitignore) 项目 `master` 分支获取数据，而非 [`gitignore.io`](https://www.gitignore.io/)。

## 目录

- [`latestGitignore(needs, to)`](#latestgitignoreneeds-to)
    - [安装](#安装)
    - [使用](#使用)
- [命令行](#命令行)
    - [安装](#安装-1)
    - [使用](#使用-1)
- [相关](#相关)
- [参与开发](#参与开发)
- [贡献指南](#贡献指南)
- [证书](#证书)

## `latestGitignore(needs, to)`

- `needs` {Array | String} 需被 Git 忽略的内容的主题
- `to` {String} `.gitignore` 文件存储位置
- 返回: {Object}
  - `out` {String} 生成后的 `.gitignore` 所在位置
  - `message` {String} 生成结果简述

#### 安装

```shell
# 使用 NPM
$ npm i @oopsunome/latest-gitignore

# 使用 Yarn
$ yarn add @oopsunome/latest-gitignore
```

#### 使用

```javascript
import latestGitignore from '@oopsunome/latest-gitignore';

(async () => {
  console.log(await latestGitignore(
    [
      'macOS',
      'Windows',
      'Linux',
      'Node',
      'VisualStudioCode',
      'SublimeText',
      'CVS',
      'Diff',
      'Vim',
      'TortoiseGit',
    ],
    '.',
  ));

  /**
   * 输出:
   *
   * {
   *   out: '/Users/username/git-project',
   *   message: '成功添加 `.gitignore` 文件'
   * }
   */
})();
```

## 命令行

- [X] 支持通过配置文件自定义 [`github/gitignore`][github/gitignore] 模板，减少多项目下重复操作;
- [X] 从 [`github/gitignore`][github/gitignore] 实时下载，保证生成的 `.gitignore` 一定是最新的;

#### 安装

在全局系统环境下使用的话，需要先全局安装 [@oopsunome/latest-gitignore][@oopsunome/latest-gitignore]，

```shell
# 使用 NPM
$ npm i -g @oopsunome/latest-gitignore

# 使用 Yarn
$ yarn global add @oopsunome/latest-gitignore
```

#### 使用

```
$ 使用方式
    $ latest-gitignore <主题> <...> 选项 [...]

  选项
    --out, -o, '.gitignore' 文件存储位置，默认：'process.cwd()'

  示例
    $ latest-gitignore macOS Windows Linux Node -o .
```

## 相关
- [`@oopsunome/fast-gitignore`][@oopsunome/fast-gitignore] - 添加 / 更新 `.gitignore`。内嵌 [`@oopsunome/fast-gitignore`][@oopsunome/fast-gitignore] 维护但来自 [`github/gitignore`][github/gitignore] 的模板。

## 参与开发

**准备开发环境**

详细参见 [SETUP.md][SETUP.md]。

**安装依赖**

[`@oopsunome/latest-gitignore`][@oopsunome/latest-gitignore] 使用 [`Yarn`](https://yarnpkg.com/zh-Hans/) 包管理器，执行 `yarn install` 安装依赖。

**运行**

```shell
yarn start
```

**生产构建**

```shell
yarn build
```

**测试**

```shell
yarn test
```

## 贡献指南

仔细查阅 [CONTRIBUTING.md][贡献指南] 以了解详情。

## 证书

[`@oopsunome/latest-gitignore`][@oopsunome/latest-gitignore] 获得了 MIT 许可，仔细查阅 [LICENSE.md][证书] 以了解详情。

[贡献指南]: https://github.com/iTonyYo/latest-gitignore/blob/master/CONTRIBUTING.md
[证书]: https://github.com/iTonyYo/latest-gitignore/blob/master/LICENSE.md
[@oopsunome/latest-gitignore]: https://github.com/iTonyYo/latest-gitignore
[SETUP.md]: #
[github/gitignore]: https://github.com/github/gitignore
[@oopsunome/fast-gitignore]: https://github.com/iTonyYo/fast-gitignore
