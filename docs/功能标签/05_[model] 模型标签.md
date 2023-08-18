# [model] 模型标签 

用于选择语言模型和调整语言模型的参数。内置了比如`gpt3.5-turbo`，`gpt3.5-turbo-16k`, `gpt4`等。（gpt4需要你本身key有权限才可用）

不插入任何模型标签，默认是一个温度0.5的 gpt-3.5-turbo-0613 ，输入 token 超过4000后会自动使用 gpt-3.5-turbo-16k 。 如果需要一些定制特定参数的 ChatGPT 模型，比如调整温度，调整最大token、改变 system message 等，方法是在`设置->配置目录->models文件夹`中添加模型配置文件。每个文件是一个 yaml 文件，按下面格式写就可以了。只要是 ChatGPT 官方 API 的参数都可以传入。详见 [https://platform.openai.com/docs/api-reference/chat/create](https://platform.openai.com/docs/api-reference/chat/create)

```yaml
api: openai # 目前此处只能填openai
params: # 除了stream和message/prompt不要传入，其他ChatGPT官方支持的API参数都可以传入来调整模型
    max_tokens: 1500
    temperature: 0.8
system_message: "you are a help assistant" # 系统message可以此处传入
```

重启程序或切换一次无框模式后，即可以在标签中选择该模型。