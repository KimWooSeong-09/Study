# Unity 데이터 구조화 - ScriptableObject 정리

---

## 1. ScriptableObject란?
- `MonoBehaviour`와 달리 씬(Scene)에 붙는 컴포넌트가 아님  
- **에셋 파일 형태로 프로젝트에 저장**되어, 여러 오브젝트에서 공유 가능  
- 장점:
  - 메모리 절약 (데이터 공유)
  - Inspector에서 값 수정 가능 → 코드 수정 없이 밸런스 조정 가능
  - 게임 실행 중에도 데이터 참조 가능

---

## 2. 기본 사용법

### 생성하기
```csharp
using UnityEngine;

[CreateAssetMenu(fileName = "NewItem", menuName = "Data/Item")]
public class ItemData : ScriptableObject
{
    public string itemName;
    public int attackPower;
    public Sprite icon;
}
```
CreateAssetMenu 어트리뷰트를 사용하면 Project 뷰에서 에셋 생성 가능

menuName = "Data/Item" → 우클릭 → Create/Data/Item 메뉴로 생성됨

---

## 3. 활용 예시
(1) 아이템 데이터
무기, 방어구, 소비템 등 공통 구조를 만들어두고 값만 다르게 설정

예시:

Sword.asset → 공격력 10

Shield.asset → 방어력 5

게임 내 인벤토리 시스템에서 해당 데이터를 불러와 사용 가능

(2) 스킬 데이터
```csharp
[CreateAssetMenu(fileName = "NewSkill", menuName = "Data/Skill")]
public class SkillData : ScriptableObject
{
    public string skillName;
    public float cooldown;
    public int damage;
}
```

불, 얼음, 번개 같은 스킬들을 각각 ScriptableObject로 만들어 관리

쿨타임/데미지 값을 Inspector에서 직접 수정 가능

---

## 4. 확장 활용
Event 시스템: ScriptableObject를 이벤트 전달 매개체로 사용

Config 데이터: 난이도, UI 색상, 경험치 테이블 등 설정값 관리

테스트/밸런싱 편의성: 프로그래머가 아닌 기획자도 수치 변경 가능

---

## 5. 느낀 점
데이터를 에셋으로 따로 관리하니 코드 수정이 줄어들고 깔끔해졌다

특히 아이템/스킬 같은 반복 구조는 ScriptableObject로 관리하는 게 훨씬 효율적임