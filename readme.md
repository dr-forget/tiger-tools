# Tiger-CLI

Tiger-CLI is a command-line interface tool developed based on Vite 5.0. It allows for rapid setup of project architectures supporting Vue 3, React, and more, out-of-the-box without requiring extensive configuration.

- 💡 支持项目多环境配置
- 🛠️ 构建打包的依赖分析
- 📦  低版本浏览器的自动兼容
- 🔩  构建产物的模块的 CDN 引入
- 🔑  更多模块持续更新

## Installation

### Using npm

```bash
npm i @tiger-cli -g
```

### Using pnpm

```bash
pnpm install @tiger-cli -g
```

## Usage

###  Scaffold a Project

To scaffold a Vite + Vue project:

```bash
tiger-cli create --vue  #vue
```

To scaffold a Vite + React project:

```bash
tiger-cli create --react #react
```

## Run Development Server

```bash
npm run dev
```



## CLI Commands



| Command            | Types           | Default       | Description                             |
| ------------------ | --------------- | ------------- | --------------------------------------- |
| `-v` or `version`  | `string`        | `1.0.0`       | Check version number                    |
| `server`           |                 |               | Run the project                         |
| `-p` or `port`     | `string|number` | `8001`        | Set the port                            |
| `-e` or `env`      | `string`        | `dev`         | Set environment variables               |
| `-n` or `NODE_ENV` | `string`        | `development` | Specify NODE_ENV (default: development) |
| `build`            |                 |               | Build the project                       |
| `create`           | `vue|react`     | `vue`         | Create a project                        |
|                    |                 |               | - `--vue vue`: Vue template             |
|                    |                 |               | - `--react react`: React template       |



## Custom Configuration

Create a `tiger-cli` configuration file in the root directory supporting TypeScript (ts) and ECMAScript modules (mjs). The CLI only supports configuration files following ECMAScript standards due to its reliance on Vite 5.0, which will eventually deprecate CommonJS (cjs) APIs.



### Configuration Options



| Option                | Types                                                        | Default      | Description                                          |
| --------------------- | ------------------------------------------------------------ | ------------ | ---------------------------------------------------- |
| `vueIsJsx`            | `bool`                                                       | `false`      | Enable JSX support in Vue mode                       |
| `analyzeDependencies` | `object`                                                     |              | Dependency analysis configuration                    |
|                       | `bool`                                                       | `false`      | - `enable`: Enable dependency analysis               |
|                       | `bool`                                                       | `false`      | - `open`: Automatically open the analysis panel      |
| `polyfill`            | `object`                                                     |              | Configuration for compatibility with older browsers  |
|                       | `bool`                                                       | `false`      | - `enable`: Enable compatibility with older versions |
|                       | `string[]`                                                   | `['ie>=11']` | - `targets`: Target browser versions                 |
| `html_plugin`         | `object`                                                     |              | HTML injection configuration                         |
|                       | `bool`                                                       | `false`      | - `enable`: Enable HTML injection                    |
|                       | `string`                                                     | `index.html` | - `template`: HTML template entry                    |
|                       | `object`                                                     | `{}`         | - `injectData`: Data to be injected                  |
| `package_cdn`         | `object`                                                     |              | Module CDN import                                    |
|                       | `string[]|Module[]`                                          | `[]`         | - `modules`: Modules to import                       |
|                       | `string`                                                     | `""`         | - `cdnUrl`: CDN address for imported modules         |
| `custom_vite_config`  | `({mode,env,isPreview,isSSR})=>UserConfig|Promise<UserConfig>` | `()=>{}`     | Custom Vite configuration                            |
|                       | `vite->UserConfig`                                           |              | - Integrates the Vite UserConfig                     |



### License
This project is licensed under the [License Name] - see the LICENSE file for details.


This Markdown document outlines the Tiger-CLI tool, including installation, usage, CLI commands, custom configuration options in a tabular format, guidelines for contributing, and licensing information. Adjust the placeholders like `[License Name]`, `[link-to-issues]`, and `[link-to-license-file]` with appropriate details.

