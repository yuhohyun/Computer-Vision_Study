# Image Classification

## Classifier

![Untitled](Image%20Classification%203c8bc01c14c74df1a3d503d3d9891b1b/Untitled.png)

- Input : 영상 / Output : 카테고리
- 어떤 물체가 영상 속에 있는지 분류하는 매핑을 Classifier라고 함.

---

## K-Nearest Neighnbors Search

![Untitled](Image%20Classification%203c8bc01c14c74df1a3d503d3d9891b1b/Untitled%201.png)

- 질의 데이터가 들어오면, K개의 이웃데이터를 데이터베이스에서 찾음.
- 그 후, 데이터들이 갖고 있던 라벨 정보를 기반으로 분류함.
- 간단하지만 강력한 분류기
- 하지만, 검색하면서 걸리는 시간이 데이터 수에 비례해 증가함.
    
    ⇒ O(n) 복잡도
    
- 메모리 사용량이 증가함.
    
    ⇒ O(n) 복잡도
    

---

## Convolutional Neural Networks(CNN)

![Untitled](Image%20Classification%203c8bc01c14c74df1a3d503d3d9891b1b/Untitled%202.png)

- 방대한 데이터를 제한된 복잡도의 시스템에 압축하여 녹여냄.

### Fully-Connected Layer

![Untitled](Image%20Classification%203c8bc01c14c74df1a3d503d3d9891b1b/Untitled%203.png)

- 모든 픽셀들을 서로 다른 가중치로 Weighted Sum을 함.
- Non-Linear Activation Function을 통해서 분류 score로 출력함.
- 한계
    - Layer가 한 층이므로 단순해, 표현이 어려움.
    - Test Time에서의 문제…
        
        → Templete(영상)의 scale이 다르기 때문…
        

→ 이러한 이유로 CNN 등장!!

### Locally Connected Layer

![Untitled](Image%20Classification%203c8bc01c14c74df1a3d503d3d9891b1b/Untitled%204.png)

- 하나의 특징을 영상의 공간적인 특성을 고려해 국부적인 영역만 Connection을 고려한 Layer
- 필요한 parameter수가 획기적으로 줄어듦.
- Hidden Node의 Activation을 많이 뽑음.
    
    → Overfitting 방지 & 적은 수의 Parameter
    

### Convolutional Neural Networks(CNN)

- CNN은 많은 CV Task들에서 Backbone network로 사용됨.

---

## AlexNet

### Motivation

![Untitled](Image%20Classification%203c8bc01c14c74df1a3d503d3d9891b1b/Untitled%205.png)

- 1998년, Yann LeCun의 매우 간단한 CNN 구조
- Conv → Pool → Conv → Pool → FC → FC
- AlexNet의 Motivation이 됨.

### LeNet-5와의 차이점

- Layer가 7개로 늘어나 굉장히 Deep 해짐.
- 학습에 사용된 이미지도 큰 이미지.

### AlexNet’s Overall Architecture

<aside>
💡 **Conv → Pool → LRN → Conv → Pool → LRN → Conv → Conv → Conv → Pool → FC → FC → FC**

</aside>

![Untitled](Image%20Classification%203c8bc01c14c74df1a3d503d3d9891b1b/Untitled%206.png)

![LRN(Activation map에서 명암을 정규화함.) 생략](Image%20Classification%203c8bc01c14c74df1a3d503d3d9891b1b/Untitled%207.png)

LRN(Activation map에서 명암을 정규화함.) 생략

- 3x3 MaxPool → Dense
    - Tensor → Vector : 벡터화
    - Average Pooling을 이용해 공간 정보를 압축 긴 채널 축의 정보만 남겨둠.
    - **Flattening 이용 → Activation map을 어떠한 순서에 따라 쌓아둠.**
- Convolution Filter의 큰 Size
    
    → 최근 Network에선 큰 Size의 Convolution Filter를 사용하지 않음.
    

---

## VGGNet

![Untitled](Image%20Classification%203c8bc01c14c74df1a3d503d3d9891b1b/Untitled%208.png)

- AlexNet과 비교해 더 깊음.
- Linear Response Normalization(LRN) 사용 X
- 보다 작은 사이즈의 필터를 사용함.
- But, 상당히 개선된 성능을 보여줌.

### References
Naver BoostCourse - 컴퓨터 비전의 모든 것