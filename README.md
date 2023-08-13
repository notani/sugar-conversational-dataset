# SUGAR: A Textual Dataset for Situated Proactive Response Selection

This repository contains data for the paper ["Otani et al. 2023. A Textual Dataset for Situated Proactive Response Selection."](https://aclanthology.org/2023.acl-long.214/)


SUGAR (a dataset of SitUatated, Goal-Aware, and proactive Responses) contains 1,760 examples of single-turn English conversations in help-seeking scenarios. Each example includes a user request anchored by an implicit goal, a reference response, two extra response candidates, and 12 sentences of situational information. All response candidates are annotated with three-point appropriateness ratings to develop and evaluate response selection systems. The use of SUGAR is not limited to the development/evaluation of response selection systems. For instance, you can train situated response generation systems using SUGAR (See also [(Otani et al., NLP4ConvAI 2023)](https://aclanthology.org/2023.nlp4convai-1.2/)).

## Key Characteristics

![introduction](https://github.com/notani/sugar-conversational-dataset/assets/1850199/cbfbe404-91c9-412f-b594-1964933db9a3)

1. __Situational information__ plays an important role in conversations as we illustrate in the figure. The example shows two response candidates to a user utterance "Can you open the window for me?" Although both candidates here sound helpful, their appropriateness varies depending on context (the "Situation" boxes). We represent situational information of six semantic categories (Location, Possession, Time, Date, Behavior, and Environment) in free-form English texts.

2. While often being unspoken, __underlying goals__ ("to cool off" and "to air the room" in the example) provide important semantic connections among context and utterances on many occasions particularly when language is indirect. We used goal information as a stimulus for soliciting naturalistic and proactive responses from human annotators in data collection.

## Citation

Naoki Otani, Jun Araki, HyeongSik Kim, and Eduard Hovy. 2023. A Textual Dataset for Situated Proactive Response Selection. In Proceedings of the 61st Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers), pages 3856–3874, Toronto, Canada. Association for Computational Linguistics.

```
@inproceedings{otani-etal-2023-textual,
    title = "A Textual Dataset for Situated Proactive Response Selection",
    author = "Otani, Naoki  and
      Araki, Jun  and
      Kim, HyeongSik  and
      Hovy, Eduard",
    booktitle = "Proceedings of the 61st Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)",
    month = jul,
    year = "2023",
    address = "Toronto, Canada",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2023.acl-long.214",
    doi = "10.18653/v1/2023.acl-long.214",
    pages = "3856--3874",
}
```
