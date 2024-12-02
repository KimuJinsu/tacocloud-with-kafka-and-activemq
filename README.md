
# 🌮 **Taco Cloud Project: 실습 내용**

## 📌 프로젝트 소개
Taco Cloud는 **Spring Framework**를 활용한 웹 애플리케이션 프로젝트로, **Spring in Action** 도서를 기반으로 학습하며 구현하였습니다.  
이 프로젝트는 **백엔드와 프론트엔드의 통합**, **유저 인증 및 데이터 관리**를 중심으로 설계되었으며, 웹 애플리케이션 개발의 기초와 실무적인 기능 구현을 연습하기 위한 목적으로 진행되었습니다.

---

## 🎯 **주요 학습 목표**
1. 🖥️ **Spring MVC**를 활용한 웹 애플리케이션 설계 및 구현.
2. 🌐 **Thymeleaf**를 사용한 동적 HTML 렌더링 및 UI 구현.
3. 🔐 **Spring Security**를 이용한 인증 및 권한 관리 학습.
4. 🗄️ **H2 Database**를 활용한 데이터 관리 및 JPA 활용.
5. 📡 **REST API**와 **프론트엔드 연동** 실습.
6. 💬 **ActiveMQ 및 Kafka**를 활용한 메시징 기능 학습.

---

## 🛠️ **프로젝트 주요 기능**

### 1️⃣ 사용자 등록 및 로그인
- ✅ 사용자 등록 시 **Spring Security**를 활용한 암호화된 비밀번호 저장.
- ✅ 로그인 기능 구현을 통해 Spring Security의 인증 흐름 이해.
- ✅ 사용자 프로필 정보 입력 및 데이터베이스 저장:
  - **Username**
  - **Password**
  - **Email**
  - **Address**

### 2️⃣ 타코 주문 관리
- 🛒 **주문 관리 시스템**을 구현하여 사용자별 주문 내역 저장.
- 🗃️ 주문 시 입력된 데이터를 H2 Database에 저장하고, 데이터가 UI에 반영되도록 설계.
- ✔️ 입력 검증(Validation)을 통해 올바른 형식의 데이터를 받도록 처리.

### 3️⃣ 동적 UI 구현
- 🖼️ **Thymeleaf**를 사용하여 주문 내역, 타코 구성 등을 동적으로 렌더링.
- 💳 카드 번호 입력 폼과 유효성 검증을 추가하여 실습.
- 📍 **localhost:9091**에서 주문 확인 및 관리.

### 4️⃣ 메시징 시스템 연동
- 📩 ActiveMQ를 활용한 주문 데이터 메시지 송신.
- 📨 Kafka를 통해 주문 메시지를 소비하고 처리하는 기능 추가.

---

## 🔧 **개발 과정**

### 1️⃣ Spring Boot 프로젝트 생성
Spring Initializr를 통해 **Spring Boot 기반의 프로젝트**를 생성하였습니다. 주요 의존성은 다음과 같습니다:
- **Spring Web**
- **Spring Security**
- **Spring Data JPA**
- **H2 Database**
- **Thymeleaf**
- **Spring Boot Starter AMQP**
- **Spring Boot Starter Kafka**

---

### 2️⃣ 주요 컨트롤러 구현
#### 🧑‍💻 **UserController**
- 사용자 등록 및 로그인 처리.
- `/register` 경로에서 사용자 정보를 입력받아 저장.

#### 🌮 **TacoController**
- `/tacos` 경로에서 타코 구성 페이지 제공.
- 사용자 선택에 따라 타코를 구성하여 주문 데이터로 저장.

#### 📦 **OrderController**
- `/orders` 경로에서 사용자 주문 내역 조회.
- 주문 데이터 유효성 검증 후 저장.

---

### 3️⃣ 메시징 시스템 연동
#### ✉️ **ActiveMQ**
- 주문 생성 시 **ActiveMQ**를 사용해 메시지를 송신.
- 메시지는 큐(Queue)에 저장되며, 주문 처리를 담당하는 Consumer가 이를 소비.

#### 📡 **Kafka**
- Kafka 브로커를 설정하고, **주문 처리 상태**를 소비하는 Consumer를 작성.
- 주문 생성 → Kafka 메시지 송신 → 처리 상태 업데이트의 흐름 학습.

---

### 4️⃣ UI와 프론트엔드 연동
- 🌐 **localhost:9091**에서 타코 주문을 확인하고 관리.
- 📝 사용자 입력폼:
  - 사용자 정보: 이름, 이메일, 주소.
  - 주문 데이터: 타코 구성, 수량.
  - 카드 번호 입력 및 유효성 검증.
- 🌍 **localhost:4200**에서 React 기반의 프론트엔드와 연동 실습.

---

## 🚀 **기술 스택**
- **Backend**: Spring Boot, Spring Data JPA, Spring Security
- **Frontend**: Thymeleaf, HTML, CSS
- **Database**: H2 Database
- **Messaging**: ActiveMQ, Apache Kafka
- **Build Tool**: Maven
- **Version Control**: Git & GitHub

---

## 🌟 **프로젝트 결과 및 성과**
1. 🛠️ **Spring MVC와 Security**를 활용한 사용자 인증 및 권한 관리 구현.
2. 🌐 REST API와 프론트엔드 연동을 통한 데이터 처리 및 UI 개발.
3. 💬 ActiveMQ 및 Kafka를 활용한 메시징 기능 구현 및 테스트.
4. 🔗 클라이언트-서버 간 데이터 통신 구조 이해와 실습.

---

## 📘 **배운 점**
- 🔐 **Spring Security**를 활용하여 인증 및 권한 관리 로직을 구현하는 법을 익혔습니다.
- 🌐 **REST API**와 **프론트엔드 연동**을 통해 클라이언트와 서버 간의 데이터 흐름을 학습했습니다.
- 🖼️ **Thymeleaf**를 사용하여 동적 UI를 렌더링하는 경험을 통해 백엔드와의 통합 작업을 실습했습니다.
- 💬 **ActiveMQ와 Kafka**를 활용하여 메시징 시스템을 구성하고, 대규모 데이터를 처리하는 로직을 학습했습니다.

---

## ▶️ **실행 방법**
1. **프로젝트 클론**
   ```bash
   git clone https://github.com/KimuJinsu/taco-cloud
   cd taco-cloud
   ```

2. **의존성 설치**
   ```bash
   mvn clean install
   ```

3. **ActiveMQ 및 Kafka 실행**
   - ActiveMQ 실행: `/bin/activemq start`
   - Kafka 실행: `/bin/kafka-server-start.sh config/server.properties`

4. **애플리케이션 실행**
   ```bash
   mvn spring-boot:run
   ```

5. **웹 애플리케이션 접속**
   - 사용자 UI: [http://localhost:9091](http://localhost:9091)
