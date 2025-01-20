# Selenium Login Test Project
# Vũ Quang Dương_22IT1_BIT220290

## Giới thiệu
Dự án này là một bài kiểm thử tự động đăng nhập vào trang web [OrangeHRM Demo](https://opensource-demo.orangehrmlive.com/web/index.php/auth/login) bằng Selenium WebDriver.

## Công nghệ sử dụng
- **Java 22**
- **Selenium WebDriver** (Phiên bản 4.27.0)
- **TestNG** (Phiên bản 7.10.2)
- **JUnit** (Phiên bản 4.13.1)
- **Maven** để quản lý dependencies

## Cấu trúc dự án
```
selenium-login-test
|-- src
|   |-- main
|   |   |-- java
|   |       |-- org.example
|   |           |-- LoginTest.java
|-- pom.xml
|-- README.md
```

## Yêu cầu hệ thống
- Cài đặt **Java 22**
- Cài đặt **Maven**
- Tải và cài đặt trình duyệt Chrome
- Tải ChromeDriver phù hợp với phiên bản trình duyệt Chrome

## Hướng dẫn sử dụng
1. Chạy chương trình để kiểm tra quá trình đăng nhập.
2. Nếu đăng nhập thành công, bạn sẽ thấy thông báo: `Test PASSED: Đăng nhập thành công!`
3. Nếu đăng nhập thất bại, bạn sẽ thấy thông báo: `Test FAILED: Đăng nhập không thành công!`

## Mã nguồn mẫu
**File LoginTest.java**
```java
package org.example;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class LoginTest {
    public static void main(String[] args) {
        WebDriver driver = new ChromeDriver();
        try {
            driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
            WebElement usernameField = driver.findElement(By.id("username"));
            usernameField.sendKeys("admin");
            WebElement passwordField = driver.findElement(By.id("password"));
            passwordField.sendKeys("admin123");
            WebElement loginButton = driver.findElement(By.id("login"));
            loginButton.click();
            
            String expectedUrl = "https://opensource-demo.orangehrmlive.com/web/index.php/dashboard/index";
            if (driver.getCurrentUrl().equals(expectedUrl)) {
                System.out.println("Test PASSED: Đăng nhập thành công!");
            } else {
                System.out.println("Test FAILED: Đăng nhập không thành công!");
            }
        } catch (Exception e) {
            System.out.println("Có lỗi xảy ra: " + e.getMessage());
        } finally {
            driver.quit();
        }
    }
}
```

## Tham khảo
- [Selenium Documentation](https://www.selenium.dev/documentation/)
- [TestNG Documentation](https://testng.org/doc/)
- [JUnit Documentation](https://junit.org/junit4/)

## Tác giả
- Tên: [Your Name]
- Email: [your.email@example.com]

