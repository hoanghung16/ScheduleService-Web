# Schedule Service Web

ASP.NET Core 8 MVC cho ứng dụng đặt lịch và quản lý dịch vụ tại gia

## 🎯 Tính Năng

- ✅ Giao diện đặt lịch
- ✅ Quản lý hồ sơ khách hàng
- ✅ Xem danh sách dịch vụ
- ✅ Quản lý lịch hẹn
- ✅ Đánh giá & bình luận

## 🔧 Tech Stack

- **Framework**: ASP.NET Core 8 MVC
- **Frontend**: HTML5, CSS3, JavaScript
- **API Communication**: HttpClient
- **Architecture**: MVC Pattern

## 📋 Requirements

- .NET 8.0 SDK
- Visual Studio 2022 / VS Code
- Backend API (ScheduleService-API) running

## 🚀 Setup & Run

### 1. Clone Repository
```bash
git clone https://github.com/hoanghung16/ScheduleService-Web.git
cd ScheduleService-Web/ScheduleService.Web
```

### 2. Restore NuGet Packages
```bash
dotnet restore
```

### 3. Configure API Base URL

Cập nhật `appsettings.json`:
```json
{
  "ApiSettings": {
    "ApiBaseUrl": "https://localhost:5001/api"
  }
}
```

### 4. Run Web Application
```bash
dotnet run
```

Web sẽ chạy tại: `https://localhost:5002` (hoặc cổng khác)

## 📁 Project Structure

```
ScheduleService.Web/
├── Controllers/         (MVC Controllers)
├── Models/             (View Models)
├── Views/              (Razor Views)
│   ├── Home/
│   ├── Services/
│   ├── Bookings/
│   └── Shared/
├── wwwroot/            (Static Files)
│   ├── css/
│   ├── js/
│   └── images/
├── Program.cs          (Startup Configuration)
├── appsettings.json    (Configuration)
└── ScheduleService.Web.csproj
```

## 🎨 Pages

- **/Home** - Trang chủ
- **/Services** - Danh sách dịch vụ
- **/Bookings** - Quản lý lịch hẹn
- **/Account** - Quản lý tài khoản
- **/Admin** - Trang quản lý (nếu Admin)

## 🔗 API Integration

Gọi Backend API qua HttpClient:
```csharp
public class ServiceClient
{
    private readonly HttpClient _httpClient;
    
    public async Task<List<ServiceDto>> GetServicesAsync()
    {
        var response = await _httpClient.GetAsync($"{baseUrl}/services");
        return await response.Content.ReadAsAsync<List<ServiceDto>>();
    }
}
```

## 📝 Environment Variables

Tạo file `appsettings.Development.json`:
```json
{
  "ApiSettings": {
    "ApiBaseUrl": "https://localhost:5001/api"
  },
  "ConnectionStrings": {
    "DefaultConnection": "Data Source=HoangHung;Initial Catalog=doanthuctapDB;Integrated Security=True;Encrypt=False"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Debug",
      "Microsoft": "Information"
    }
  }
}
```

## 🤝 Contributing

1. Fork repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 📄 License

This project is licensed under the MIT License.

## 📧 Contact

- Email: weew3426@gmail.com
- GitHub: [@hoanghung16](https://github.com/hoanghung16)

## 🔗 Related Repositories

- **Backend API**: [ScheduleService-API](https://github.com/hoanghung16/ScheduleService-API)
