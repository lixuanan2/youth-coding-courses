# 青少年编程课程

给中小学生的编程课件，免费、开源。每门课是一个单独的仓库，课件是网页，点下面的按钮直接打开。

## 课程

| 课程 | 基础课件 | 项目课 | 仓库 |
| --- | --- | --- | --- |
| Python | [![打开 Python 基础课件](assets/button-python.svg)](https://lixuanan2.github.io/python-for-youth/basics/) | [井字棋](https://lixuanan2.github.io/python-for-youth/project/) | [python-for-youth](https://github.com/lixuanan2/python-for-youth) |
| C++ | [![打开 C++ 基础课件](assets/button-cpp.svg)](https://lixuanan2.github.io/cpp-for-youth/basics/) | 在做 | [cpp-for-youth](https://github.com/lixuanan2/cpp-for-youth) |
| AI | 还在设想，没有课件 | | |

## 老师本机

这个仓库也是老师本机的主文件夹，只放跨课程的说明，各门课的仓库 clone 在它里面。

### 上课

课件可以离线打开。上课时只复制对应课程的 `basics/dist/` 文件夹，双击里面的 `index.html`：

- Python：`python-for-youth/basics/dist/index.html`
- C++：`cpp-for-youth/basics/dist/index.html`

### 换电脑

先 clone 这个仓库，再在里面 clone 各门课：

```sh
git clone https://github.com/lixuanan2/youth-coding-courses.git ppt-claude
cd ppt-claude
git clone https://github.com/lixuanan2/python-for-youth.git
git clone https://github.com/lixuanan2/cpp-for-youth.git
git clone https://github.com/lixuanan2/ai-for-youth.git   # 私有仓库
```

### 公开和点评

公开课程、请人点评的准备在 [community/](community/README.md)。

### 做课

用 Claude Code 做课时，打开主文件夹或课程文件夹都可以。做新课的方法看各课程自己的 `README.md`，新增一门课的步骤在 [AGENTS.md](AGENTS.md)。
