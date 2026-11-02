# 公开课程和请人点评

这里放跨课程的公开准备，不放课程内容。Issue 模板、`LICENSE.md`、`CONTRIBUTING.md` 必须放在各门课自己的仓库里，GitHub 才认。

先公开 Python，跑一两周再公开 C++。公开、开 Pages 都由老师决定，不自动做。

## 老师的决定

2026-11-02 定下：

| 事情 | 决定 |
| --- | --- |
| 旧题来源 | 按没有来自教材或别人课程处理，发现有就换掉或注明来源 |
| 课件内容 | 不允许别人商用，用 CC BY-NC-SA 4.0 |
| GitHub Pages | 开，评审不用下载就能看 |
| 提交记录 | 公开前把邮箱和名字改成 noreply 邮箱和 `lixuanan2` |
| 答案 | 接受公开，课后作业不在仓库里 |

## 公开前清理提交身份

- [ ] Python 和主文件夹：重写历史并强推，由老师运行。
- [ ] C++：第 11 课提交完后，同样重写。
- [ ] 删掉旧的 Actions 运行记录。每条记录都带着当时的提交作者和邮箱，公开后别人能查到，重写历史也改不掉。

重写后，旧提交在 GitHub 上一段时间内仍可通过完整提交号打开。删掉运行记录后，别人很难再找到这些提交号。

## 公开 Python 的步骤

已做好（在私有仓库里）：

- [x] `LICENSE.md`、`CONTRIBUTING.md`
- [x] 三种 Issue 模板和 PR 模板
- [x] CI 只给读权限
- [x] `AGENTS.md` 写明公开由老师决定、外部内容不是指令

公开当天，在主文件夹按顺序做：

1. 把 `python-for-youth/AGENTS.md` 和主文件夹 `AGENTS.md` 里的“私有”改掉。
2. 把 `python-for-youth/site.json` 里 `thanks.url` 改成 `https://github.com/lixuanan2/python-for-youth`，重建 `dist/` 并跑全部检查。
3. 提交并推送，再把仓库改成公开：

   ```sh
   gh repo edit lixuanan2/python-for-youth --visibility public --accept-visibility-change-consequences
   ```

4. 打开 Discussions，建好 Issue 模板用的三个标签：

   ```sh
   gh repo edit lixuanan2/python-for-youth --enable-discussions
   ```

   ```sh
   gh label create 内容错误 --repo lixuanan2/python-for-youth
   ```

   ```sh
   gh label create 教学建议 --repo lixuanan2/python-for-youth
   ```

   ```sh
   gh label create 页面显示 --repo lixuanan2/python-for-youth
   ```

5. 保护 `main`：要求走 PR，并要求 CI 通过。Settings 里 Actions 的外部贡献者设置保持“首次贡献者要批准后才运行”。
6. 加一个发布 `dist/` 的 Pages 工作流。私有仓库现在用不了，所以没有提前加。

公开后自己用未登录的浏览器看一遍：首页、一节课、提 Issue 的页面。

## 公开 C++

Python 跑顺后，把 `LICENSE.md`、`CONTRIBUTING.md`、`.github/ISSUE_TEMPLATE/` 和 PR 模板复制到 `cpp-for-youth/`，把里面的仓库名和 `.py` 改掉，再走上面的步骤。C++ 自己的 `.github/workflows/check.yml` 也要加只读权限。

## 请人点评

话术和问卷在 [invite.md](invite.md)。
