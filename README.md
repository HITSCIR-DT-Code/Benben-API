# 笨笨 API 接口现已对外开放调用，欢迎体验~

**摘要：**  笨笨 聊天机器人 API 接口 现已通过 CTP平台 对外开放，供开发者免费调用。接口目前支持 HTTP 调用，包括闲聊、咨询以及各种游戏技能，欢迎体验。如有任何使用问题或者建议可联系 [kyzhang@ir.hit.edu.cn](mailto:kyzhang@ir.hit.edu.cn) 。

更多使用说明可参考：https://hitscir-dt-code.github.io/Benben-API/

## 接口说明

### 请求示例代码

笨笨机器人相关接口目前可通过以下代码示例请求。

```python
import requests

data = {
  "bot_id": "9c5a7e90-14bb-49da-819f-300cc4cef827",
  "api_key": "e6bc4917-2ce6-440b-b8e3-0b49569ad069",
  "user_id": "user-001",
  "session_id": "session-007",
  "message": "你好",
  "msg_type": "text"
}
response = requests.post(url="http://120.25.81.83:16999/ctp/chat/api", json=data)
print(response.json())
```

> 上述命令返回的 JSON 数据格式如下

```json
{
  "bot_id": "9c5a7e90-14bb-49da-819f-300cc4cef827",
  "user_id": "user-001",
  "session_id": "session-007",
  "msg_type": "text",
  "reply": "你好，来个拥抱吧！"
}
```



### 请求/返回参数说明

**请求参数说明**

| 参数       | 说明                                       | 示例                                   |
| ---------- | ------------------------------------------ | -------------------------------------- |
| bot_id     | 机器人ID<br />提供公用机器人               | `9c5a7e90-14bb-49da-819f-300cc4cef827` |
| api_key    | API 秘钥<br />提供公用秘钥                 | `e6bc4917-2ce6-440b-b8e3-0b49569ad069` |
| user_id    | 当前聊天用户ID<br />根据情况初始化或者赋值 | `user-001`                             |
| session_id | 当前聊天会话ID<br />根据情况初始化或者赋值 | `session-007`                          |
| message    | 当前请求的消息                             | `你好`                                 |
| msg_type   | 当前消息类型<br />目前仅支持文本消息       | `text`                                 |

**返回参数说明**

| 参数       | 说明             | 示例                 |
| ---------- | ---------------- | -------------------- |
| bot_id     | 机器人ID         |                      |
| user_id    | 当前聊天用户ID   | `user-001`           |
| session_id | 当前聊天会话ID   | `session-007`        |
| msg_type   | 消息类型         | `text`               |
| reply      | 机器人返回的消息 | `你好，来个拥抱吧！` |



### 自定义使用

开发者可通过上述公开密钥直接调用公开闲聊机器人API，公开API现已内置所有笨笨功能。此外开发者可以登录 [CTP平台](http://221.207.166.58:8000/) 注册，支持开发、定制专属功能模块。



## 主要功能

笨笨目前支持以下多种功能，现均已对外开放使用。

| 功能名称   | 功能描述                                                     | 模块触发                       |
| ---------- | ------------------------------------------------------------ | ------------------------------ |
| 闲聊       | 检索单轮模块                                                 | “你是谁”<br />“你爸爸是谁”     |
| 天气咨询   | 多轮模块<br />根据用户咨询的地点、时间<br />调用接口查询天气并返回 | “哈尔滨今天天气怎么样”         |
| 主题对话   | 足球相关问答                                                 | 默认触发<br />“你知道梅西吗？” |
| 古文回复   | 多轮模块<br />触发后锁定直至输入“退出”<br />对用户输入语句用文言文进行回复 | "笨笨古文"                     |
| 聊小说     | 多轮模块<br />触发后锁定直至输入“退出”<br />笨笨扮演金庸小说人物角色<br />对自己的属性关系进行回答 | “笨笨聊小说”                   |
| 笨笨古诗   | 多轮模块<br />可进行诗词成语等5个小游戏                      | “笨笨古诗”                     |
| 成语接龙   | 多轮模块<br />可进行成语接龙游戏                             | “成语接龙”                     |
| 猜谜语     | 多轮模块<br />可进行字谜灯谜等猜谜语游戏                     | “猜谜语”<br />“来个字谜”       |
| 脑筋急转弯 | 多轮模块                                                     | “脑筋急转弯”                   |



## 关于笨笨

笨笨是由 [哈工大SCIR实验室](http://ir.hit.edu.cn/) 的 [对话技术小组](http://ir.hit.edu.cn/1979.html) 主导研发的一款面向普通用户的聊天机器人，具备开放域对话、知识问答、任务型对话以及对话式推荐等功能。2016年6月6日正式对外发布，搭载于微信公众号平台之上，截至2021年10月7日，关注人数达到6569。曾获“合创杯”第二届全国青年人工智能创新创业大会三等奖，中国人工智能学会最佳青年技术成果奖，相关研究成果发表在ACL等会议。

