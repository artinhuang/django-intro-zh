# 编写您的第一个 Django 补丁

## 简介

有兴趣为社区做点贡献吗？也许您会在Django中发现您想要修复的漏洞，或者您希望为它添加一个小功能。

为Django做贡献本身就是解决您顾虑的最好的方式。这看起来似乎会令人生畏，但事实上其实很简单。我们将为您逐步讲解全过程，因此您可以通过相关例子进行学习。

### 本教程面向的读者

对于本教程，我们期待您至少对Django的工作方式有着基础的了解。这意味着您将能够 [**writing your first Django app**](https://docs.djangoproject.com/en/1.8/intro/tutorial01/)。此外，您对于Python语言本身也应有着良好的了解。但如果您不满足这一点的话，[Dive Into Python](http://www.diveintopython3.net/对于Python新手程序员而言会是一个优秀（并且免费）的在线电子书。

对于版本控制系统及Trac跟踪工具不熟悉的人来说，这份教程及其中的链接所包含的信息足以满足您们开始学习的需求。尽管如此，如果您希望定期为Django贡献，您可能需要阅读更多关于这些不同工具的相关信息。

对于本教程的大部分内容来说，本教程致力于尽可能进行讲解来为广大的读者提供帮助。

#### 何处获得帮助:

如果您在使用本教程时遇到困难，你可以发送信息给 [**django-developers**](https://docs.djangoproject.com/en/1.8/internals/mailing-lists/#django-developers-mailing-list)，或者登陆[**irc://irc.freenode.net/django-dev**](irc://irc.freenode.net/django-dev)向其他Django使用者寻求帮助。

### 本教程包含的内容

## 安装版本控制工具

## 获取Django 开发版的副本

## 回滚到Django旧有版本

## 第一次运行Django测试套件

## 为您的撰写测试用例

### 

```
class AdminURLWidgetTest(DjangoTestCase):
    def test_render(self):
        w = widgets.AdminURLFieldWidget()
        self.assertHTMLEqual(
            conditional_escape(w.render('test', '')),
            '<input class="vURLField" name="test" type="text" />'
        )
        self.assertHTMLEqual(
            conditional_escape(w.render('test', 'http://example.com')),
            '<p class="url">Currently:<a href="http://example.com">http://example.com</a><br />Change:<input class="vURLField" name="test" type="text" value="http://example.com" /></p>'
        )

    def test_render_idn(self):
        w = widgets.AdminURLFieldWidget()
        self.assertHTMLEqual(
            conditional_escape(w.render('test', 'http://example-äüö.com')),
            '<p class="url">Currently:<a href="http://xn--example--7za4pnc.com">http://example-äüö.com</a><br />Change:<input class="vURLField" name="test" type="text" value="http://example-äüö.com" /></p>'
        )

    def test_render_quoting(self):
        w = widgets.AdminURLFieldWidget()
        self.assertHTMLEqual(
            conditional_escape(w.render('test', 'http://example.com/<sometag>some text</sometag>')),
            '<p class="url">Currently:<a href="http://example.com/%3Csometag%3Esome%20text%3C/sometag%3E">http://example.com/&lt;sometag&gt;some text&lt;/sometag&gt;</a><br />Change:<input class="vURLField" name="test" type="text" value="http://example.com/<sometag>some text</sometag>" /></p>'
        )
        self.assertHTMLEqual(
            conditional_escape(w.render('test', 'http://example-äüö.com/<sometag>some text</sometag>')),
            '<p class="url">Currently:<a href="http://xn--example--7za4pnc.com/%3Csometag%3Esome%20text%3C/sometag%3E">http://example-äüö.com/&lt;sometag&gt;some text&lt;/sometag&gt;</a><br />Change:<input class="vURLField" name="test" type="text" value="http://example-äüö.com/<sometag>some text</sometag>" /></p>'
        )
```

### 运行新测试

## 编写Django源码

### 为标签#17549编写代码

### 确保测试通过

## 再次运行Django测试套件

## 撰写文档

## 为您的修改生成新的补丁

## 接下来做什么？

## 关于新贡献者的更多信息

## 寻找您的第一个真正的标签

## 接下来是？

