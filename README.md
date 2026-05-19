# 新闻摘要与语音播报 / News Summary & Voice Broadcast

![分类](https://img.shields.io/badge/分类-媒体-green)

## 简介 / Overview

当用户询问新闻动态、每日简报、世界大事时使用此技能。从可信的国际RSS源抓取新闻，可生成语音摘要。

## 详细说明 / Details

## 概述

从可信的国际新闻源通过RSS获取并总结新闻。

## RSS 源

### BBC（主要源）
```bash
curl -s "https://feeds.bbci.co.uk/news/world/rss.xml"

curl -s "https://feeds.bbci.co.uk/news/rss.xml"

curl -s "https://feeds.bbci.co.uk/news/business/rss.xml"

curl -s "https://feeds.bbci.co.uk/news/technology/rss.xml"
```

### Reuters
```bash
curl -s "https://www.reutersagency.com/feed/?best-regions=world&post_type=best"
```

### NPR（美国视角）
```bash
curl -s "https://feeds.npr.org/1001/rss.xml"
```

### Al Jazeera（全球南方视角）
```bash
curl -s "https://www.aljazeera.com/xml/rss/all.xml"
```

## 解析RSS

提取标题和描述：
```bash
curl -s "https://feeds.bbci.co.uk/news/world/rss.xml" | \
  grep -E "<title>|<description>" | \
  sed 's/<[^>]*>//g' | \
  sed 's/^[ \t]*//' | \
  head -30
```

## 工作流程

### 文字摘要
1. 抓取BBC国际头条
2. 可选补充Reuters/NPR
3. 总结关键新闻

## 功能特性 / Features

- 新闻摘要
- 概述
- RSS 源
- 国际新闻
- 头条新闻
- 财经
- 科技
- 国际新闻
- 解析RSS
- 工作流程

## 使用示例 / Usage Examples

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

## 文件结构 / File Structure

```
SKILL.md
_meta.json
```

## 作者 / Author

Hermes Agent Community

## 许可证 / License

MIT License

---

更多技能请访问：[github.com/g3353534517-hue?tab=repositories](https://github.com/g3353534517-hue?tab=repositories)
