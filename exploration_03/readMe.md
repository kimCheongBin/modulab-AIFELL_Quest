# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 김청빈
- 리뷰어 : 김태민


# PRT(Peer Review Template)
- [ ]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
        - 해당 조건을 만족하는 코드를 캡쳐해 근거로 첨부
        - 루브릭 1. 자기만의 카메라앱 기능 구현을 완수하였다.
        - ![image](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/29370771/e866160d-9401-4752-8e87-1ace7f08ba39)

        - 루브릭 2. 스티커 이미지를 정확한 원본 위치에 반영하였다.
        - ![image](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/29370771/d4bf54ea-dad8-48e9-89da-4bf62073343e)
          
        - 루브릭 3. 카메라 스티커앱을 다양한 원본 이미지에 적용했을 때의 문제점을 체계적으로 분석하였다.
            - 문제점에 대하여서 분석하지 못했습니다.
    
- [ ]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
        - 잘 작성했습니다.
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
        - ![image](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/29370771/a074e427-a413-456f-9237-83e208dd0469)

        
- [ ]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
        - 문제 원인 및 해결 과정에 대한 기록은 없습니다.
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 없습니다.
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
        
- [ ]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
	- ![image](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/29370771/95e9d98a-7e6d-43fd-8598-ce69225cac5b)
        
- [ ]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
        - 준수하였습니다.
    - 하드코딩을 하지않고 함수화, 모듈화가 가능한 부분은 함수를 만들거나 클래스로 짰는지
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화했는지
        - 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부합니다.
        - ![image](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/29370771/43259195-d1fe-4f5e-97c5-91c92c9dc58d)



# 참고 링크 및 코드 개선
```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
img_show[refined_y:refined_y+img_sticker.shape[0], refined_x:refined_x+img_sticker.shape[1]] = \
    np.where(img_sticker==255,sticker_area,img_sticker).astype(np.uint8)
- img_sticker == 255 부분에서 저는 img_sticker > 0보다 크게하여 0보다 크면 수염부분을 나타내는걸로 했습니다. 255로 해도 상관은 없지만 255인 부분만이라는 조건과 0보다 큰 모든 위치의 차이가 있습니다.
```


