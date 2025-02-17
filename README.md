Code for EMNLP 2020 Findings Paper: Language Generation via Combinatorial Constraint Satisfaction:A Tree Search Enhanced Monte-Carlo Approach

Seems this project is based on https://github.com/NingMiao/CGMH

## Requirement ##

- python
  - `>=3.6`

- python packages
  - PyTorch 1.2.0 or 1.3.0
  - numpy
  - pickle
  - Rake (pip install python-rake)
  - zpar (pip install python-zpar, download model file from https://github.com/frcchang/zpar/releases/download/v0.7.5/english-models.zip and extract it to `POS/english-models`)
  - skipthoughts (needed only when config.sim=='skipthoughts')
  - en (get en from https://www.nodebox.net/code/index.php/Linguistics and put under `liguistics/`)
  - Stanford CoreNLP (export CORENLP_HOME=/path-to-corenlp)
  - CoreNLP interface (pip install stanford-corenlp)
  - Huggingface Transformers (pip install transformers) 2.8.0
  - FastText 0.9.1 (cd fasttext; python setup.py install)
  
- word embedding
  - Download or train a word embedding first and place it at config.emb_path and set config.emb_path='word_max'.

## Language model download
- For a pretrained language model, please download the following file and extract it under model/.
- Correction and key-gen: https://drive.google.com/open?id=1L3q-xGD3lHNETfibERTIh-ciCXmzRs3i
- Paraphrase: https://drive.google.com/open?id=1kTjnqO69CjwpBXwPtOPT6v7Ur7ro5nRR. Please put the .pkl file under data/quora

## Word embedding download
- For a pretrained word embedding, please download the following file.
- Correction and key-gen: https://drive.google.com/open?id=1q79Dvrx3eapffHL4ApfrT0XpOgm3sKKF. Please put the .pkl file under data/1-billion
- Paraphrase: https://drive.google.com/open?id=1ggEdFyLIrr9sjfG1SHxjyHgOYNKy3ySE. Please put the .pkl file under data/quora

## Running ##
- Generation
  - For generating new sample for each tasks:    
      - Give inputs in `input/input.txt`, or change the `input` parameter in `config.py`
      - Change the `mode` parameter in `config.py`: `q` for questions, `i` for imperative, `n` for sentiment;
      - Run `python` `key_gen_search.py` / `sentiment_key_gen_search.py` to generate.  
      - Outputs are in `output`.

 - Details
   - Make sure that paths for package and data are correctly set in 'config.py'.
