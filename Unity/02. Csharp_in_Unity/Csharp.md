# C#

---

## 장점

### 간결한 문법  
Java보다 코드가 짧고 명확함. 세미콜론 생략 가능, 클래스 구조 단순함.

### 객체지향 지원  
클래스, 상속, 다형성, 캡슐화 모두 지원. Unity 개발에 적합한 구조 설계 가능.

### 자동 메모리 관리  
Garbage Collector가 있어서 메모리를 직접 해제할 필요 없음.

### 플랫폼 다양성  
.NET으로 데스크탑, 웹, 모바일 등 다양한 플랫폼 지원.

---

## 단점

### 상대적으로 낮은 성능  
GC로 인해 실시간 연산이 중요한 경우 C++보다 성능이 떨어짐.

### 플랫폼 종속성  
.NET 런타임 필요. 모든 플랫폼에서 완전히 독립적으로 동작하진 않음.

### Unity 특화 구조  
Unity 중심으로 익히면 순수 C#의 고급 기능(LINQ, async 등)을 놓치기 쉬움.

---

## 타입 안정성

- 정적 타입 언어로 컴파일 타임에 대부분의 에러를 잡아줌
- null 참조 관련 오류를 줄이기 위해 nullable 명시 가능

---

## 실행 구조

### .NET CLR  
C#은 .NET 런타임(Common Language Runtime) 위에서 실행됨.  
JVM과 비슷한 구조로, 플랫폼 독립적인 실행 환경을 제공.

### C# 프로그램 실행  
작성된 코드는 IL(Intermediate Language)로 컴파일되고,  
CLR이 해당 코드를 JIT(Just In Time) 방식으로 실행함.

---

## 사용 예시

### Unity 게임 개발  
- 2D / 3D 게임 개발  
- 캐릭터 이동, 충돌 처리, UI 등 구현

### 일반 소프트웨어 개발  
- 데스크탑 앱 (WPF, WinForms)  
- 웹 서버 (ASP.NET)  
- 모바일 앱 (Xamarin)

---

## 코드 예시

csharp
using UnityEngine;

public class MovePlayer : MonoBehaviour
{
    void Update()
    {
        transform.Translate(Vector3.forward * Time.deltaTime);
    }
}