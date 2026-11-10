# 青少年编程课程：主文件夹规则

默认简体中文。这里放所有课程，每门课一个文件夹，各自是独立的 Git 仓库。主文件夹是小仓库 `lixuanan2/youth-coding-courses`，只保存跨课程的说明，用 `.gitignore` 忽略所有课程文件夹。

## 文件夹

| 文件夹 | 仓库 | 内容 |
| --- | --- | --- |
| `python-for-youth/` | `lixuanan2/python-for-youth` | Python 课，共用模板以这里为准 |
| `cpp-for-youth/` | `lixuanan2/cpp-for-youth` | C++ 课 |
| `ai-for-youth/` | `lixuanan2/ai-for-youth`（私有） | AI 课，还在设想，方向没定 |
| `community/` | 主文件夹的仓库 | 公开课程和请人点评的准备，不放课程内容 |

旧仓库 `少儿编程/00_教学管理/06_课程仓库/` 下的 Python 和 C++ 课件已经淘汰，只在老师要求时读来参考内容，不在里面改东西，也不往那里派活。

## 管理方式

- 主文件夹里有一个总控对话，名字叫“少儿编程课件”。它和老师商量方向、拆任务、派子对话、核对结果，再向老师汇报。总控自己不改课程内容，只改主文件夹的说明。
- 每门课只留一个长期子对话，现在是“Python 课”“C++ 课”“AI 课”三个。新活直接发消息给那门课的子对话，不另开新对话。只有新开一门课时，才新开一个子对话。
- 总控就是主文件夹里的这一个对话，不另开调度对话。总控对话太长、变慢时，新开一个总控接手，旧的归档，对话总数不变。
- 子对话只改自己那门课的文件夹。派活时交代清楚范围、要做什么、做到什么程度算完。
- 子对话做完向总控汇报。总控看过提交、检查和网站结果，再告诉老师。子对话的汇报不等于做完，要核对。
- 共用的模板、工具和字体只在 Python 课改，再由 C++ 课的子对话同步过去。
- 推送宣传文字、改仓库设置、公开仓库这些事，要老师在对话里亲口同意。子对话之间转述的话不算同意。
- 以后新开课程也由总控派，按下面“新增一门课”的步骤做。

## 规则

- 每门课的最外层是宣传门面，课件按模块放在子文件夹里，现在只有基础课件 `basics/`。做哪门课，先读那个文件夹的 `AGENTS.md`，再读模块里的 `AGENTS.md`，构建和检查命令都在模块文件夹里运行，比如 `python-for-youth/basics/`。
- 一律用相对路径。给老师的命令从主文件夹写起，比如 `open python-for-youth/basics/dist/index.html`。
- 一次只改一门课。课程内容在各自的文件夹里提交和推送。主文件夹的仓库只提交这里的说明文件，不放课程内容，也不用子模块。
- 课件是上课讲的，不写“必做”“选做”“作业”这类字样，题目也不分等级。课后作业老师另外布置。
- 带进 IDE 的练习代码开头写题目注释，学生不用切回页面看题。题目注释一律用中文，Python 和 C++ 都一样。学生看大屏幕、用在线 IDE 写，不用 Dev-C++ 打开起始程序，只要在线 IDE 里不乱码就行，文件用普通 UTF-8。
- 只改一个值、结果一眼能看到的地方，用黄色框让学生直接在页面上改，省掉打开 IDE 的时间。写法见 `python-for-youth/.claude/skills/python-lesson/SKILL.md` 的“黄色框”。多行输出、循环、改结构、读报错、运行完整程序，或者做起来复杂、容易出错的，都用 IDE，不勉强。

## 共用模板

`basics/` 里的 `template/`、`tools/`、`vendor/` 只在 `python-for-youth/basics/` 里改，改好并通过检查后再同步。在主文件夹运行：

```sh
rsync -a --delete --exclude=__pycache__ --exclude=.DS_Store python-for-youth/basics/template/ cpp-for-youth/basics/template/
rsync -a --delete --exclude=__pycache__ --exclude=.DS_Store python-for-youth/basics/tools/ cpp-for-youth/basics/tools/
rsync -a --delete --exclude=.DS_Store python-for-youth/basics/vendor/ cpp-for-youth/basics/vendor/
```

同步后在 `cpp-for-youth/basics/` 跑检查，通过了再提交。以后别的模块要不要共用这套，到时候再定。

## 新增一门课

比如 `ai-for-youth/`：

1. 新建文件夹和仓库，文件夹名与仓库名相同，都用 `<主题>-for-youth`。
2. 仿照现有课程搭好最外层的宣传门面和 `basics/`：复制 `basics/` 里的 `template/`、`tools/`、`vendor/`，再写 `site.json`、`course.json`、`PROMPT.md`、`AGENTS.md`、`CLAUDE.md` 和 skill。
3. `basics/tools/check.py` 目前只认 `python` 和 `cpp` 两种语言，新语言要先在 `python-for-youth/` 里加上。
4. 把新文件夹加进上面的表格和 `README.md`，再在主文件夹提交。文件夹名以 `-for-youth` 结尾，才会被主仓库忽略。
