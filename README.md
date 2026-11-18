# RecyclerView 列表 Demo

Android 入门练习：使用 `RecyclerView` + `Adapter` 实现带图片的纵向列表。

课程：Android 应用开发（2021 年第一次作业）

## 功能

在一个 `RecyclerView` 中展示 30 项图文列表，每项由本地图片和标题组成，使用 `LinearLayoutManager` 纵向排列。

## 核心代码

| 文件 | 作用 |
| --- | --- |
| [`app/src/main/java/com/example/recyclerview/MainActivity.java`](app/src/main/java/com/example/recyclerview/MainActivity.java) | 入口 Activity。构造 30 条数据，设置 `LinearLayoutManager` 和 Adapter |
| [`adapters/ListViewAdapters.java`](app/src/main/java/com/example/recyclerview/adapters/ListViewAdapters.java) | 自定义 Adapter，负责 ViewHolder 创建与数据绑定 |
| [`beans/ItemBean.java`](app/src/main/java/com/example/recyclerview/beans/ItemBean.java) | 列表项数据模型（`icon` + `title`） |
| [`beans/Datas.java`](app/src/main/java/com/example/recyclerview/beans/Datas.java) | 静态图片资源数组，共 10 张图循环使用 |
| [`res/layout/activity_main.xml`](app/src/main/res/layout/activity_main.xml) | 主布局，仅含一个 RecyclerView |
| [`res/layout/item_list_view.xml`](app/src/main/res/layout/item_list_view.xml) | 单项布局（ImageView + TextView） |

## 技术栈

- Java
- Android SDK（`compileSdk` 见 `app/build.gradle`）
- AndroidX：`recyclerview`、`appcompat`
- Gradle 构建

## 构建与运行

用 Android Studio 打开项目根目录，等待 Gradle 同步完成，然后运行到模拟器或真机。

```bash
./gradlew assembleDebug        # Linux / macOS
gradlew.bat assembleDebug      # Windows
```

## 目录

```
app/
  src/main/java/com/example/recyclerview/
    MainActivity.java          入口
    adapters/                  Adapter
    beans/                     数据模型
  src/main/res/
    layout/                   布局文件
    mipmap-xhdpi/p_*.jpeg     列表图片（10 张，约 1MB）
build.gradle                  模块构建脚本
settings.gradle               工程配置
```

## 已知问题

- `.idea/` 是 Android Studio 的本地配置目录，不应进版本库
- 提交信息为 `xx`，无实际含义
- 列表数据用硬编码的静态数组，未做分页或数据源抽象
