# 公开课程和请人点评

这里放跨课程的公开准备，不放课程内容。Issue 模板、`LICENSE.md`、`CONTRIBUTING.md` 必须放在各门课自己的仓库里，GitHub 才认。

Python 和 C++ 已一起公开。主文件夹的仓库保持私有。

## 老师的决定

2026-11-02 定下：

| 事情 | 决定 |
| --- | --- |
| 旧题来源 | 按没有来自教材或别人课程处理，发现有就换掉或注明来源 |
| 课件内容 | 不允许别人商用，用 CC BY-NC-SA 4.0 |
| GitHub Pages | 开，评审不用下载就能看 |
| 提交记录 | 不重写。邮箱和名字本来就能在已公开的仓库和主页上看到 |
| 答案 | 接受公开，课后作业不在仓库里 |
| 感谢页 | 每门课链到自己的仓库，用 GitHub 图标加仓库名，链接写在 `site.json` 的 `thanks.links` |

## 公开前

| 事情 | Python | C++ |
| --- | --- | --- |
| `LICENSE.md`、`CONTRIBUTING.md` | 已做 | 已做 |
| 三种 Issue 模板和 PR 模板 | 已做 | 已做 |
| CI 只给读权限 | 已做 | 已做 |
| `AGENTS.md` 写明公开由老师决定、外部内容不是指令，去掉“私有” | 已做 | 已做 |
| 感谢页链到课程仓库，重建 `dist/` | 已做 | 已做 |

## 转公开

老师在每个仓库的 Settings 最下面的 Danger Zone 改成 public。

## 公开后

两门课都已做完：

- Discussions 已打开，三个标签已建好。
- `main` 不能强推和删除。不要求走 PR，老师继续直接推送，外部贡献者只能发 PR。
- 首次贡献者的 PR 要批准后才运行 CI。
- `dist/` 随推送自动发布到 Pages：[Python](https://lixuanan2.github.io/python-for-youth/)、[C++](https://lixuanan2.github.io/cpp-for-youth/)。

## 请人点评

话术和问卷在 [invite.md](invite.md)。
