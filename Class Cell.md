# Class Cell

## 简述

Cell对象对应工作簿中相应的工作表的单元格，用于对单元格进行操作。

**注意⚠️**： 单元格类**不应**由用户手动实例化，应通过`Sheet`类的`get_data()`方法获得

---

## 构造函数\_\_init\_\_()

### 函数签名

```python
def __init__(self, col: str, row: int, excelize: Excelize):
  ...
```

### 参数

#### col

必须，对应单元格所在列索引

#### row

必须，对应单元格所在行索引

### excelize

必须，由`PyXl`类传入对应的`excelize`对象。

---

## 实例字段

| 字段           | 类型              | 描述              | 只读？ |
| ------------- | ----------------- | :--------------- | ------ |
| row           | int               | 单元格所在行       | **是** |
| col           | str               | 单元格所在列       | **是** |
| axis          | str               | 单元格位置         | **是** |
| style         | Style             | 单元格样式         | 否     |
| runs          | List[RichTextRun] | 富文本格式         | 否     |
| comment       | str               | 单元格批注         | 否     |
| formula       | str               | 公式              | 否     |


