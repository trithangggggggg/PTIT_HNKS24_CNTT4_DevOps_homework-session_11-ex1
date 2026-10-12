# Bài 1: Khởi tạo Workflow chạy Unit Test tự động cho Java Spring Boot với Gradle

## Mục tiêu
- Khởi tạo tệp kịch bản GitHub Actions Workflow cho dự án Java Spring Boot sử dụng Gradle.
- Cấu hình môi trường Java JDK 17 (Temurin) và tự động chạy bài kiểm thử JUnit Test bằng Gradle Wrapper (`./gradlew test`).

## Cấu trúc thư mục
```
bai1/
├── .github/
│   └── workflows/
│       └── ci.yml
├── gradle/
│   └── wrapper/
├── src/
│   ├── main/java/...
│   └── test/java/...
├── build.gradle
├── gradlew
├── gradlew.bat
├── settings.gradle
└── README.md
```

## Workflow CI (`.github/workflows/ci.yml`)
Workflow được kích hoạt khi có sự kiện push vào nhánh `main`:
1. **Checkout mã nguồn**: Sử dụng `actions/checkout@v5`.
2. **Thiết lập Java JDK 17**: Sử dụng `actions/setup-java@v5` với distribution `temurin`.
3. **Cấp quyền thực thi**: Chạy `chmod +x gradlew`.
4. **Thực thi JUnit Test**: Chạy `./gradlew test`.
