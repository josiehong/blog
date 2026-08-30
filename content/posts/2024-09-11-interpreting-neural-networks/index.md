---
title: "Interpreting Neural Networks: What Exactly Are We Analyzing?"
date: 2024-09-11
tags: ["Deep Learning", "Interpretation"]
categories: ["Wild Thoughts"]
summary: "What are we talking about when we discuss interpretable models? Thoughts on human-centric vs. model-centric explanations."
---

*This post is also available in [Chinese](#中文版) below.*

As someone who started my research career in deep learning, I wasn't initially that enthusiastic about explaining models. Deep learning models are often very "deep," and even if they achieve the desired goals, such as classifying images or predicting certain properties, they may not operate according to the logic we expect. Therefore, I always felt that it is quite arrogant for humans to try to understand deep learning models in our own way.

## Interpret Machine Learning Models from a Human Perspective, Why and Why Not?

However, it is quite common to understand new things based on one's own experiences. For instance, when learning a new language, people often tend to establish correspondences between the new language and their native language through translation.

But is the common choice always correct? I often think of the advice in the book *Word Power Made Easy*: learn new words as a child learns to speak. In this way of learning, our understanding of each word is based entirely on the new language itself, rather than simply mapping it to a known language. Additionally, we all know that there is no exact one-to-one correspondence between languages.

For example, the Chinese word "缘故" is difficult to translate with a single English word. Translating it as "cause" or "reason" might not fully capture the nuance of "缘故," which often implies a more subtle or indirect reason behind an event or situation. Such subtle differences that cannot be precisely described with a single English word sometimes lead to the creation of new terms or explanations to better convey the intended meaning.

## Understanding Models in Terms of Models

Currently, interpretable models can be divided into three categories [[1]](#references). The first category involves designing model structures based on known knowledge structures, which can be directly explained through the model parameters. The second category involves methods based on gradients or contributions, where various mechanisms are designed to measure the contributions of inputs and network components to the output. The third category involves perturbation-based methods, where contributions of various parts are determined by changing inputs and observing changes in outputs.

Firstly, when dealing with complex tasks, especially those with incomplete knowledge, the first method, although providing interpretability, inevitably sacrifices accuracy. This is clearly not a good approach for moving towards explainable general artificial intelligence.

Additionally, perturbation-based methods attempt to explain deep learning models using human understanding. For example, suppose you have a model for classifying cats and dogs. If you use a masking method to obscure the ear region in the image and observe changes in the model's predictions, if the predictions change significantly, you might infer that the ears are highly important for the model to identify cats or dogs. However, in reality, the model may rely more on overall visual context, such as the body shape and color features of the cat, and simply masking the ears might give incomplete or misleading explanations. Of course, the actual situation may be more complex, as there may be high-dimensional features in the data that we cannot understand. Therefore, while perturbation-based methods are intuitive, they may not fully capture the comprehensive internal mechanisms of deep learning models when processing complex data.

Although current gradient- or contribution-based methods consider only the independent effects of input or hidden layer neurons on the output, while ignoring interactions between different neurons, and these methods are less robust compared to perturbation-based explanations [[2]](#references), they seem to be closer to revealing the internal workings of the model.

## Final Thoughts

Although I believe that gradient-based or contribution-based explanation methods are the "ultimate way" to open the black box of machine learning, explaining models through human knowledge remains a pathway to building human trust in deep learning, analyzing data, and even discovering more scientific principles based on human understanding. Interpretable neural networks are not only for explaining the model itself but also for building trust and more.

---

## 中文版

### 可解釋模型:當我們在談論可解釋模型時我們在談論什麽?

作為一個從深度學習開始研究生涯的人,一開始我對於解釋模型並沒有那麼熱衷。深度學習模型往往非常「深」,即便它達成了我們期望的目標,例如分類一些圖片或預測某些性質,也不一定是按照我們所期望的邏輯運行。因此,我總覺得,人類試圖以自己的方式來理解深度學習模型,是非常傲慢的。

### 爲什麽(不)從人類的視角解釋機器學習模型?

但是,話又說回來,依據自己的經歷與經驗去理解新事物,是非常常見的選擇。就像學習一門新語言時,人們通常傾向於通過翻譯來建立新語言與舊語言的對應關係。

但常見的選擇就是正確的嗎?我時常想起《Word Power Made Easy》這本書中的建議:像剛學會說話的孩子一樣學習新詞。這樣學習時,我們對每個詞的理解完全基於新語言本身,而不是簡單地與已知語言做對應。此外,我們都知道,語言之間無法精確一一對應。

例如,「handle」這個詞很難用單一詞語翻譯。如果翻譯為「處理」,似乎與「process」無法區分,雖然「process」更適用於有系統的步驟和程序的處理。這種無法用單詞描述的微小差異,有時甚至會導致新詞的產生,比如「抓手」這個說法的產生。

### 以模型的方式理解模型

目前的可解釋模型可以分為三類 [[1]](#references)。第一類是根據已知的知識結構來設計模型結構,這類模型可以直接通過模型參數解釋。第二類是基於梯度(gradient)或貢獻(contribute)的方法,各種機制被設計出來衡量輸入及網絡各部分對輸出的貢獻。第三類則是基於擾動(perturbation)的方法,通過改變輸入並觀察輸出的變化來確定各部分的貢獻。

首先,當面對複雜任務,尤其是知識不夠完備的任務時,第一種方法雖然可以獲得可解釋性,但必然會犧牲精度。這顯然不是我們邁向可解釋的通用型人工智能的好方法。

此外,基於擾動的方法試圖用人類的理解來解釋深度學習模型。舉個例子,假設你有一個貓和狗的分類模型。若使用遮蔽(masking)方法將圖像中的耳朵區域遮蔽,並觀察模型的預測變化,若預測顯著變化,可能會推斷耳朵對模型識別貓或狗的重要性很高。但實際上,模型可能更依賴於整體視覺上下文,如貓的身體形狀和顏色特徵,僅遮蔽耳朵可能會給出不完整或誤導性的解釋。當然,實際情況可能更加複雜,因爲數據中可能存在更多我們無法理解的高維度特徵。因此,基於擾動的方法雖然直觀,但可能無法完全捕捉深度學習模型處理複雜數據時的全面內部機制。

雖然目前基於梯度或貢獻的方法僅考慮輸入或隱藏層神經元對輸出的獨立影響,並忽略了不同神經元之間的交互作用,而這些方法相比基於擾動的解釋在魯棒性上也較差 [[2]](#references),但它們似乎更接近於揭示模型內部運作的方向。

### 寫在最後

儘管我認為基於梯度或基於貢獻的解釋方法是我們打開機器學習黑盒的「最終方式」,但按照人類的知識來解釋模型仍然是讓人類信任深度學習,分析數據,甚至按照人類知識來發掘更多科學規則的途徑,這些方法的意義可能不僅僅在於解釋模型本身。

---

## References

1. Montavon, G., Samek, W. and Müller, K.R., 2018. Methods for interpreting and understanding deep neural networks. *Digital Signal Processing*, 73, pp.1-15. [[link]](https://www.sciencedirect.com/science/article/pii/S1051200417302385)
2. Ghorbani, A., Abid, A. and Zou, J., 2019. Interpretation of neural networks is fragile. In *Proceedings of the AAAI Conference on Artificial Intelligence* (Vol. 33, No. 01, pp. 3681-3688). [[link]](https://ojs.aaai.org/index.php/AAAI/article/view/4252)
