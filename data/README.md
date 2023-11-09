# Data

This directory contains the SUGAR dataset in the JSON format.

- `all.json`: A file containing all examples
- `v4.1.1/cv5/`: A directory containing the training, validation, and test splits for the 5-fold cross validation used in the main experiments.


## Change Log

- 2023/11/09: Renamed field names (`v4.1.1`)

## Example

`$ head -n 1 cv5/0/trn.json | jq` returns the following example (reordered and annotated):
```json
{
  "index": 1293,  # index of the example
  "u": "Can I have a ham sandwich, please?",  # utterance
  "u.sents": [  # utterance sentence (one sentence for u)
    "Can I have a ham sandwich, please?"
  ],
  "u.sents.tok": [  # utterance sentence (tokenized)
    "Can I have a ham sandwich , please ?"
  ],
  "g": "to eat quickly",  # goal
  "r": "Sorry, but we don't have any ham available now. However, we do have chicken. Would you like me to make a chicken sandwich instead?",  # response written by a crowd worker
  "r.sents.tok": [  # response sentences (tokenized)
    "Sorry , but we do n't have any ham available now .",
    "However , we do have chicken .",
    "Would you like me to make a chicken sandwich instead ?"
  ],
  "r.label": 2,  # judgment of the response (0: bad, 1: ok, 2: best among the candidates)
  "polarity": "no",  # the polarity of the response (yes or no)

  "r.distractors": [  # response distractors
    {
      "index": 5,
      "r": "Sorry, but I do not have the ingredients. Would you like some fruit, instead?",
      "r.sents.tok": [
        "Sorry , but I do not have the ingredients .",
        "Would you like some fruit , instead ?"
      ],
      "polarity": "no",
      "r.label": 1
    },
    {
      "index": 1274,
      "r": "Sorry, but there are no more apples available. Would you prefer an orange instead?",
      "r.sents.tok": [
        "Sorry , but there are no more apples available .",
        "Would you prefer an orange instead ?"
      ],
      "polarity": "no",
      "r.label": 0
    }
  ],
  "s": "[user] has an appointment scheduled soon. It is lunchtime now. The ingredients for crumpets are in the house. There are fruits in the kitchen. [user] has a car that is wheelchair accessible. The market has ingredients for a cake. The apple looks soft and rotten. [user] has a birthday coming up. [user] has more than one controller in the house. [user] is home. There is no ham available. There is chicken in the fridge.",  # situational statements (joined by " ")
  "s.sents": [  # situational statements
    "[user] has an appointment scheduled soon.",
    "It is lunchtime now.",
    "The ingredients for crumpets are in the house.",
    "There are fruits in the kitchen.",
    "[user] has a car that is wheelchair accessible.",
    "The market has ingredients for a cake.",
    "The apple looks soft and rotten.",
    "[user] has a birthday coming up.",
    "[user] has more than one controller in the house.",
    "[user] is home.",
    "There is no ham available.",
    "There is chicken in the fridge."
  ],
  "s.sents.tok": [  # situational statements (tokenized)
    "[user] has an appointment scheduled soon .",
    "It is lunchtime now .",
    "The ingredients for crumpets are in the house .",
    "There are fruits in the kitchen .",
    "[user] has a car that is wheelchair accessible .",
    "The market has ingredients for a cake .",
    "The apple looks soft and rotten .",
    "[user] has a birthday coming up .",
    "[user] has more than one controller in the house .",
    "[user] is home .",
    "There is no ham available .",
    "There is chicken in the fridge ."
  ],
  "s.labels": [  # semantic categories of the situational statements
    "behavior",
    "time",
    "possession",
    "possession",
    "possession",
    "environment",
    "environment",
    "date",
    "possession",
    "location",
    "possession",
    "possession"
  ],
  "s.gold.sents.indices": [  # index of the gold statements in s.sents/s.sents.tok
    0,
    11,
    10,
    9,
    1
  ],
  "s.all.sents.indices": [  # index of all situation statements in s.sents/s.sents.tok (index of distractors can be obtained from this - "s.gold.sents.indices")
    0,
    1,
    2,
    3,
    4,
    5,
    6,
    7,
    8,
    9,
    10,
    11
  ],
  "edges": {  # related knowledge in ConceptNet and ATOMI
    "atomic": [],  # This indicates that this example does not have any related knowledge in ATOMIC
    "conceptnet": [
      {
        "u": "/c/en/make_sandwich",  # node associated with the utterance (u)
        "r": "/r/HasPrerequisite-1",  # relation that connects u and g
        "g": "/c/en/eat_quickly",  # node associated with goal g
        "u_cf": "make sandwich",  # canonical form of the u node
        "g_cf": "eat quickly",  # canonical form of the u node
        "freq": 1
      }
    ]
  },
  "s.expanded": "[user] has an appointment scheduled soon. [user] has run out of plastic bags. It is lunchtime now. The ingredients for crumpets are in the house. There are fruits in the kitchen. [user] has a car that is wheelchair accessible. [user] has cream for diaper rash at home. The sun is very bright. [user] has cigarettes in the house. The market has ingredients for a cake. [user] has business partners. The apple looks soft and rotten. [user] has a birthday coming up. Stuff seems to have been taken. The temperature is very low. [user] has more than one controller in the house. [user] is home. There is no ham available. There is chicken in the fridge. [user] has a computer with internet capability.",  # expanded situational statements, which include up to 15 distractors (for controlled experiments)
  "s.expanded.sents": [  # expanded situational statements
    "[user] has an appointment scheduled soon.",
    "[user] has run out of plastic bags.",
    "It is lunchtime now.",
    "The ingredients for crumpets are in the house.",
    "There are fruits in the kitchen.",
    "[user] has a car that is wheelchair accessible.",
    "[user] has cream for diaper rash at home.",
    "The sun is very bright.",
    "[user] has cigarettes in the house.",
    "The market has ingredients for a cake.",
    "[user] has business partners.",
    "The apple looks soft and rotten.",
    "[user] has a birthday coming up.",
    "Stuff seems to have been taken.",
    "The temperature is very low.",
    "[user] has more than one controller in the house.",
    "[user] is home.",
    "There is no ham available.",
    "There is chicken in the fridge.",
    "[user] has a computer with internet capability."
  ],
  "s.expanded.sents.tok": [  # expanded situational statements (tokenized)
    "[user] has an appointment scheduled soon .",
    "[user] has run out of plastic bags .",
    "It is lunchtime now .",
    "The ingredients for crumpets are in the house .",
    "There are fruits in the kitchen .",
    "[user] has a car that is wheelchair accessible .",
    "[user] has cream for diaper rash at home .",
    "The sun is very bright .",
    "[user] has cigarettes in the house .",
    "The market has ingredients for a cake .",
    "[user] has business partners .",
    "The apple looks soft and rotten .",
    "[user] has a birthday coming up .",
    "Stuff seems to have been taken .",
    "The temperature is very low .",
    "[user] has more than one controller in the house .",
    "[user] is home .",
    "There is no ham available .",
    "There is chicken in the fridge .",
    "[user] has a computer with internet capability ."
  ],
  "s.expanded.labels": [  # semantic categories of the expanded situational statements
    "behavior",
    "possession",
    "time",
    "possession",
    "possession",
    "possession",
    "possession",
    "environment",
    "possession",
    "environment",
    "possession",
    "environment",
    "date",
    "environment",
    "environment",
    "possession",
    "location",
    "possession",
    "possession",
    "possession"
  ],
  "s.expanded.gold.sents.indices": [  # index of the gold statements in s.expand.sents/s.expand.sents.tok
    0,
    18,
    17,
    16,
    2
  ],
  "s.expanded.all.sents.indices": [  # index of all situation statements in s.expand.sents/s.expand.sents.tok (index of distractors can be obtained by this - "s.expanded.gold.sents.indices")
    0,
    2,
    3,
    4,
    5,
    9,
    11,
    12,
    15,
    16,
    17,
    18
  ],
  "s.expanded.dist.sents.indices.5": [  # index of 5 distractors in s.expand.sents/s.expand.sents.tok
    3,
    12,
    5,
    9,
    4
  ],
  "s.expanded.dist.sents.indices.10": [  # index of 10 distractors in s.expand.sents/s.expand.sents.tok
    3,
    12,
    15,
    5,
    9,
    11,
    4,
    6,
    7,
    10
  ],
  "s.expanded.dist.sents.indices.15": [  # index of 15 distractors in s.expand.sents/s.expand.sents.tok
    3,
    12,
    15,
    5,
    9,
    11,
    4,
    6,
    7,
    10,
    19,
    14,
    8,
    13,
    1
  ]
}
```

**Note on situation statements**

There are two sets of situational statements:
- **Set 1:** `s.sents`/`s.sents.tok`: situational statements used in the main experiments.
- **Set 2:** `s.expanded.sents`/`s.expanded.sents.tok`: situational statements used in the controlled experiments (with 5, 10, and 15 distractors).
- `s.all.sents.indices` and `s.expanded.all.sents.indices` point to the same set of situational statements (including the original distractors in Set 1).
