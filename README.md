# 🍽️ Meals - Recipe Discovery App

Một ứng dụng Flutter hiện đại để khám phá, tìm kiếm và quản lý các công thức nấu ăn yêu thích của bạn.

## ✨ Tính Năng Chính

### 📂 **Danh Mục Công Thức**
- 10 danh mục khác nhau: Italian, Quick & Easy, Hamburgers, German, Light & Lovely, Exotic, Breakfast, Asian, French, Summer
- Giao diện lưới đẹp mắt với gradient màu sắc
- Hoạt ảnh slide mượt mà khi tải trang

### 🔍 **Danh Sách Công Thức**
- Hiển thị danh sách công thức theo danh mục
- Thông tin chi tiết:
  - Hình ảnh với hiệu ứng fade-in
  - Tên công thức
  - Thời gian nấu (phút)
  - Độ phức tạp (Simple, Challenging, Hard)
  - Mức giá (Affordable, Pricey, Luxurious)

### 📖 **Chi Tiết Công Thức**
- Hình ảnh lớn với hiệu ứng Hero transition
- Danh sách nguyên liệu đầy đủ
- Hướng dẫn từng bước nấu ăn chi tiết
- Thông tin về tính chất đặc biệt:
  - 🌾 Không chứa gluten
  - 🥛 Không chứa lactose
  - 🥬 Chay (Vegetarian)
  - 🌱 Chay hoàn toàn (Vegan)

### ⭐ **Yêu Thích (Favorites)**
- Thêm/xóa công thức yêu thích
- Xem danh sách các công thức yêu thích
- Biểu tượng sao với hoạt ảnh xoay mượt mà
- Thông báo xác nhận hành động

### 🔧 **Bộ Lọc (Filters)**
Lọc công thức theo 4 tiêu chí:
- 🌾 **Gluten-free** - Không chứa gluten
- 🥛 **Lactose-free** - Không chứa lactose
- 🥬 **Vegetarian** - Chay
- 🌱 **Vegan** - Chay hoàn toàn

Giao diện toggle switch dễ sử dụng, kết hợp các bộ lọc theo nhu cầu.

### 🧭 **Điều Hướng**
- Bottom Navigation Bar giữa Categories và Favorites
- Drawer menu bên trái với các tùy chọn
- Deep linking hỗ trợ

## 🛠️ Công Nghệ & Stack

