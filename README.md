# Qeydiyyat və Tapşırıq İdarəetmə Sistemi (Task Management System)

Bu layihə, istifadəçilərin qeydiyyatdan keçə biləcəyi, tapşırıqlar əlavə edə biləcəyi və tapşırıqlarını idarə edə biləcəyi sadə bir API təqdim edir. API, Django və Django Rest Framework istifadə edilərək hazırlanmışdır.

## API Endpoints

Bu layihə aşağıdakı API endpoindtlərini təqdim edir:

### 1. **İstifadəçi qeydiyyatı və daxil olması (Authentication)**

- **POST** `/api/token/`
  
  İstifadəçinin daxil olması və token alması üçün.

  **Request Body**:
  ```json
  {
    "username": "your_username",
    "password": "your_password"
  }

### 2. **Tapşırıqların yaradılması (Create Task)**

- **POST** `/api/tasks/`
  
  Yeni tapşırıq yaratmaq.

  **Request Body**:
  ```json
  {
    "title": "Tapşırıq başlığı",
    "description": "Tapşırıq haqqında ətraflı məlumat",
    "status": "pending"  
  }

- **Response**:
  ```json
  {
    "id": 1,
    "title": "Tapşırıq başlığı",
    "description": "Tapşırıq haqqında ətraflı məlumat",
    "status": "pending"
  }

### 3. **Tapşırıqları əldə etmək (Get Tasks)**

- **GET** `/api/tasks/`
  
  Bütün tapşırıqları əldə etmək.

  **Response**:
  ```json
  {
    [
  {
    "id": 1,
    "title": "Tapşırıq başlığı",
    "description": "Tapşırıq haqqında ətraflı məlumat",
    "status": "pending"
  },
  {
    "id": 2,
    "title": "Digər tapşırıq",
    "description": "Ətraflı məlumat",
    "status": "completed"
  }
]
 }

 ### 4. **Tapşırıq əldə etmək (Get Task by ID)**

- **GET** `/api/tasks/{id}/`
  
  Müəyyən bir tapşırığı əldə etmək.

  **Response**:
  ```json
  {
  "id": 1,
  "title": "Tapşırıq başlığı",
  "description": "Tapşırıq haqqında ətraflı məlumat",
  "status": "pending"
  }

 ### 5. **Tapşırığı yeniləmək (Update Task)**

- **PUT** `/api/tasks/{id}/`
  
  Mövcud tapşırığı yeniləmək.

  **Request**:
  ```json
  {
  "title": "Yeni başlıq",
  "description": "Yenilənmiş məlumat",
  "status": "completed"
  }

**Response**:
  ```json
  {
  "id": 1,
  "title": "Yeni başlıq",
  "description": "Yenilənmiş məlumat",
  "status": "completed"
  }
