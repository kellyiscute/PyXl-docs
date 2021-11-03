# Class Sheet

## 简述

Sheet对象对应工作簿中相应的工作表，用于对工作表进行操作。

**注意⚠️**： 工作表类**不应**由用户手动实例化，应通过`PyXl`类的`get_sheet()`或`add_sheet()`方法获得

---

## 构造函数\_\_init\_\_()

### 函数签名

```python
def __init__(self, sheet_name: str, excelize: Excelize):
  ...
```

### 参数

#### sheet_name

必须，工作簿中对应的工作表名称

### excelize

必须，由`PyXl`类传入对应的`excelize`对象。

---

## 实例字段

| 字段          | 类型              | 描述             | 只读？ |
| ------------- | ----------------- | :--------------- | ------ |
| visible       | bool              | 工作表是否可见   | 否     |
| sheet_name    | str               | 工作表名称       | 否     |
| sheet_index   | int               | 工作表索引       | **是** |
| format        | SheetFormat       | 工作表格式属性   | 否     |
| view_options  | SheetViewOptions  | 工作表视图       | 否     |
| page_layout   | SheetPageLayout   | 工作表页面布局   | 否     |
| margins       | PageMargins       | 工作表页边距     | 否     |
| header_footer | HeaderFooterStyle | 工作表页眉和页脚 | 否     |

