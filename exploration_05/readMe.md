# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 김청빈
- 리뷰어 : 이동희


# PRT(Peer Review Template)
- [x]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
```
1. 인물모드 사진을 성공적으로 제작하였다.	아웃포커싱 효과가 적용된 인물모드 사진과 동물 사진, 배경전환 크로마키사진을 각각 1장 이상 성공적으로 제작하였다. -> O
2. 제작한 인물모드 사진들에서 나타나는 문제점을 정확히 지적하였다.	인물사진에서 발생한 문제점을 정확히 지적한 사진을 제출하였다. -> O
3. 인물모드 사진의 문제점을 개선할 수 있는 솔루션을 적절히 제시하였다.	semantic segmentation mask의 오류를 보완할 수 있는 좋은 솔루션을 이유와 함께 제시하였다. -> O
```
![image](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/29495950/337bb43c-0125-4724-af69-6bb9817ec13f)
![image](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/29495950/9a3d62b7-71bc-47d2-98b6-b8e8fc5dee0c)
![image](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/29495950/122c9b84-b949-4776-ab15-a5e50ee7644d)
![image](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/29495950/77148d71-3bf7-4f68-b121-7eb85b7cd20d)
![image](https://github.com/kimCheongBin/modulab-AIFELL_Quest/assets/29495950/af18bce5-3c60-459e-a0f3-ebc1a32dd10e)


- [x]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드가 무슨 기능을 하는지, 왜 그렇게 짜여진건지, 작동 메커니즘이 뭔지 기술.
    - 주석을 보고 코드 이해가 잘 되었는지 확인
```py
# output의 픽셀 별로 색상이 seg_color와 같다면 1(True), 다르다면 0(False)이 됩니다
# seg_color 값이 person을 값이 므로 사람이 있는 위치를 제외하고는 gray로 출력
# cmap 값을 변경하면 다른 색상으로 확인이 가능함
seg_map = np.all(output==seg_color_person, axis=-1) 
print(seg_map.shape) 
plt.imshow(seg_map, cmap='gray')
plt.show()
```

        
- [ ]  **3. 에러가 난 부분을 디버깅하여 문제를 “해결한 기록을 남겼거나” 
”새로운 시도 또는 추가 실험을 수행”해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 문제에서 요구하는 조건에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        
- [x]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
```
- 배운점
    - 스마트폰의 인물모드의 트릭을 배웠다. (카메라가 많이 붙어 있는 폰을 사야하는 이유를 몸소 경험할 수 있었다.)
    - 광학에 대해서는 제대로 공부해본 적이 없지만 아웃포커싱을 통해 공부할 수 있었다.
    - 이미지 세그멘테이션 기법에 대해 학습할 수 있었고, 사용될 수 있는 모델 DeepLab을 배웠다.
- 아쉬운점
    - Unet이나 다른 세그멘테이션 모델을 활용하고 싶었으나 시도해보지 못했음
    - 제안하는 방법을 실험해보지 못했음
- 느낀점
    - 컴퓨터 비전 분야에 관심은 없었지만 생각보다 재밌는 것 같다.
```

        
- [x]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 하드코딩을 하지않고 함수화, 모듈화가 가능한 부분은 함수를 만들거나 클래스로 짰는지
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화했는지
```
함수 설명
___dlv3_segmentation___(img_path, model) -> segvalues, output

모델로 세그멘테이션 수행하여 값을 얻음
___Get_seg_backbround___(segvalues, background_image) -> img_mask_color,img_bg

de seg한 백그라운드 이미지 생성
___get_img_mask___(segvalues) -> img_mask, color_mask
원하는 OBJ의 세그멘테이션 값으로 마스크 생성
___search_seg_obj_color___(segvalues, obj = 'cat') -> 넘피 컬러값
원하는 OBJ의 컬러맵 정보 추출
___synthesis_img_and_seg___(segvalues,img_show)

세그멘테이션 마스크 값과 원본 이미지 겹쳐서 확인해보기
__concat_img___(img_mask_color,img_bg)

img_mask_color을 보고 np.where로 조건부 출력
즉, 마스크가 되어있으면 (값이 255) origin, 아니면 background의 픽셀을 가져옴
```


# 참고 링크 및 코드 개선
```
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.
```
