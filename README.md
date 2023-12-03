# NER for French Transportation Data

This repository contains a Natural Language Processing (NLP) project focused on Named Entity Recognition (NER) using the spaCy library. The project is designed for processing French-language text data with a specific emphasis on transportation-related entities.

## Dataset

The dataset used in this project is composed of approximately 10,000 entries. It was meticulously constructed by writing multiple patterns of sentences. All entries represent trip requests with at least a departure location and an arrival location. Some entries also include additional information such as transit details or departure times.

| Name             | Description                  | Type               |
|------------------|------------------------------| ------------------ |
| `sentence`       | Request of a trip            | `string`           |
| `departure`      | Station or town of departure | `string`           |
| `arrival`        | Station or town of arrival   | `string`           |
| `transit`        | Station or town of transit   | `string` or `None` |
| `departure_time` | Departure time               | `string` or `None` |

## Dependencies
Install the dependencies:
```
pip install -r requirements.txt
```

## Usage
- Load the pre-trained spaCy model:
    ```
    import spacy
  
    nlp = spacy.load("./model/ner_transport_model")
    ```
- Process text data and extract named entities related to transportation.
  ```
  # Process a sample text
  text = "en passant par Lyon, je pars de Paris pour Marseille le 27 novembre à 9h"
  doc = nlp(text)

  # Extract and display named entities
  for ent in doc.ents:
      print(f"Entity: {ent.text}, Label: {ent.label_}")
  ```