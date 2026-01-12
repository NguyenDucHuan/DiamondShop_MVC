# 💎 DiamondShop MVC

A diamond shop management system built with ASP.NET MVC using Layered Architecture pattern.

## 📋 Table of Contents

- [Introduction](#introduction)
- [Technologies](#technologies)
- [System Architecture](#system-architecture)
- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Database Configuration](#database-configuration)
- [Project Structure](#project-structure)
- [Features](#features)
- [Usage Guide](#usage-guide)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [Author](#author)

## 🎯 Introduction

DiamondShop MVC is a web application for managing a diamond shop, allowing management of products, orders, customers, and other functions related to diamond business operations.

The project is developed following the **Layered Architecture** pattern with the following layers:
- **Presentation Layer** (MVC)
- **Business Logic Layer** (Services)
- **Data Access Layer** (Repositories & DAOs)
- **Data Model Layer** (Business Objects)

## 🛠 Technologies

### Backend
- **Framework**: ASP.NET MVC 5
- **Language**: C# (. NET Framework)
- **ORM**: Entity Framework
- **Database**: SQL Server

### Frontend
- **HTML5, CSS3, JavaScript**
- **Bootstrap** - Responsive UI Framework
- **jQuery** - JavaScript Library

### Other Libraries
- **Newtonsoft.Json** - JSON serialization
- **Microsoft.AspNet.Mvc** - MVC Framework
- **EntityFramework** - ORM

## 🏗 System Architecture

```
DiamondShop_MVC/
│
├── ProjectDiamondShop/          # Presentation Layer (MVC)
│   ├── Controllers/             # MVC Controllers
│   ├── Views/                   # Razor Views
│   ├── Models/                  # View Models
│   ├── Content/                 # CSS, Images
│   ├── Scripts/                 # JavaScript files
│   └── App_Start/               # Configuration
│
├── DiamondShopServices/         # Business Logic Layer
│   └── Service classes          # Business logic implementation
│
├── DiamondShopRepositories/     # Data Access Layer
│   └── Repository classes       # Data access logic
│
├── DiamondShopDAOs/            # Data Access Objects
│   └── DAO classes             # Direct database operations
│
├── DiamondShopBOs/             # Business Objects
│   └── Entity classes          # Domain models
│
└── SQL Scripts/
    ├── DiamondShop.sql         # Database schema
    └── DiamondShop_New.sql     # Updated schema
```

## 💻 System Requirements

- **Visual Studio 2019/2022** or higher
- **.NET Framework 4.7.2** or higher
- **SQL Server 2016** or higher
- **IIS Express** (included with Visual Studio)
- **Web Browser**:  Chrome, Firefox, Edge (latest versions)

## 📦 Installation

### Step 1: Clone the repository

```bash
git clone https://github.com/NguyenDucHuan/DiamondShop_MVC.git
cd DiamondShop_MVC
```

### Step 2: Open the solution

1. Open Visual Studio
2. File → Open → Project/Solution
3. Select the `SWP391. sln` file

### Step 3: Restore NuGet Packages

```
Tools → NuGet Package Manager → Manage NuGet Packages for Solution
→ Click "Restore" button
```

Or use Package Manager Console:

```powershell
Update-Package -Reinstall
```

## 🗄 Database Configuration

### Create Database

1. Open **SQL Server Management Studio (SSMS)**
2. Connect to your SQL Server instance
3. Execute the database creation script:

```sql
-- Select and execute the DiamondShop_New.sql file (F5)
```

### Update Connection String

Open the `Web.config` file in the **ProjectDiamondShop** project and update the connection string: 

```xml
<connectionStrings>
  <add name="DiamondShopContext" 
       connectionString="Data Source=YOUR_SERVER_NAME;Initial Catalog=DiamondShop;Integrated Security=True" 
       providerName="System.Data.SqlClient" />
</connectionStrings>
```

Replace `YOUR_SERVER_NAME` with your SQL Server name (e.g., `localhost` or `.` or `(localdb)\MSSQLLocalDB`)

### Migration (if using Entity Framework Code First)

```powershell
# In Package Manager Console
Enable-Migrations
Add-Migration InitialCreate
Update-Database
```

## 📁 Project Structure

```
ProjectDiamondShop/
│
├── Controllers/
│   ├── HomeController.cs
│   ├── ProductController.cs
│   ├── OrderController.cs
│   ├── CustomerController.cs
│   └── AdminController.cs
│
├── Views/
│   ├── Home/
│   ├── Product/
│   ├── Order/
│   ├── Customer/
│   ├── Admin/
│   └── Shared/
│       ├── _Layout.cshtml
│       └── Error.cshtml
│
├── Models/
│   └── ViewModels/
│
├── Content/
│   ├── css/
│   └── images/
│
├── Scripts/
│   └── JavaScript files
│
└── App_Start/
    ├── RouteConfig.cs
    ├── BundleConfig.cs
    └── FilterConfig.cs
```

## ✨ Features

### Customer Features
- ✅ Browse diamond products
- ✅ Search and filter products
- ✅ View product details
- ✅ Add products to shopping cart
- ✅ Place orders and checkout
- ✅ View order history
- ✅ Manage personal information

### Admin Features
- ✅ Product management (CRUD)
- ✅ Category management
- ✅ Order management
- ✅ Customer management
- ✅ Reports and statistics
- ✅ Inventory management
- ✅ User management and role assignment

## 🚀 Usage Guide

### Running the Application

1. In Visual Studio, press `F5` or click **Debug → Start Debugging**
2. Your browser will automatically open at:  `https://localhost:PORT`

### Login Credentials

**Default Admin Account:**
- Username: `admin`
- Password: `admin123`

**Default Customer Account:**
- Username: `customer`
- Password: `customer123`

> ⚠️ **Note**: Please change the default passwords after first login

### Main Functions

#### 1. Product Management
- Access:  Admin Dashboard → Products
- Add New:  Click "Add New Product"
- Edit: Click "Edit" icon on each product
- Delete: Click "Delete" icon

#### 2. Order Management
- Access: Admin Dashboard → Orders
- View order details
- Update order status

#### 3. Shopping (Customer)
- Browse products from homepage
- Click "Add to Cart"
- Go to cart and adjust quantities
- Click "Checkout" to complete purchase

## 📸 Screenshots

_Add application screenshots here_

```
// Add images to Images/ folder and link them here
![Home Page](ProjectDiamondShop/Images/homepage.png)
![Product List](ProjectDiamondShop/Images/products.png)
![Admin Dashboard](ProjectDiamondShop/Images/admin-dashboard.png)
```

## 🧪 Testing

### Unit Tests
```bash
# Run all unit tests
dotnet test
```

### Integration Tests
```bash
# Run integration tests
dotnet test --filter Category=Integration
```

## 🔧 Troubleshooting

### Database Connection Error
```
Error: Cannot open database "DiamondShop" requested by the login
```
**Solution**: Check the connection string in Web.config and ensure the database has been created

### NuGet Packages Error
```
Error: Could not find package
```
**Solution**: Restore packages
```powershell
Update-Package -Reinstall
```

### Build Error
```
Error: The type or namespace name could not be found
```
**Solution**: Clean and rebuild solution
```
Build → Clean Solution
Build → Rebuild Solution
```

## 🤝 Contributing

All contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Contributing Guidelines
- Write clear, understandable code
- Follow C# coding conventions
- Add comments for complex code sections
- Write unit tests for new features
- Update documentation when necessary

## 📝 License

This project is distributed under the MIT License.  See the [LICENSE](LICENSE) file for more details.

## 👥 Author

**Nguyen Duc Huan** - [@NguyenDucHuan](https://github.com/NguyenDucHuan)

## 📞 Contact

- GitHub: [@NguyenDucHuan](https://github.com/NguyenDucHuan)
- Email: your.email@example.com
- Project Link: [https://github.com/NguyenDucHuan/DiamondShop_MVC](https://github.com/NguyenDucHuan/DiamondShop_MVC)

## 🙏 Acknowledgments

- Thanks to all open-source libraries used in this project
- Thanks to the ASP.NET MVC community
- Bootstrap and jQuery teams

---

⭐️ If you find this project useful, please give it a star! 

Made with ❤️ by [NguyenDucHuan](https://github.com/NguyenDucHuan)
