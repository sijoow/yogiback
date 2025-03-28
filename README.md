# 출석체크 이벤트 개발

## 개요
- **이벤트 목표**: 3일 연속 출석체크에 성공한 고객에게 쿠폰을 지급하여 고객 참여 유도 및 재방문율 증가
- **핵심 기능**:
  - 매일 이벤트 참여 리스트를 MongoDB에 저장
  - 3일 연속 출석체크 성공 시 쿠폰 지급
  - 이벤트 참여 시 출석체크 도장 추가
  - 연속 출석체크 실패 고객에 대해 실패 문구 노출 후 체크 기록 초기화

## 기능 상세

1. **출석체크 참여 및 데이터 저장**
   - 고객이 매일 출석체크 이벤트에 참여하면 참여 내역이 MongoDB에 저장됨
   - 날짜별 참여 데이터를 기반으로 출석체크 기록을 관리

2. **3일 연속 출석체크 성공 및 쿠폰 지급**
   - 연속 3일 출석체크를 완료한 고객에게 쿠폰 지급
   - 출석체크 성공 여부를 확인하여 쿠폰 지급 로직을 실행

3. **출석체크 도장 및 실패 처리**
   - 이벤트 참여 시 출석체크 도장이 추가되어 고객에게 진행 상황을 시각적으로 제공
   - 연속체크에 실패한 경우, 실패 문구를 노출하고 출석체크 기록을 초기화하여 다시 도전할 수 있도록 함

4. **스케줄러 활용**
   - schedule 라이브러리를 활용하여 날짜별 참여 데이터 관리 및 이벤트 진행
   - 정해진 시간에 출석체크 상태를 업데이트하거나 초기화하는 작업 자동화

## 기술 스택
- **데이터베이스**: MongoDB
- **스케줄링**: schedule 라이브러리 등 (날짜별 데이터 관리 및 이벤트 자동화)
