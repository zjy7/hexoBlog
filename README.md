# hexoBlog

通过travis，将push至本仓库的代码自动执行hexo g，hexo d命令后，自动push至我的GitHub Page仓库，实现自动部署

具体步骤，如下

- hexo初始化操作 hexo init
- 建立仓库 <你的 GitHub 用户名>.github.io
- 建立仓库 blog（任意名称）
- 将 [Travis CI](https://github.com/marketplace/travis-ci) 添加到你的 GitHub 账户中
- 前往 GitHub 的 [Applications settings](https://github.com/settings/installations)，配置 Travis CI 权限，使其能够访问你的 repository
- 前往 GitHub 新建 [Personal Access Token](https://github.com/settings/tokens)，只勾选 repo 的权限并生成一个新的 Token。Token 生成后请复制并保存好
- 回到 Travis CI，前往你的 repository 的设置页面，在 Environment Variables 下新建一个环境变量，Name 为 GH_TOKEN，Value 为刚才你在 GitHub 生成的 Token。确保 DISPLAY VALUE IN BUILD LOG 保持 不被勾选 避免你的 Token 泄漏。点击 Add 保存。
- 在你的 Hexo 站点文件夹中新建一个 .travis.yml 文件：
```
language: node_js
node_js: stable

cache:
  directories:
    - node_modules

install:
  - npm install

script:
  - hexo g

after_script:
  - cd ./public
  - git init
  - git config user.name "zjy7"
  - git config user.email "zjy7@hotmail.com"
  - git add .
  - git commit -m "Update blog content by Travis CI"
  - git push --force --quiet "https://${GH_TOKEN}@${GH_REF}" master:master

branches:
  only:
    - master
```
- 将 .travis.yml 推送到 repository 中。Travis CI 应该会自动开始运行，并将生成的文件推送到GitHub Pages 下的 master 分支下
- 最后访问GitHub Pages