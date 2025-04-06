<h1 align="center"> Halo Theme Joe3.0-EN  </h1>

<p class="badge-row" align="center">
  <a href="https://halo.run" target="_blank">
    <img src="https://img.shields.io/badge/dynamic/yaml?label=Halo&query=%24.spec.require&url=https://raw.githubusercontent.com/jiewenhuang/halo-theme-joe3.0/main/theme.yaml&color=113,195,71" alt="Halo"/>
  </a>
  <a href="https://github.com/jiewenhuang/halo-theme-joe3.0/releases" target="_blank">
    <img src="https://img.shields.io/github/v/release/jiewenhuang/halo-theme-joe3.0" alt="Release"/>
  </a>
  <a href="https://halo.run" target="_blank">
    <img src="https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-orange" alt="License"/>
  </a>
</p>

---
<p align="center">
<img width="100%" src="https://wmimg.com/i/70/2023/08/64d3c41d5bde2.webp">
</p>

Preview: [Jiewen's Blog](https://www.jiewen.run/?preview-theme=theme-Joe3)

Documentation: For some configurations, please refer to [Joe3 Incomplete User Guide](https://www.jiewen.run/archives/joe3use)
> halo-theme-Joe3.0-EN is a blog theme for [Halo2.0](https://halo.run/)  
> Adapted from [halo-theme-joe2.0](https://github.com/qinhua/halo-theme-joe2.0), thanks to the original author for the selfless contribution

## Installation

### Download and Install
Download from [releases](https://github.com/jiewenhuang/halo-theme-joe3.0/releases) or directly [download the code](https://github.com/jiewenhuang/halo-theme-joe3.0), then upload through the Halo Console backend theme installation.

## Instructions
> 1. For first-time use, please save all theme configurations first  
> 2. Some functions are implemented using plugins  
> 3. Please use with Halo 2.8.0 and above  
> 4. For menu icons, please use [iconfont](https://www.iconfont.cn/) icons, you need to fill in the Font Family and icon code, for example: `jiewen joe-icon-tupian`  
> 5. To use custom tag styles, please use them in the form of inserted HTML text. For tags, please refer to [Joe3 Partial Styles](https://www.jiewen.run/archives/joe3style) or use plugin tags directly

- [x] Card design
- [x] Responsive theme
- [x] Dark mode
- [X] Article table of contents
- [X] Code highlighting/language/copy
- [x] [Article search](https://github.com/halo-sigs/plugin-search-widget)
- [x] Display word count
- [x] Show related articles
- [X] [Comment system](https://github.com/halo-sigs/plugin-comment-widget)
- [x] [Friend links](https://github.com/halo-sigs/plugin-links)  
- [x] [Moments](https://github.com/halo-sigs/plugin-moments)  
- [x] [Gallery](https://github.com/halo-sigs/plugin-photos)  
- [x] Other features

## Theme Configuration

### Basic Settings

#### Waline Settings

##### Waline Basic Configuration

This configuration item allows custom basic configuration for Waline in JSON format. If the configuration doesn't take effect, please first check if the entered content is in JSON format. You can go to [JSON validation website](https://www.json.cn/) for format validation. To make it easier for users to fill in, here is an example, please refer to [Waline official website](https://waline.js.org/) for specific meanings and more configuration items.

```json
{
  "search":false,
  "reaction":true,
  "login":"force",
  "locale": {
     "placeholder":"Welcome to comment"
  },
   "emoji": [
      "//unpkg.com/@waline/emojis@1.2.0/weibo",
      "//unpkg.com/@waline/emojis@1.2.0/bmoji"
    ]  
}
```

##### Waline Image Upload Configuration

This configuration item can configure the image upload method for Waline

+ Default

The default image upload method can only upload images up to 128Kb

+ LskyPro

This configuration item can configure Waline to upload images to LskyPro, requiring a self-hosted LskyPro service

##### LskyPro Upload Settings

+ LskyPro Server URL

LskyPro server address, e.g., https://img.example.com/api/v1/upload (do not add a trailing slash)

+ LskyPro Token

LskyPro Token, e.g., `2|1bJbwlqBfnggmOMEZqXT5XusaIwqiZjCDs7r1Ob5`. By configuring the Token, you can control image upload permissions. If empty, uploads will be made as a guest (requires LskyPro to allow guest uploads)

How to get a Token?

Get it through the LskyPro API, request example as follows:

```bash
curl -X POST https://img.example.com/api/v1/tokens \
-H "Content-Type: application/json" \
-d '{
  "email": "email@qq.com",
  "password": "password***"
}'
```

If you encounter the following error, add the parameter `-k` at the end to ignore certificate verification

```bash
curl: (60) schannel: SEC_E_UNTRUSTED_ROOT (0x80090325) - More details here: https://curl.se/docs/sslcerts.html

curl failed to verify the legitimacy of the server and therefore could not
establish a secure connection to it.
```

Example response:

```json
{"status":true,"message":"success","data":{"token":"2|1bJbwlqBfnggmOMEZqXT5XusaIwqiZjCDs7r1Ob5"}}
```

### Blogger Information

#### Display Weather Information

>Note: The weather text color is white. Considering that users may use different backgrounds, if it's not suitable, please modify the font color through code injection to adapt to your blog

This configuration item configures whether to display weather information in the blogger information

#### Weather Plugin Token

Since the Hefeng Weather plugin has stopped service, it has been replaced with the Seniverse Weather plugin

1. Register an account

Go to the [Seniverse Weather official website](https://www.seniverse.com/) to register an account and log in to the console

2. Add product

The specific operation is shown in the figure below:

![Add product](docs/joe3_20240915184016.webp)

3. Configure the plugin and get the token

Go to this [website](https://www.seniverse.com/widgetv3) to configure the plugin. Currently, this website is not visible in the console, not sure if it will also stop service 😅

First, configure the plugin:

![Configure plugin](docs/joe3_20240915185024.webp)

Second, click generate code to get the token:

![Get token](docs/joe3_20240915185129.webp)

## Preview

WIP
## TODO
- [ ] Optimize gallery
- [ ] ......


### 🏭 Contribution

> If you want to help improve the `Joe3.0` theme, please:

- Star
- Submit issues
- Fix bugs
- Submit PRs

<br>  

### Contribution Tips
~~This repository is divided into main and dev branches. If you want to contribute code, please fork the dev branch, complete development, and submit a PR to the dev branch. The dev branch will be periodically merged into the main branch. The main branch is the stable version, and the dev branch has the latest code. PRs to main are not accepted.~~  
Now only the main branch is maintained, the dev branch is no longer maintained. If needed, please submit PRs directly to the main branch.


### 🙆‍♂️ Thanks

Thanks to the following projects for their support:

- [Halo](https://halo.run)
- [theme-starter](https://github.com/halo-dev/theme-starter)
- [Typecho Themes Joe](https://github.com/HaoOuBa/Joe)
- [Halo-theme-Joe2.0](https://github.com/qinhua/halo-theme-joe2.0)
- [Halo-theme-hao](https://github.com/liuzhihang/halo-theme-hao)
- [Halo-theme-sakura](https://github.com/LIlGG/halo-theme-sakura/tree/next)
- [plugin-links](https://github.com/halo-sigs/plugin-links)
- [plugin-comment-widget](https://github.com/halo-sigs/plugin-comment-widget)
- [plugin-search-widget](https://github.com/halo-sigs/plugin-search-widget)
- [plugin-moments](https://github.com/halo-sigs/plugin-moments)
- [plugin-photos](https://github.com/halo-sigs/plugin-photos)
- ......

<br>

### Discussion Group
QQ Group (929708466) Welcome to join for discussion and sharing  

![QQ Group](https://www.jiewen.run/upload/IMG_3508(20240717-140309).JPG)  

### TinyTale Mini Program  
[TinyTale Halo WeChat Mini Program Official Version Released](https://www.jiewen.run/archives/TinyTale-formal-edition)
![TinyTale](https://www.jiewen.run/upload/111.png)
