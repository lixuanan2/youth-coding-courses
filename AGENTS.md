# 青少年编程课程：主文件夹规则

默认简体中文。这里放所有课程，每门课一个文件夹，各自是独立的 Git 仓库。主文件夹是小仓库 `lixuanan2/youth-coding-courses`，只保存跨课程的说明，用 `.gitignore` 忽略所有课程文件夹。

## 文件夹

| 文件夹 | 仓库 | 内容 |
| --- | --- | --- |
| `python-for-youth/` | `lixuanan2/python-for-youth` | Python 课，共用模板以这里为准 |
| `cpp-for-youth/` | `lixuanan2/cpp-for-youth` | C++ 课 |
| `community/` | 主文件夹的仓库 | 公开课程和请人点评的准备，不放课程内容 |

## 规则

- 做哪门课，就先读那个文件夹里的 `AGENTS.md`，所有命令都在那个文件夹里运行。
- 一律用相对路径。给老师的命令从主文件夹写起，比如 `open python-for-youth/dist/index.html`。
- 一次只改一门课。课程内容在各自的文件夹里提交和推送。主文件夹的仓库只提交这里的说明文件，不放课程内容，也不用子模块。
- 课件是上课讲的，不写“必做”“选做”“作业”这类字样，题目也不分等级。课后作业老师另外布置。
- 只改一个值、结果一眼能看到的地方，用黄色框让学生直接在页面上改，省掉打开 IDE 的时间。写法见 `python-for-youth/.claude/skills/python-lesson/SKILL.md` 的“黄色框”。多行输出、循环、改结构、读报错、运行完整程序，或者做起来复杂、容易出错的，都用 IDE，不勉强。

## 共用模板

`template/`、`tools/`、`vendor/` 只在 `python-for-youth/` 里改，改好并通过检查后再同步。在主文件夹运行：

```sh
rsync -a --delete --exclude=__pycache__ --exclude=.DS_Store python-for-youth/template/ cpp-for-youth/template/
rsync -a --delete --exclude=__pycache__ --exclude=.DS_Store python-for-youth/tools/ cpp-for-youth/tools/
rsync -a --delete --exclude=.DS_Store python-for-youth/vendor/ cpp-for-youth/vendor/
```

同步后在 `cpp-for-youth/` 跑检查，通过了再提交。

## 新增一门课

比如 `ai-for-youth/`：

1. 新建文件夹和仓库，文件夹名与仓库名相同，都用 `<主题>-for-youth`。
2. 复制 `template/`、`tools/`、`vendor/`，再仿照现有课程写 `site.json`、`course.json`、`PROMPT.md`、`AGENTS.md`、`CLAUDE.md` 和 skill。
3. `tools/check.py` 目前只认 `python` 和 `cpp` 两种语言，新语言要先在 `python-for-youth/` 里加上。
4. 把新文件夹加进上面的表格和 `README.md`，再在主文件夹提交。文件夹名以 `-for-youth` 结尾，才会被主仓库忽略。
