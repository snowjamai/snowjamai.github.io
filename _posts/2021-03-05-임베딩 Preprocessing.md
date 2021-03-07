---
title: "임베딩에서의 Preprocessing"

categories:
- 임베딩

tags:
- 임베딩
- 딥러닝
- 자연어

use_math: true
comments: true
---

***
### 1. 말뭉치 데이터 얻기
임베딩을 위해서는 말뭉치(학습 데이터)가 필요
1. 직접 말뭉치를 만들기
2. 웹 문서에 대한 스크래핑(scraping)
3. 공개된 말뭉치 데이터 받아오기

### 2. 
1. 한국어 위키 백과에 대한 raw data 다운
```bash 
git pull origin master
bash preprocess.sh dump-raw-wiki
```

2. 다운받은 데이터 전처리
``` python
from gensim.corpora import WikiCorpus, Dictionary
from gensim.utils import to_unicode

input_f = "/notebooks/embedding/data/raw/kowiki-latest-pages-articles.xml.bz2"
output_f = "/notebooks/embedding/data/processed/processed_wiki_ko.txt"
for text in wiki.get_texts()
```
