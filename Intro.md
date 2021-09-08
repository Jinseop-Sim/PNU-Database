# Overview on Database
---
## Understanding & Modeling (Phase 1)
### Understanding
  - Physics : 무슨 일이 일어나는 지, 시간과 공간을 통한 움직임을 연구하고 이해하는 것
  - Economics : 사람들이 어떻게 가치에 반응하는지에 대해 이해하는 것
  - Philosophy : 이해한 것을 이해하는 것! 가장 중요한 부분이다.
  - 결국 우리가 이해한 것을 컴퓨터에게 이해를 시키기 위해서 우리는 이 부분을 중요하게 생각해야한다!

### Modeling
  - Formalism : Equations, Diagram .. etc.
  - Why Formalism?
    - We should make it clear (Verifiable)
    - Easy to implement
    - Diagrams(UML) and Algebra
 
## Implementation design and coding
  - Implementation is not final goal.
  - Application Management is goal.
  - Design & Coding
    - Convert formal understanding to Sketches
    - Methods(e.g. How to collect Data?)
    - Development environment
    - Architectures
    - Modules
 
## Lifecycle
### Software
  - Requirement Analysis(어떤 것이 필요한 지 먼저 생각해보는 것)
  - Functional Specification(Design)
  - Design
  - Development Environments
  - Coding
  - Test
  - Maintenance

### Database
  - Requirement Analysis
  - Modeling(Formal understanding)
  - Schema design
  - DB Environements
  - Data Collection and Input
  - Quality Control
  - Management and Retrieval
  
  - SW와 DB의 각 부분들은 순서대로 대응한다.

## Three Layered Structure (Three Schema)
- Physical Schema
  - 가장 밑 바닥에 위치하는 파트로, OS에 설치되어 진다.
  - Real World를 이해하려는 시도
  - 어떻게 File System에서 Data를 물리적으로 조직할 것인가? ==> DBSM Issue
- Logical Schema(Conceptual)
  - Physical Representation과는 독립적으로 구동된다.
  - Try to formal understand
  - 어떻게 정보를 이해하고 표현할 것인가 ==> DB Issue
- Application Schema(External)
  - Logical Representation을 기반으로 한다.
  - Application들은 Real World의 Conceptual understanding을 기반으로 Develop된다.
