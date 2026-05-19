# News Summary & Voice Broadcast / 新闻摘要与语音播报

![分类](https://img.shields.io/badge/分类-媒体-green)

## 项目简介

当用户询问新闻动态、每日简报、世界大事时使用此技能。从可信的国际 RSS 源抓取新闻，生成文字摘要和语音播报。支持定时推送。

## 功能特性

- 新闻摘要
- 概述
- RSS 源
- BBC（主要源）
- 国际新闻
- 头条新闻
- 财经
- 科技
- Reuters
- 国际新闻
- NPR（美国视角）
- Al Jazeera（全球南方视角）
- 解析RSS
- 工作流程
- 文字摘要

## 使用示例

```bash
# 国际新闻
curl -s "https://feeds.bbci.co.uk/news/world/rss.xml"

# 头条新闻
curl -s "https://feeds.bbci.co.uk/news/rss.xml"

# 财经
curl -s "https://feeds.bbci.co.uk/news/business/rss.xml"

# 科技
curl -s "https://feeds.bbci.co.uk/news/technology/rss.xml"
```

```bash
# 国际新闻
curl -s "https://www.reutersagency.com/feed/?best-regions=world&post_type=best"
```

```bash
curl -s "https://feeds.npr.org/1001/rss.xml"
```

## 文件结构

```
SKILL.md
_meta.json
```

## 许可证

MIT License

---

更多项目请访问：[github.com/g3353534517-hue?tab=repositories](https://github.com/g3353534517-hue?tab=repositories)
