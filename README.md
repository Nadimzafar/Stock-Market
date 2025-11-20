Here is your content converted into **clean, well-structured Markdown**:

---

# **Stock Market Application**

## **Overview**

The **Stock Market Application** is a two-module system built using **Spring Boot**, **Thymeleaf**, and **MySQL**, supporting both **Admin** and **User** roles.

### **Admin Features**

* Log in using credentials stored in the *application.properties* file
* Add stocks by entering a stock ticker

  * Fetches stock details from the **Alpha Vantage API**
* Manage stocks and view:

  * Total transactions (buy & sell)
  * Platform fees collected

### **User Features**

* Register with **OTP email verification** using Java Mail Sender
* Log in after successful verification
* Recharge wallet using **Razorpay API**
* Purchase available stocks
* View and manage portfolio (buy/sell stocks)

The application uses custom session management instead of Spring Security.

---

## **Technologies Used**

### **Backend**

* Spring Boot
* Spring Data JPA

### **Frontend**

* Thymeleaf
* HTML, CSS

### **Database**

* MySQL

### **APIs**

* **Alpha Vantage API** – fetch stock data
* **Razorpay API** – wallet recharge
* **Java Mail Sender** – OTP verification

---

## **Features**

### **Admin Features**

* **Login:** Credentials stored in `application.properties`
* **Add Stock:**

  * Enter ticker symbol
  * Fetches stock details using RestTemplate
  * Saves details to MySQL
* **Manage Stocks:**

  * View all transactions
  * Track platform fee

### **User Features**

* **Registration:** With OTP verification
* **Login**
* **Wallet Recharge:** Using Razorpay API
* **Buy Stocks:** If wallet balance is sufficient
* **Portfolio:** View and sell owned stocks

---

## **Installation**

### **Prerequisites**

* Java (JDK 17+)
* Maven
* MySQL
* Razorpay API Key
* Alpha Vantage API Key
* Email API key (for OTP)

### **Steps**

#### 1. **Clone the Repository**

```bash
git clone https://github.com/Nadimzafar/Stock-Market.git
```

#### 2. **Set Up MySQL Database**

Create a new MySQL database and configure credentials in `application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/stock_market
spring.datasource.username=root
spring.datasource.password=password
```

#### 3. **Configure External APIs**

Add your keys to `application.properties`:

* Alpha Vantage API Key
* Razorpay API Key

#### 4. **Run the Application**

```bash
mvn spring-boot:run
```

#### 5. **Access the Application**

Open:

```
http://localhost
```

---

## **Database Schema**

Key tables:

* **users** – Email, password, wallet balance
* **stocks** – Ticker and stock information
* **transactions** – Records of buy/sell operations
* **admin_details** – Platform fee details

---

## **API Integration**

### **Alpha Vantage API**

Used to fetch stock details (price, company info, etc.) based on the ticker provided by admin.

### **Razorpay API**

Handles wallet recharge for users.

### **Java Mail Sender**

Used for sending OTP emails during user registration.

---

## **Session Management**

Custom session handling instead of Spring Security:

* Session created on user login
* Admin and User sessions are handled separately
* Ensures proper access control

---

## **Contributing**

Feel free to fork the repository, submit issues, or open pull requests.
**Contributions are welcome!**

