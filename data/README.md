# Data policy

The archive contains deterministic split manifests under `manifests/`, but
does not redistribute HotpotQA, 2WikiMultiHopQA, MuSiQue, or Bamboogle raw
records. Download each benchmark from its official source and place local
copies under `data/external/` using the relative paths below:

```text
data/external/
├── HotpotQA/distractor/train-00000-of-00002.parquet
├── HotpotQA/distractor/train-00001-of-00002.parquet
├── HotpotQA/distractor/validation-00000-of-00001.parquet
├── 2WikiMultiHopQA/train.json
├── 2WikiMultiHopQA/dev.json
├── 2WikiMultiHopQA/test.json
├── musique/train-00000-of-00001.parquet
├── musique/validation-00000-of-00001.parquet
├── musique/test-00000-of-00001.parquet
└── Bamboogle/test-00000-of-00001-fd9def31e0acf72c.parquet
```

`configs/datasets.yaml` records the expected row counts, labels, and protocol
roles. The clean HotpotQA held-out manifest excludes the 50 identifiers
exposed during earlier debugging. The 2Wiki frozen evaluation is the disjoint
row range 500--12,575 after the declared 500-example compatibility pilot.

Do not commit `data/external/` to a public repository. Follow each benchmark's
license, citation, and redistribution terms. The archived result workbooks
and audit tables are sufficient to reproduce the paper statistics and figures
without access to the raw passages.
