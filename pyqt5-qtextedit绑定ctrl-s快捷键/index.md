# pyqt5 QTextEdit绑定ctrl+s快捷键


继承QtWidgets.QTextEdit类,重写keyPressEvent
```python
class MyTextEdit(QtWidgets.QTextEdit):
    def __init__(self,parent):
        QtWidgets.QTextEdit.__init__(self)
        self.parent = parent
    def keyPressEvent(self,event):
        QtWidgets.QTextEdit.keyPressEvent(self,event)
        if event.modifiers() == QtCore.Qt.ControlModifier and event.key()==QtCore.Qt.Key_S:
            #具体的业务逻辑
```

