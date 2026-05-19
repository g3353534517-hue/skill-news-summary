---
name: news-summary
description: 当用户询问新闻动态、每日简报、世界大事时使用此技能。从可信的国际RSS源抓取新闻，可生成语音摘要。
---

# 新闻摘要

## 概述

从可信的国际新闻源通过RSS获取并总结新闻。

## RSS 源

### BBC（主要源）
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

### Reuters
```bash
# 国际新闻
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
4. 按地区或主题分组

### 语音摘要
1. 生成文字摘要
2. 用OpenAI TTS生成语音
3. 以语音消息发送

```bash
curl -s https://api.openai.com/v1/audio/speech \
  -H "Authorization: Bearer ***" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "tts-1-hd",
    "input": "<新闻摘要文本>",
    "voice": "onyx",
    "speed": 0.95
  }' \
  --output /tmp/news.mp3
```

## 输出格式示例

```
📰 新闻摘要 [日期]

🌍 国际
- [标题1]
- [标题2]

💼 财经
- [标题1]

💻 科技
- [标题1]

🤖 AI动态
- [标题1]
```

## 最佳实践

- 摘要简洁，5-8条重点新闻
- 优先突发新闻和重大事件
- 语音版最多2分钟
- 平衡西方与全球南方视角
- 被问及时注明来源
- **所有输出必须使用中文**
