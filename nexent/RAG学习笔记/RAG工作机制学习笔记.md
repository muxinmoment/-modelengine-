# RAG[^RAG]工作机制学习
## 基本任务：
先从资料库里检索相关内容，再基于这些内容来生成答案

## 没有RAG，直接带上内容的问题
1. 模型没法读取所有内容
2. 模型推理成本高
3. 模型推理慢
   
## RAG的基本流程
![alt text]({218BEEB3-91BA-43D4-AB6B-65AEAC91DA4E}.png)

### 分片的方式
![alt text](image.png)

### 索引
![alt text](image-1.png)

### MTEB排行榜
https://huggingface.co/spaces/mteb/
![alt text](image-2.png)

## 召回
![alt text](image-3.png)

## 重排
![alt text](image-4.png)
![alt text](image-5.png)
![alt text](image-6.png)














[^RAG]: Retrieval-Augmented Generation 检索增强生成

