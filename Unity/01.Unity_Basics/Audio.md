### Unity Audio 관련 정리

---

## AudioSource / Clip
---
AudioSource : 오디오를 실행 시켜주는 "스피커"같은 역할
AudioClip : 소리 파일 그 자체로, 재생 가능한 사운드를 뜻함
AudioListener : 오디오를 듣는 위치 <-- 보통 카메라에 붙임

---

## 2. AudioSource 주요 속성
| 속성 | 설명 |
|------|------|
| `clip` | 재생할 오디오 클립 |
| `loop` | 반복 재생 여부 |
| `playOnAwake` | 시작하자마자 재생할지 여부 |
| `volume` | 볼륨 크기 (0~1) |
| `pitch` | 음정 (속도도 영향을 줌) |
| `spatialBlend` | 2D~3D 사운드 비율 조절 (0: 2D, 1: 3D) |

---

## 3. Audio관련 메서드 요약

| 메서드 | 설명 |
|-----|-----| 
| Play() | 지정된 clip 재생 |
| Stop() | 재생 중지 |
| Pause() / UnPause() | 일시 정지 / 다시 재생 |
| PlayOneShot(clip) | clip을 한 번 재생 (겹쳐 재생 가능) |

---

## 4. 코드 예제

```csharp
[SerializeField] private AudioSource audioSource;
[SerializeField] private AudioClip clickSound;

void PlayClickSound()
{
    audioSource.PlayOneShot(clickSound);
}
```