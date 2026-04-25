---
title: The TokenBreak Attack
date: 2025-06-12
categories: [NEWS]
tags: [TOKENBREAK,SECURITY,TEXT CLASSIFICATION,HIDDEN LAYER]
---

## Summary

Do you know which model is protecting each LLM you have in production? HiddenLayer’s security research team has discovered a novel way to bypass models built to detect malicious text input, opening the door for a new prompt injection technique. The TokenBreak attack targets a text classification model’s tokenization strategy to induce false negatives, leaving end targets vulnerable to attacks that the implemented protection model was put in place to prevent. Models using certain tokenizers are susceptible to this attack, whilst others are not, meaning susceptibility can be determined by model family.

## Introduction

HiddenLayer’s security research team has uncovered a method to bypass text classification models meant to detect malicious input, such as prompt injection, toxicity, or spam. This novel exploit, called TokenBreak, takes advantage of the way models tokenize text. Subtly altering input words by adding letters in specific ways, the team was able to preserve the meaning for the intended target while evading detection by the protective model.

The root cause lies in the tokenizer. Models using BPE (Byte Pair Encoding) or WordPiece tokenization strategies were found to be vulnerable, while those using Unigram were not. Because tokenization strategy typically correlates with model family, a straightforward mitigation exists: select models that use Unigram tokenizers.

To read the complete article see:

[The TokenBreak Attack](https://hiddenlayer.com/innovation-hub/the-tokenbreak-attack/) [🔗]