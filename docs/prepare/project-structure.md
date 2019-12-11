
## 文件类型说明

在 HttpRunner 自动化测试项目中，主要存在如下几类文件：

- `YAML/JSON`（必须）：测试用例文件，存储接口测试相关信息
- `debugtalk.py`（可选）：存储项目中逻辑运算辅助函数
    - 该文件存在时，将作为项目根目录定位标记，其所在目录即被视为项目工程根目录
    - 该文件不存在时，运行测试的所在路径（`CWD`）将被视为项目工程根目录
    - 测试用例文件中的相对路径（例如`.csv`）均需基于项目工程根目录
    - 运行测试后，测试报告文件夹（`reports`）会生成在项目工程根目录
- `.env`（可选）：存储项目环境变量，通常用于存储项目敏感信息
- `.csv`（可选）：项目数据文件，用于进行数据驱动
- `reports`：默认生成测试报告的存储文件夹

## 项目文件结构

对于接口数比较少，或者测试场景比较简单的项目，组织测试用例时无需分层。在此种情况下，项目文件的目录结构没有任何要求，在项目中只需要一堆 `YAML/JSON` 文件即可，每一个文件单独对应一条测试用例；根据需要，项目中可能还会有 `debugtalk.py`、`.env`等文件。

推荐的项目文件目录结构示例如下：

```bash
$ tree demo -a
demo
├── .env
├── debugtalk.py
├── reports
├── testcase1.yml
└── testcase2.json
```