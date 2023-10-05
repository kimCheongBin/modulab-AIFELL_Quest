# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 김청빈
- 리뷰어 : 김서연


# PRT(Peer Review Template)
- [X]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - <img width="883" alt="스크린샷 2023-10-05 오후 12 00 41" src="https://github.com/Seoyeon1129/modulab-AIFELL_Quest/assets/112914475/9d278f93-9b6c-41a3-b614-a133271624da">
    - <img width="975" alt="스크린샷 2023-10-05 오후 12 00 52" src="https://github.com/Seoyeon1129/modulab-AIFELL_Quest/assets/112914475/7157d32e-031a-48d4-b845-1f80a449eb19">
    - 3가지 모델을 시도함(LSTM, Conv, Conv+GlobalMaxPool)
    - 유사 단어 분석에 대한 내용이 없음
    - <img width="573" alt="스크린샷 2023-10-05 오후 12 20 21" src="https://github.com/Seoyeon1129/modulab-AIFELL_Quest/assets/112914475/11e3c46e-537d-4dee-8648-6a3c61a71c22">

    - 85% 정확도를 갖는 결과가 나왔다.
    
- [ ]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - ```python
        import matplotlib.pyplot as plt
        acc = history_dict['accuracy']
        val_acc = history_dict['val_accuracy']
        loss = history_dict['loss']
        val_loss = history_dict['val_loss']
        
        epochs = range(1, len(acc) + 1)
        
        # "bo"는 "파란색 점"입니다
        plt.plot(epochs, loss, 'bo', label='Training loss')
        # b는 "파란 실선"입니다
        plt.plot(epochs, val_loss, 'b', label='Validation loss')
        plt.title('Training and validation loss')
        plt.xlabel('Epochs')
        plt.ylabel('Loss')
        plt.legend()
        
        plt.show()
      ```
    - 어떤 모델에 대한 그래프인지 확인하기 어렵다.
    - <img width="865" alt="스크린샷 2023-10-05 오후 12 25 12" src="https://github.com/Seoyeon1129/modulab-AIFELL_Quest/assets/112914475/e7771d5f-fa3f-4b89-8368-58b304db790b">
    - 주석의 내용과 출력값의 내용이 일치하지 않음(주석에서는 15000개로 되어있으나 실제로는 136182개). 

        
- [ ]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - epoch-loss 그래프를 해석하고 이를 바탕으로 모델을 수정하거나 개선하면 더 좋을 것 같다.
    - 한국어 word2vec을 활용한 모델에서도 학습에 대한 분석 등이 추가되면 좋을 것 같다.

- [ ]  **4. 회고를 잘 작성했나요?**
    - 한국어 word2vec을 활용했을 때 오히려 성능이 저하되는 이유에 대한 내용을 작성하였다.
    - 새롭게 알게 된 점에 대해서도 내용을 작성하면 좋을 것 같다.
      
- [ ]  **5. 코드가 간결하고 효율적인가요?**
    - 그래프를 그리는 과정을 함수화하면 다양한 모델에 대해서 쉽게 그래프를 그릴 수 있을 것이다.

# 참고 링크 및 코드 개선
```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
