# ISO/IEC

> - 국제표준화기구(ISO; International Organization for Standardization)
> - 국제전기기술위원회(IEC; International Electrotechnical Commission)

## 국제 제품 품질 표준

- **ISO/IEC 9126**: 품질 특성 및 평가 기준 제시
- **ISO/IEC 12119**: 패키지 SW 품질 요구사항 및 테스트
- **ISO/IEC 14598**: 품질 평가의 절차 규정
- **ISO/IEC 25000(SQuaRE; Software Product Quality Requirements and Evaluation)**: SW 품질 평가 통합 모델이며, 위의 3 모델 통합 버전임.
- **ISO/IEC 25010**: 9126에 호환성과 보안성을 강화함.

### ISO/IEC 9126 품질 특성

- **기능성(Functionality)**: 요구사항을 정확하게 만족하는 기능을 제공
  - 부특성: 적절성(적합성), 정확성, 상호운용성, 보안성, 호환성
- **신뢰성(Reliability)**: 요구된 기능을 정확하고 일관되게 오류없이 수행하는가
  - 부특성: 성숙성, 결함 허용성, 회복성
- **사용성(Usability)**: 사용자가 정확하게 이해하고 사용하는가
  - 부특성: 이해성, 학습성, 운영성, 친밀성
- **효율성(Efficiency)**: 할당된 시간동안 한정된 자원으로 얼마나 빨리 처리하는가
  - 부특성: 시간효율성, 자원효율성
- **유지보수성(Maintainability)**: 환경의 변화에 소프트웨어를 쉽게 개선, 확장, 수정할 수 있는가
  - 부특성: 분석성, 변경성, 안정성, 시험성
- **이식성(Portability)**: 소프트웨어를 다른 환경에서도 쉽게 적용할 수 있는가
  - 부특성: 적용성, 설치성, 대체성, 공존성

### ISO/IEC 14598 평가 특성

- **반복성(Repeatability)**
- **재현성(Reproducibility)**
- **공정성(Impartiality)**
- **객관성(Objectivity)**

### ISO/IEC 25000 구성요소

- **ISO/IEC 2500n**: 품질 관리 분야(Quality Management Division), SQuaRE를 용도에 맞게 적절히 사용할 수 있도록 설명함.
- **ISO/IEC 2501n**: 품질 모델 분야(Quality Model Division), 제품의 사용 품질 및 데이터에 대한 품질 모델을 설명하고, 품질 모델을 적용할 수 있도록 설명함.
- **ISO/IEC 2502n**: 품질 측정 분야(Quality Measurement Division), 품질 측정을 위한 참조 모델 및 수학적 정의를 설명하고, 다음 측정법을 적용할 수 있도록 설명함.
- **ISO/IEC 2503n**: 품질 요구사항 분야(Quality Requirement Division), 요구사항 명세에 대한 내용을 설명함.
- **ISO/IEC 2504n**: 품질 평가 분야(Quality Evaluation Division), 개발자/구매자/평가자 관점에서의 품질 평가를 위한 요구사항과 권장사항, 지침을 설명함.
- **ISO/IEC 25050 to 25099**: 확장 분야(SQuaRE Extension Division), SQuaRE에서 제시하는 품질 평가의 기본 모델 이외를 설명함.

## 국제 프로세스 품질 표준

- **ISO/IEC 9001**: 품질경영시스템의 요구사항을 규정한 국제표준
- **ISO/IEC 12207**: 소프트웨어 생명주기 프로세스 관련 규정
- **ISO/IEC 15504(SPICE; Software Process Improvement and Capability dEtermination)**: 프로세스 수행능력 평가 표준 프레임워크
- **CMM(Capability Maturity Model)**: SW 개발 조직 성숙도 수준 평가
- **CMMI(Capability Maturity Model Integration)**: CMM + 프로젝트 관리, 프로큐어먼트, 시스템 엔지니어링
  - 조직차원의 성숙도를 평가하는 단계별 표현과 프로세스 영역별 능력도를 평가하는 연속적 표현을 표현함.

### ISO/IEC 12207 구분

- **기본** 생명주기 프로세스: 획득, 공급, 개발, 운영, 유지보수
- **지원** 생명주기 프로세스: 문서화, 형상관리, 품질 보증, 확인, 합동검토, 감사, 문제해결
- **조직** 생명주기 프로세스: 관리, 기반구조, 개선, 교육

### ISO/IEC 15504 수행 능력 단계

- **불완전**: 프로세스가 구현되지 않았거나 목적을 달성하지 못한 단계
- **수행**: 프로세스가 수행되고 목적이 달성된 단계
- **관리**: 정의된 자원의 한도 내에서 그 프로세스가 작업 산출물을 인도하는 단계
- **확립**: 소프트웨어 공학 원칙에 기반하여 그 프로세스가 작업 산출물을 인도하는 단계
- **예측**: 프로세스가 목적 달성을 위해 통제되고, 양적인 측정을 통해서 일관되게 수행되는 단계
- **최적화**: 프로세스 수행을 최적화하고, 지속적인 개선을 통해 업무 목적을 만족시키는 단계

## 소스코드 품질 분석 도구

- **정적** 분석 도구: pmd, cppcheck, checkstyle, SonarQube, ccm, cobertuna
- **동적** 분석 도구: Avalanche, Valgrind

# 참고 자료

- [품질 요구사항](https://m.blog.naver.com/wook2124/222103002516)
- [정보처리기사-6장(화면설계,UI, 품질요구사항, ISO/IEC)](https://strap.tistory.com/entry/%EC%A0%95%EB%B3%B4%EC%B2%98%EB%A6%AC%EA%B8%B0%EC%82%AC-6%EC%9E%A5%ED%99%94%EB%A9%B4%EC%84%A4%EA%B3%84UI-%ED%92%88%EC%A7%88%EC%9A%94%EA%B5%AC%EC%82%AC%ED%95%AD-ISOIEC)
- [\[소프트웨어개발\] 품질 요구사항](https://velog.io/@thing-zoo/%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4%EA%B0%9C%EB%B0%9C-%ED%92%88%EC%A7%88-%EC%9A%94%EA%B5%AC%EC%82%AC%ED%95%AD)
- [ISO/IEC 25000 Series(SQuaRE Series) 소개 - 1부](https://blog.naver.com/suresofttech/221352227669)
- [ISO 9001(품질)](https://ksa.or.kr/ksa_kr/977/subview.do)
- [\[정보처리기사\] 소프트웨어 개발 표준](https://velog.io/@ssook1222/%EC%A0%95%EB%B3%B4%EC%B2%98%EB%A6%AC%EA%B8%B0%EC%82%AC-%EC%86%8C%ED%94%84%ED%8A%B8%EC%9B%A8%EC%96%B4-%EA%B0%9C%EB%B0%9C-%ED%91%9C%EC%A4%80)
