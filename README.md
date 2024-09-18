# Translating Elasticsearch pipelines into text

## Setup
1. Get your Gemini API key here
https://ai.google.dev/gemini-api/docs/quickstart?lang=python

2. Create a separate `.env.hidden` file that will not be checked into Github
3. Start your docker compose with `docker compose --env-file .env.hidden --env-file .env up -d`

## Username/password
Kibana: elastic/cribldemo
Jupyter: cribldemo

## Install an integration
For example, Menu -> Integrations, then select Crowdstrike. Install Assets. Update Elastic2Cribl.ipynb with the name and version of the installed pipeline, i.e.
```python
PIPELINE_NAME = 'logs-crowdstrike.fdr-1.41.0'
```
## URLs
Kibana https://localhost:5601
Jupyter http://localhost:8888