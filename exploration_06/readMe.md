# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 김청빈
- 리뷰어 : 서민성


# PRT(Peer Review Template)
- [ ]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
        - 해당 조건을 만족하는 코드를 캡쳐해 근거로 첨부
        - Abstractive 모델 구성을 위한 텍스트 전처리 단계가 체계적으로 진행되었다.
            - 네 분석단계, 정제단계, 정규화와 불용어 제거, 데이터셋 분리, 인코딩 과정이 빠짐없이 체계적으로 진행되었습니다.
     
        - 텍스트 요약모델이 성공적으로 학습되었음을 확인하였다.
            - 네. 모델 학습이 진행되면서 train loss와 validation loss가 감소하는 경향을 그래프를 통해 확인했으며, 실제 요약문에 있는 핵심 단어들이 요약 문장 안에 포함되었습니다.
            -  ![스크린샷 2023-10-10 오전 11 59 43](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/138687269/b562d2f1-f544-4148-b85e-cbdd0239227b)
        -  Extractive 요약을 시도해 보고 Abstractive 요약 결과과 함께 비교해 보았다.
            - 네 두 요약 결과를 문법완성도 측면과 핵심단어 포함 측면으로 나누어 비교하고 분석 결과를 표로 정리하여 제시하였습니다.
            - ![스크린샷 2023-10-10 오후 12 02 03](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/138687269/f434b67e-6748-4056-83e8-7d100f83a85d)


    
- [ ]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 단어집합에서 5번 빈도 이하에 대한 단어의 개수를 확인하는 코드입니다.
        ```
        threshold = 6
        total_cnt = len(tar_tokenizer.word_index) # 단어의 수
        rare_cnt = 0 # 등장 빈도수가 threshold보다 작은 단어의 개수를 카운트
        total_freq = 0 # 훈련 데이터의 전체 단어 빈도수 총 합
        rare_freq = 0 # 등장 빈도수가 threshold보다 작은 단어의 등장 빈도수의 총 합
        
        # 단어와 빈도수의 쌍(pair)을 key와 value로 받는다.
        for key, value in tar_tokenizer.word_counts.items():
            total_freq = total_freq + value
        
            # 단어의 등장 빈도수가 threshold보다 작으면
            if(value < threshold):
                rare_cnt = rare_cnt + 1
                rare_freq = rare_freq + value
        
        print('단어 집합(vocabulary)의 크기 :', total_cnt)
        print('등장 빈도가 %s번 이하인 희귀 단어의 수: %s'%(threshold - 1, rare_cnt))
        print('단어 집합에서 희귀 단어를 제외시킬 경우의 단어 집합의 크기 %s'%(total_cnt - rare_cnt))
        print("단어 집합에서 희귀 단어의 비율:", (rare_cnt / total_cnt)*100)
        print("전체 등장 빈도에서 희귀 단어 등장 빈도 비율:", (rare_freq / total_freq)*100)
        ```

      
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
        - ![스크린샷 2023-10-10 오후 12 16 12](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/138687269/8cbefff6-74cd-48a2-9cf8-bab7227fffed)

        
- [ ]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
      - 해당부분은 확인하기 어려웠습니다. 
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
            - 학습을 10 epoch까지만 진행한 부분에 대한 이유를 잘 작성해주셨습니다.
            -  ![스크린샷 2023-10-10 오후 12 21 38](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/138687269/b0895d4a-76a8-4c6e-8e1b-d8cf84cd4871)


        
- [ ]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
        - 네 작성되었습니다.
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
            - ![스크린샷 2023-10-10 오후 12 10 19](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/138687269/6be22459-738d-4b3d-b750-1a28810f6e7b)

        
- [ ]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
        - 네 준수하여 작성하였습니다. 
    - 하드코딩을 하지않고 함수화, 모듈화가 가능한 부분은 함수를 만들거나 클래스로 짰는지
        -  네 함수화하여 작성되었습니다.
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화했는지
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
            -  ![스크린샷 2023-10-10 오후 12 15 25](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/138687269/15a969f3-d077-4b94-bcae-5754c5ddf184)



# 참고 링크 및 코드 개선
```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
