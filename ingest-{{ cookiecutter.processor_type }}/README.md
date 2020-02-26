# Elasticsearch {{ cookiecutter.processor_type }} Ingest Processor

Explain the use case of this processor in a TLDR fashion.

## Usage


```
PUT _ingest/pipeline/{{ cookiecutter.processor_type }}-pipeline
{
  "description": "A pipeline to do whatever",
  "processors": [
    {
      "{{ cookiecutter.processor_type | replace("-", "_") }}" : {
        "field" : "my_field"
      }
    }
  ]
}

PUT /my-index/_doc/my_id?pipeline={{ cookiecutter.processor_type }}-pipeline
{
  "my_field" : "Some content"
}

GET /my-index/_doc/my_id
{
  "my_field" : "Some content",
  "potentially_enriched_field": "potentially_enriched_value"
}

GET my_index/_doc/my_id
{
  "my_field" : "asaaaaaa",
  "potentially_enriched_field": "potentially_enriched_value"
}

GET my_index/_doc/my_id
```

## Configuration

| Parameter | Use |
| --- | --- |
| some.setting   | Configure x |
| other.setting  | Configure y |

## Setup

In order to install this plugin, you need to create a zip distribution first by running

```bash
./gradlew clean check
```

This will produce a zip file in `build/distributions`.

After building the zip file, you can install it like this

```bash
bin/elasticsearch-plugin install file:///path/to/ingest-{{ cookiecutter.processor_type }}/build/distribution/ingest-{{ cookiecutter.processor_type }}-0.0.1-SNAPSHOT.zip
```

## Bugs & TODO

* There are always bugs
* and todos...

