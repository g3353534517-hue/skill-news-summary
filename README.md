# News Summary / 新闻摘要与语音播报

![分类](https://img.shields.io/badge/分类-媒体-green)

## 项目简介

从可信的国际RSS源抓取新闻，生成文字摘要和语音播报。支持定时推送。

## RSS新闻源

BBC（主要源）：
- 国际新闻
- 头条新闻
- 财经
- 科技

Reuters（路透社）、NPR（美国视角）、Al Jazeera（全球南方视角）

## 工作流程

1. 从RSS源获取最新文章列表
2. 解析标题、摘要、发布时间
3. 生成结构化文字摘要
4. 可选：用Edge-TTS生成语音播报

## 文件结构

```
SKILL.md
_meta.json
```

## 许可证

MIT License
