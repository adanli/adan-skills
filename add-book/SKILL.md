---
name: add-book
description: 向书单中添加新的书籍
version: 0.6
---

# add-book

## 什么时候用

当用户说“我想要读XX书”、“将XX书加入到书单中”、“我想要读XX类型的书”的时候，必须使用这个技能

## 工作流程

1. 调用create-book-dir技能，获取书单目录，将其作为ROOT_BOOK_PATH
1. 根据用户输入的信息，或者大模型推荐的书籍信息，将这些书籍添加到ROOT_BOOK_PATH/to_read.md文件中，格式：{书名}-{作者}-{出版信息}--{类型}

### 核心原则

1. 在往书单中添加书籍的时候，严格按照格式：{书名}-{作者}-{出版信息}--{类型}，如果其中有信息缺失的，帮我自动补全
2. 严格保证ROOT_BOOK_PATH/to_read.md和ROOT_BOOK_PATH/finish_read.md两个文档中的内容符合要求
