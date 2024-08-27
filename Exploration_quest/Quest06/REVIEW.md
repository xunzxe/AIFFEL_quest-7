- [o]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요? (완성도)**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
    - 문제를 해결하는 완성된 코드란 프로젝트 루브릭 3개 중 2개, 
    퀘스트 문제 요구조건 등을 지칭
        - 해당 조건을 만족하는 부분의 코드 및 결과물을 캡쳐하여 사진으로 첨부
```
from diffusers import UniPCMultistepScheduler

openpose_pipe.scheduler = UniPCMultistepScheduler.from_config(openpose_pipe.scheduler.config)
openpose_pipe = openpose_pipe.to("cuda")

# Q. 코드를 작성해 보세요.
# 동일한 이미지를 생성하기 위해 seed를 넣어줍니다.
generator = torch.manual_seed(0)

#프롬프트를 작성합니다.
prompt =  'Donald Trump wearing an austronaut suit in the universe'
negative_prompt =  'blurry, low resolution, ugly, distorted, out of focus'

images = openpose_image

# 이미지를 생성합니다.
openpose_image1 = openpose_pipe(prompt=prompt, negative_prompt=negative_prompt, num_inference_steps=20, image=images).images[0]

# 생성된 이미지를 출력합니다.
openpose_image1
```

- [o]  **2. 프로젝트에서 핵심적인 부분에 대한 설명이 주석(닥스트링) 및 마크다운 형태로 잘 기록되어있나요? (설명)**
    - [ ]  모델 선정 이유
    - [ ]  하이퍼 파라미터 선정 이유
    - [ ]  데이터 전처리 이유 또는 방법 설명

- [o]  **3. 체크리스트에 해당하는 항목들을 수행하였나요? (문제 해결)**
    - [ ]  데이터를 분할하여 프로젝트를 진행했나요? (train, validation, test 데이터로 구분)
    - [ ]  하이퍼파라미터를 변경해가며 여러 시도를 했나요? (learning rate, dropout rate, unit, batch size, epoch 등)
    - [ ]  각 실험을 시각화하여 비교하였나요?
    - [ ]  모든 실험 결과가 기록되었나요?

- [o]  **4. 프로젝트에 대한 회고가 상세히 기록 되어 있나요? (회고, 정리)**
    - [ ]  배운 점
    - [ ]  아쉬운 점
    - [ ]  느낀 점
    - [ ]  어려웠던 점
```
생성되는 이미지 퀄리티가 좋아서 일단 신기했으나 생각보다 프롬프트대로 말을 듣게 하려면 명령어를 잘 입력해주는 방법을 먼저 터득해야 할 듯 하다.
마지막에 윤곽선 검출과 포즈 estimation을 같이 사용하는 controlnet을 사용하는데, 결국은 포즈이미지 대로 이미지가 생성되는 느낌이라 윤곽선 검출이 무슨 의미로 적용이 되는지 이해가 잘 되지 않았다.
실험을 위해 윤곽선 검출은 배경이 될 이미지도 넣어보았으나 별 차이가 없었다
김동규
DALL-E와 GPT를 플러터에서 쓸 수 있게 해보고싶습니다.
```

- [o]  **5.  앱으로 구현하였나요?**
    - [ ]  구현된 앱이 잘 동작한다.
    - [ ]  모델이 잘 동작한다.