### Framework & Language
- **Framework**: [Flutter](https://flutter.dev/) (Dart)
- **Dart Version**: 3.0+

### State Management
- **Riverpod** - Modern state management solution
  - `FavoriteMealsNotifier` - Quản lý danh sách yêu thích
  - `FiltersNotifier` - Quản lý trạng thái bộ lọc
  - `filterMealsProvider` - Lọc công thức theo điều kiện

### UI & Design
- **Material Design 3** - Modern Material Design
- **Google Fonts** - Lato font family
- **Animated Transitions**:
  - SlideTransition
  - FadeInImage
  - Hero Animation
  - RotationTransition
- **Transparent Image** - Placeholder cho images

### Architecture
```
lib/
├── main.dart                 # Entry point
├── screens/                  # Các màn hình chính
│   ├── tabs.dart            # Tab navigation
│   ├── categories.dart       # Danh mục
│   ├── meals.dart           # Danh sách công thức
│   ├── meal_details.dart    # Chi tiết công thức
│   └── filters.dart         # Bộ lọc
├── models/                   # Data models
│   ├── meal.dart
│   └── category.dart
├── providers/               # Riverpod providers
│   ├── meals_provider.dart
│   ├── favorities_provider.dart
│   └── filters_provider.dart
├── widgets/                 # Widgets tái sử dụng
│   ├── meal_item.dart
│   ├── meal_item_trait.dart
│   ├── category_grid_item.dart
│   └── main_drawer.dart
└── data/                    # Dữ liệu tĩnh
    └── dummy_data.dart
```

## 📱 Hỗ Trợ Platform

- ✅ **Android** (5.0+)
- ✅ **iOS** (11.0+)
- ✅ **Windows** (10+)
- ✅ **macOS** (10.11+)
- ✅ **Linux** (Ubuntu 17.04+)
- ✅ **Web** (Chrome, Firefox, Safari, Edge)

## 🚀 Cài Đặt & Chạy

### Yêu Cầu
- Flutter SDK: 3.13.0 hoặc cao hơn
- Dart SDK: 3.0.0 hoặc cao hơn
- Android SDK (cho Android)
- Xcode (cho iOS/macOS)

### Hướng Dẫn Cài Đặt

1. **Clone Repository**
```bash
git clone https://github.com/luongductinh-it/meals.git
cd meals
```

2. **Cài Đặt Dependencies**
```bash
flutter pub get
```

3. **Chạy Ứng Dụng**

Trên Android:
```bash
flutter run -d android
```

Trên iOS:
```bash
flutter run -d ios
```

Trên Web:
```bash
flutter run -d chrome
```

Trên Windows:
```bash
flutter run -d windows
```

Trên macOS:
```bash
flutter run -d macos
```

Trên Linux:
```bash
flutter run -d linux
```

4. **Build Release** (Tùy chọn)
```bash
flutter build apk      # Android APK
flutter build ios      # iOS app
flutter build web      # Web version
flutter build windows  # Windows executable
flutter build macos    # macOS app
flutter build linux    # Linux executable
```

## 📋 Cấu Trúc Dữ Liệu

### Meal Model
```dart
class Meal {
  final String id;
  final List<String> categories;
  final String title;
  final String imageUrl;
  final List<String> ingredients;
  final List<String> steps;
  final int duration;
  final Complexity complexity;      // simple, challenging, hard
  final Affordability affordability; // affordable, pricey, luxurious
  final bool isGlutenFree;
  final bool isLactoseFree;
  final bool isVegan;
  final bool isVegetarian;
}
```

### Category Model
```dart
class Category {
  final String id;
  final String title;
  final Color color;
}
```

## 🎨 Theme & Styling

- **Color Scheme**: Dark theme với seed color `#833900` (brown)
- **Typography**: Google Fonts - Lato
- **Brightness**: Dark mode
- **Material 3**: Enabled

## 📊 State Management Flow

```
User Action (Select Meal/Filter)
        ↓
Provider Updated
        ↓
UI Rebuilds (ConsumerWidget)
        ↓
Display New Content
```

### Providers:

1. **mealsProvider** - Cung cấp danh sách tất cả công thức
2. **filtersProvider** - Quản lý trạng thái bộ lọc
3. **filterMealsProvider** - Tính toán công thức đã lọc
4. **favoriteMealsProvider** - Quản lý danh sách yêu thích

## 🔄 Luồng Ứng Dụng

```
App Entry
├── TabsScreen (Main Navigation)
│   ├── CategoriesScreen
│   │   └── MealsScreen
│   │       └── MealDetailsScreen ⭐ (Can add to favorites)
│   └── MealsScreen (Favorites)
├── FiltersScreen (Side Menu)
│   └── CategoriesScreen (Auto filter)
└── MainDrawer
    ├── Meals (Back to Categories)
    └── Filters (Open Filter Screen)
```

## 🎯 Các Tính Năng Nâng Cao

- **Persistent Favorites**: Yêu thích được lưu (với state management)
- **Multiple Filters**: Kết hợp nhiều bộ lọc
- **Smooth Animations**: Transition mượt mà giữa các màn hình
- **Image Loading**: Fade-in effect với placeholder
- **Responsive Design**: Thích ứng trên tất cả kích thước màn hình
- **Dark Mode**: Tối ưu cho dark theme

## 📸 Dữ Liệu Mẫu

Ứng dụng bao gồm 10 công thức mẫu:
1. Spaghetti with Tomato Sauce
2. Toast Hawaii
3. Classic Hamburger
4. Wiener Schnitzel
5. Salad with Smoked Salmon
6. Delicious Orange Mousse
7. Pancakes
8. Creamy Indian Chicken Curry
9. Chocolate Souffle
10. Asparagus Salad with Cherry Tomatoes

## 🐛 Troubleshooting

### Lỗi Build
```bash
# Clean project
flutter clean

# Get dependencies again
flutter pub get

# Rebuild
flutter run
```

### Lỗi trên iOS
```bash
cd ios
pod install
cd ..
flutter run
```

### Lỗi trên Web
```bash
flutter clean
flutter pub get
flutter run -d chrome
```

## 📝 Ghi Chú

- Dữ liệu công thức được lưu trong file `dummy_data.dart`
- Yêu thích được quản lý bằng Riverpod state
- Bộ lọc được lưu trong state provider
- Ứng dụng không sử dụng database ngoài (dùng in-memory storage)

## 🚀 Cải Tiến Tương Lai

- [ ] Lưu yêu thích vào local database (Hive/Sqflite)
- [ ] Thêm tìm kiếm công thức
- [ ] Tính năng panning công thức
- [ ] Đơn vị đo lường tùy chỉnh
- [ ] Tích hợp nutrition info
- [ ] Share công thức
- [ ] Đánh giá & bình luận

## 📄 License

MIT License - Xem file LICENSE để biết chi tiết

## 👤 Tác Giả

**Luong Duc Tinh**
- GitHub: [@luongductinh-it](https://github.com/luongductinh-it)

## 📞 Liên Hệ & Hỗ Trợ

Nếu bạn có câu hỏi hoặc gặp lỗi, vui lòng:
- Tạo Issue trên GitHub
- Liên hệ qua email

---

**Happy Cooking! 🍳** 👨‍🍳