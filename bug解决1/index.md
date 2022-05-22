# QTreeWidget.setModel() is a private method


当我使用

```python
...
self.file_tree = QtWidgets.QTreeWidget(self.frame)
self.file_tree.setMaximumSize(QtCore.QSize(248, 16777215))
self.file_tree.viewport().setProperty("cursor", QtGui.QCursor(QtCore.Qt.ArrowCursor))
...
```

然后设置系统文件系统

```python
self.file_model = QFileSystemModel()
file_index = self.file_model.setRootPath("./我的文档")
self.file_tree.setModel(self.file_model)
self.file_tree.setRootIndex(file_index)
```

的时候,报出了QTreeWidget.setModel() is a private method

解决方法:

出现错误的原因是QTreeWidget有自己的model,要设置model需要使用QTreeView


