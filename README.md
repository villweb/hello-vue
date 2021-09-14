#### 主题

    vue空白脚手架。

#### 技术栈

    包含但不限于：vue, eslint，lint-staged，husky，prettier...

#### 目录结构

```bash
├── .husky                  # git hooks载体，便于我们在提交代码时做一些强制性规范操作
├── build                   # 启动脚本入口文件，webpack配置文件
│── config                  # 与环境相对应的配置文件
│── public                  # 承载构建产物
│── src                     # ----你懂的
    │── pages               # 业务代码入口
    │── components          # 公共组件
    │── images              # 图片
    │── util                #
    │── store               # 状态存贮集合
│── babelrc                 # babel配置文件
├── eslintrc                # eslint配置文件
│── .gitignore              # git忽视文件
├── prettierrc              # 统一风格prettier配置
│── commitlint.config.js    # 强校验commit -m 规范化（只对暂存区代码做处理）
│── index.template.html     # html模版
│── package-lock.json       # 依赖包本地版本
│── package                 # 依赖包版本控制，启动命令等。
│── README.md               # 库说明文件
```

#### lint-staged ， husky 搭配 prettier 和 eslint 在提交代码之前做代码格式检查

    1，husky 提供git操作的钩子函数，允许在git操作时执行额外动作
    2，lint-staged 提供只操作暂存区内的文件功能

#### git commit message 信息校验

安装：npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"'

commitlint 推荐我们使用 config-conventional 配置去写 commit
提交格式（注意冒号后面有空格）
git commit -m <type>[optional scope]: <description>

type ：用于表明我们这次提交的改动类型，是新增了功能？还是修改了测试代码？又或者是更新了文档？
optional scope：一个可选的修改范围。用于标识此次提交主要涉及到代码中哪个模块。
description：一句话描述此次提交的主要内容，做到言简意赅。

##### 常用的 type 类型

| 类型     | 描述                                                   |
| -------- | ------------------------------------------------------ |
| build    | 编译相关的修改，例如发布版本、对项目构建或者依赖的改动 |
| chore    | 其他修改, 比如改变构建流程、或者增加依赖库、工具等     |
| ci       | 持续集成修改                                           |
| docs     | 文档修改                                               |
| feat     | 新特性、新功能                                         |
| fix      | 修改 bug                                               |
| perf     | 优化相关，比如提升性能、体验                           |
| refactor | 代码重构                                               |
| revert   | 回滚到上一个版本                                       |
| style    | 代码格式修改, 注意不是 css 修改                        |
| test     | 测试用例修改                                           |

    总结：commit like this
        1，commit -m 'feact(home): 航空母舰上线'
        2，commit -m 'styles(home): 导航颜色调整'
        3，commit -m 'fix(home): 登陆白屏问题修复'
        4，commit -m 'docs(home): 组建丰富，添加XX组建'

#### 首版作者寄语

    前端技术栈，不断更新，如果你参与了丰富此库，请在下面留下你的大名，证明这个世界你来过，😄。
    第一版作者：guangyi.zhang(过客):2021-8-6

###### 说明

    1，本库采用commit校验，如果需要在编译的校验，在webpcak.base.config.js中放开eslint-loader即可。
    2，components组建内，包含目前百安居常用的组建，基本满足百安居后台管理系统的组建化要求。


## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
