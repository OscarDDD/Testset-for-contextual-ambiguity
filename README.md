# Testset-for-contextual-ambiguity

Common document-level metrics fail to evaluate the context-aware NMT systems properly. To solve this problem, we primarily focused on exploring how to extract contextual ambiguous sentences from
a large parallel dataset to build a document-level testset automatically to evaluate the performance of context-aware models accurately and easily.

We have conducted research mainly in the Chinese to English direction. There are two reasons for contextual ambiguity, namely different tenses and different subjects. After a series of extraction and filtering, we get our test set. The whole test set corresponds to the Chinese file in the dataset. They have the same number of rows and each row of the testset contains either 0 or 1. 1 means that the Chinese sentences in the same row in dataset has contextual ambiguity while 0 means that Chinese sentences in the same row in dataset has no contextual ambiguity. It is worth noting that the size of the test machine is overall small and more research is needed here.

## Datasets Installation
We mainly use two datasets: Open Parallel Corpus (OPUS) from WMT23 Shared Task: General Machine Translation and WMT23 Discourse-Level Literary Translation

To install the whole WMT23 Shared Task: General Machine Translation:

```bash
pip install mtdata==0.4.0
wget https://www.statmt.org/wmt23/mtdata/mtdata.recipes.wmt23-constrained.yml
for ri in wmt23-{enzh,zhen,ende,deen,enhe,heen,enja,jaen,enru,ruen,encs,csuk,enuk,uken}; do
  mtdata get-recipe -ri $ri -o $ri
done
```
To download only ZH->EN OPUS, follow the instruction [here](https://www2.statmt.org/wmt23/mtdata/).

To install WMT23 Discourse-Level Literary Translation, follow the instruction [here](https://www2.statmt.org/wmt23/literary-translation-task.html).
