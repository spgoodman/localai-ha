[![hacs_badge](https://img.shields.io/badge/My_HACS-localai_conversation-41BDF5?logo=homeassistant&logoColor=white)](https://my.home-assistant.io/redirect/hacs_repository/?owner=spgoodman&repository=localai-ha&category=integration)
![GitHub all releases](https://img.shields.io/github/downloads/spgoodman/localai-ha/total?color=d9810f&label=Downloads&logo=GitHub)


<p align="center">
<img src="https://raw.githubusercontent.com/spgoodman/localai-ha/main/.attachments/icon.png#gh-light-mode-only">
<img src="https://raw.githubusercontent.com/spgoodman/localai-ha/main/.attachments/dark_icon.png#gh-dark-mode-only">
</p>

<h3 align="center">

[LocalAI Conversation Custom Integration](https://github.com/spgoodman/localai-ha) for Home Assistant
</h3>

# What This Is

This custom integration adds a conversation agent powered by [LocalAI](https://localai.io/) in Home Assistant, it's based on the [Azure OpenAI Conversation integration](https://github.com/joselcaguilar/azure-openai-ha) which in turn is based on the Azure [OpenAI Conversation integration](https://www.home-assistant.io/integrations/openai_conversation/) for Home Assistant.

By using this integration with LocalAI, you can run a ChatGPT-like conversation agent, using local resources. You need a high-spec machine; either with a high-end GPU or if using CPU, a machine with a large amount of RAM.

# What It Does

This conversation agent is unable to control your house. It can only query information that has been provided by Home Assistant. To be able to answer questions about your house, Home Assistant will need to provide LocalAI with the details of your house, which include areas, devices and their states.

## AI Models tested:

- luna-ai-llama2

# Installation and Configuration

1. Ensure that the conversation integration is enabled, it allows you to converse with Home Assistant, add the line below to your `configuration.yaml`:
```yaml
conversation:
```
2. Download and install the integration from HACS: [LocalAI Conversation](https://my.home-assistant.io/redirect/hacs_repository/?owner=spgoodman&repository=localai-ha&category=integration)
3. Restart your Home Assistant instance
4. Go to [Settings -> Devices & Services -> Add Integration -> LocalAI Conversation](https://my.home-assistant.io/redirect/config_flow_start/?domain=localai_conversation)
5. Type your `API Base` similar the example below and hit submit:
> - API Base: http://localhost:8080/ <br>

#  Options

Options for LocalAI Conversation can be set via the user interface, by taking the following steps:

1. Browse to your Home Assistant instance.
2. In the sidebar click on [Settings -> Devices & Services](https://my.home-assistant.io/redirect/integrations/).
3. If multiple instances of OpenAI Conversation are configured, choose the instance you want to modify and click on "Configure".

Options available:
- **Prompt Template:**
The starting text for the AI language model to generate new text from. This text can include information about your Home Assistant instance, devices, and areas and is written using [Home Assistant Templating](https://www.home-assistant.io/docs/configuration/templating).

- **Completion Model:** The name of the GPT language model deployed for text generation (i.e.- `luna-ai-llama2`). You can find more details on the available models in the [LocalAI Documentation](https://localai.io/model-compatibility/).

- Maximum Tokens to Return in Response
The maximum number of words or "tokens" that the AI model should generate in its completion of the prompt. 

- **Temperature:** A value that determines the level of creativity and risk-taking the model should use when generating text. A higher temperature means the model is more likely to generate unexpected results, while a lower temperature results in more deterministic results. 

- **Top P:** An alternative to temperature, top_p determines the proportion of the most likely word choices the model should consider when generating text. A higher top_p means the model will only consider the most likely words, while a lower top_p means a wider range of words, including less likely ones, will be considered. 

# Changelog

Please reference the [release history](https://github.com/spgoodman/localai-ha/releases).


## UI Translations

More languages can be added [here](./custom_components/localai_conversation/translations), contributions are welcome :)

Languages available:
- English

## Documentation

The [README](./README.md) file will be used for Documentation.

# License

[MIT](LICENSE) - By providing a contribution, you agree the contribution is licensed under MIT.
