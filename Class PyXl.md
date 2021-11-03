# Class PyXl

## 简述

PyXl对应一个Excel文件，接受一个可选`path: str`参数

---

## 构造函数 \_\_init\_\_

### 函数签名

```python
def __init__(self, path: Optional[str]=None, password: Optional[str]=None, excelize: Optional[Excelize]=None):
  ...
```

### 参数

#### path

可选，传入时判断文件是否存在，存在则打开，不存在则创建。若不传入则创建，在 `save()` 函数中传入保存路径

#### password

可选，当打开带有密码保护的Excel工作簿时传入

#### excelize

可选，传入时使用传入的 `excelize` 对象作为底层API接口，未传入时使用全局 `excelize` 对象。当全局 `excelize`对象初始化失败并未传入 `excelize` 对象时报错 `ExcelizeNotDefinedException: "No global excelize instatiated and no excelize object passed in"`

### 异常

#### ExcelizeNotDefinedException

当无全局`excelize`对象存在且参数中未传入`excelize`对象时抛出

---

## get_sheet()

### 函数签名

```python
def get_sheet(self, sheet_name: str) -> Sheet:
  ...
```

### 参数

#### sheet_name

必须，指定要获取的工作表名称，大小写敏感

### 返回

对应的Sheet对象

### 异常

#### SheetNotFoundException

找不到对应的工作表时抛出

---

## add_sheet()

### 函数签名

```python
def add_sheet(self, sheet_name: str) -> Sheet:
  ...
```

### 参数

#### sheet_name

必须，指定新工作表的名称，必须唯一

### 返回

新创建的Sheet对象

### 异常

#### SheetAlreadyExistsException

工作表名称已经存在时抛出

---

## save()

### 函数签名

```python
def save(self, path: Optional[str]=None) -> None:
  ...
```

### 参数

#### path

可选，字符串，未传入时保存到初始路径，传入则作用为“另存为”功能。

**备注**：如果被另存为，下次再调用save()函数时（不传路径），会被保存到新的工作簿（被另存为的）

### 异常

#### FilePathNotDefinedException

当无初始路径且保存时未传入路径时抛出

---

