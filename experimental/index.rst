.. _experimental:

试验阶段特性
==================

这部分介绍一些正处于试验阶段的Scrapy特性，
这些特性所涉及到的函数接口等还不够稳定，
但会在以后的发布版中趋于完善。所以在使用这些特性过程中需更谨慎，
并且最好订阅我们的 `邮件列表 <http://scrapy.org/community/>`_ 以便接收任何有关特性改变的通知。 

虽然这些特性不会频繁的被修改，但是这部分文档仍有可能是过时的、
不完整的或是与已经稳定的特性文档重复。所以你需要自行承担使用风险。

.. warning::

   本部分文档一直处于修改中。请自行承担使用风险。

使用外部库插入命令
-----------------------

你可以使用外部库通过增加 `scrapy.commands` 部分到 `setup.py` 的entry_points中来插入Scrapy命令。

增加 `my_command` 命令的例子::

  from setuptools import setup, find_packages

  setup(name='scrapy-mymodule',
    entry_points={
      'scrapy.commands': [
        'my_command=my_scrapy_module.commands:MyCommand',
      ],
    },
   )
