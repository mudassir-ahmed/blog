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

The last line shows something note worthy - inference took less
time than the audio file length.

## Streaming to DeepSpeech

Make sure you have the [prerequisites](https://github.com/mozilla/DeepSpeech-examples/tree/r0.7/nodejs_mic_vad_streaming#prerequisites) before continuing.

```bash
# Prerequisites
wget https://github.com/mozilla/DeepSpeech/releases/download/v0.7.0/deepspeech-0.7.0-models.pbmm
wget https://github.com/mozilla/DeepSpeech/releases/download/v0.7.0/deepspeech-0.7.0-models.scorer

# Dependancies
sudo apt-get install libasound2-dev

# Clone and move into working directory
git clone https://github.com/mozilla/DeepSpeech-examples moz-ds-examples
cd moz-ds-examples/nodejs_mic_vad_streaming

# Install npm packages
npm install

# Start the server
node start.js
```

I had an issue where no verboise was given. This is because it uses the default
mic which may not exist.

So update `microphone` variable to the following - notice device property was
added to the [options](https://www.npmjs.com/package/mic#micoptions). Run
`arecord -l` to see the list of microphones installed.

```javascript
var microphone = mic({
  rate: "16000",
  channels: "1",
  debug: false,
  fileType: "wav",
  device: "plughw:2,0",
});
```

Now start streaming.

## Next steps

Mozilla's DeepSpeech has an API in C,.NET, Java, JavaScript (NodeJS/ElectronJS)
and Python so i'm sure you could integrate this the next time you need
speech-to-text - I know I will be. You may want to train your own models. You
could use this for an IoT device.
