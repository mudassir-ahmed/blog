---
title: Mozilla's DeepSpeech an open source speech to text engine
excerpt: Mozilla's DeepSpeech an open source speech to text  engine
hero: https://user-images.githubusercontent.com/14970832/34458788-0cd47e8a-edc6-11e7-84ed-d8c09b1da3df.png
alt: mozilla deepspeech thumbnail
date: "2020-06-16 19:51:01"
tags:
  - javascript
  - deepspeech
---

In this article, we will be trying a transcriber made using Mozilla's DeepSpeech.

## Installation


Let's start with an example.

```bash
# Create and activate a virtualenv
virtualenv -p python3 $HOME/tmp/deepspeech-venv/
source $HOME/tmp/deepspeech-venv/bin/activate

# Install DeepSpeech
pip3 install deepspeech

# Download pre-trained English model files
curl -LO https://github.com/mozilla/DeepSpeech/releases/download/v0.7.3/deepspeech-0.7.3-models.pbmm
curl -LO https://github.com/mozilla/DeepSpeech/releases/download/v0.7.3/deepspeech-0.7.3-models.scorer
```

