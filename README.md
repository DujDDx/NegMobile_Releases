# NegMobile - 负片转正专家

一个功能强大的 iOS 应用，用于将胶片负片转换为正片，并提供完整的图集管理功能。

## 📱 功能特性

### 核心功能
- ✅ **负片转正处理**：使用先进的算法将负片转换为正片
- ✅ **多格式支持**：支持 JPEG、PNG、HEIC、DNG、TIFF、TIF 等格式
- ✅ **参数调整**：Mask 强度、白平衡、对比度实时调整
- ✅ **批量处理**：一次处理多张图片，提高效率

### 图集管理（新功能）
- ✅ **图集创建**：创建多个图集，分类管理照片
- ✅ **照片保存**：处理后的照片保存到图集，而不是直接导出
- ✅ **图集浏览**：网格布局查看图集和照片
- ✅ **灵活导出**：按需将照片从图集导出到系统相册
- ✅ **批量操作**：批量导出、批量删除

### 用户界面
- ✅ **TabView 结构**：导入和相册两个选项卡，清晰分离功能
- ✅ **直观操作**：长按菜单、上下文菜单等现代 iOS 交互
- ✅ **空状态引导**：友好的提示和引导，提升用户体验
- ✅ **实时预览**：处理过程中的动画效果
- ✅ **设置界面**：应用设置管理

### 设置功能
- ✅ **应用配置**：管理应用级别的设置
- ✅ **用户偏好**：保存用户的操作偏好

## 🚀 快速开始

### 1. 打开项目

```bash
# 打开项目
cd /Users/yichen/Documents/NegMobile
open NegMobile.xcodeproj
```

### 2. 构建并运行

```bash
# 方法 1：在 Xcode 中
# 按 Cmd + B 构建
# 按 Cmd + R 运行

# 方法 2：使用命令行
xcodebuild -project NegMobile.xcodeproj -scheme NegMobile -destination 'platform=iOS Simulator,id=3D86CA03-187D-404A-A902-B10C5032DC65' build
```

### 3. 项目状态

✅ **所有文件已添加到 Xcode 项目**
✅ **项目已成功编译**
✅ **所有功能已实现**
✅ **架构重构已完成**

## 📖 文档

- **[QUICK_START.md](QUICK_START.md)** - 快速开始指南（5分钟上手）
- **[SETUP_GUIDE.md](SETUP_GUIDE.md)** - 详细设置指南（完整步骤）
- **[IMPLEMENTATION_SUMMARY.md](IMPLEMENTATION_SUMMARY.md)** - 实现总结（技术细节）

## 📁 项目结构

```
NegMobile/
├── App/
│   └── NegMobileApp.swift         # 应用入口
├── Core/
│   ├── Permissions/
│   │   └── PhotoPermissionService.swift  # 照片权限服务
│   └── Settings/
│       └── AppSettings.swift             # 应用设置
├── Data/
│   ├── Repository/
│   │   └── LocalAlbumRepository.swift    # 本地相册仓库
│   └── Storage/
│       └── LocalImageStorage.swift       # 本地图片存储
├── Domain/
│   ├── Entities/
│   │   ├── Album.swift                   # 相册实体
│   │   ├── NegativeImage.swift           # 负片图像实体
│   │   └── Photo.swift                   # 照片实体
│   ├── Protocols/
│   │   ├── AlbumRepository.swift         # 相册仓库协议
│   │   ├── ImageStorage.swift            # 图片存储协议
│   │   └── NegativeEngine.swift          # 引擎协议
│   └── UseCases/
│       ├── LoadAlbumsUseCase.swift       # 加载相册用例
│       ├── ProcessBatchImagesUseCase.swift  # 批量处理用例
│       ├── ProcessSingleImageUseCase.swift  # 单图处理用例
│       └── SaveImagesToAlbumUseCase.swift  # 保存图片到相册用例
├── Features/
│   ├── Editor/
│   │   ├── DebugLogView.swift            # 调试日志视图
│   │   ├── DebugStepOverlay.swift        # 调试步骤覆盖
│   │   ├── EditorAnimationController.swift  # 编辑器动画控制器
│   │   ├── EditorView.swift              # 编辑器视图
│   │   ├── EditorViewModel.swift         # 编辑器视图模型
│   │   └── FrameDetectionOverlay.swift   # 帧检测覆盖
│   ├── Home/
│   │   ├── HomeView.swift                # 首页视图
│   │   └── HomeViewModel.swift           # 首页视图模型
│   ├── Library/
│   │   ├── AlbumListView.swift           # 相册列表视图
│   │   ├── AlbumSelectionView.swift      # 相册选择视图
│   │   └── LibraryViewModel.swift        # 库视图模型
│   └── Settings/
│       ├── SettingsView.swift            # 设置视图
│       └── SettingsViewModel.swift       # 设置视图模型
├── ImageProcessing/
│   └── NEG/
│       ├── NEGEngineAdapter.swift        # 引擎适配器
│       ├── NEGEngineError.swift          # 引擎错误
│       ├── NEGFrame.h                    # 帧头文件
│       └── NEGFrame.mm                   # 帧实现
├── UIComponents/
│   ├── DocumentPicker.swift              # 文档选择器
│   ├── HapticManager.swift               # 触觉反馈
│   └── ImagePicker.swift                 # 图片选择器
├── NEGEngine.h                           # 引擎头文件
├── NEGEngine.mm                          # 引擎实现
├── NegMobile-Bridging-Header.h           # Objective-C 桥接头文件
└── README.md                             # 项目文档
```

## 🎯 使用流程

### 基本流程

```
1. 导入图片
   首页 → 导入选项卡 → 选择图片（支持 DNG/TIFF）

2. 处理图片
   编辑器 → 调整参数 → 转换图片

3. 保存到图集
   点击"保存" → 选择图集（或创建新图集）

4. 查看和管理
   首页 → 相册选项卡 → 查看图集

5. 导出到系统相册
   图集详情 → 长按照片 → 导出到相册
```

### 批量处理

```
1. 导入多张图片
2. 点击"批量转换所有图片"
3. 保存到图集
4. 批量导出到系统相册
```

## 🛠️ 技术栈

- **语言**：Swift 5.x, Objective-C++
- **框架**：SwiftUI, UIKit, PhotosUI
- **架构**：MVVM (Model-View-ViewModel) + UseCase + Engine Adapter
- **图像处理**：Core Graphics, Accelerate
- **数据持久化**：Codable + JSON + FileManager
- **并发**：DispatchQueue (GCD)
- **设计模式**：Protocol-Oriented Programming, Dependency Injection
- **导航**：NavigationStack, Coordinator Pattern

## 📊 代码统计

| 文件 | 行数 | 说明 |
|------|------|------|
| Features/Library/AlbumListView.swift | 841 | 相册列表视图 |
| Features/Editor/EditorView.swift | 303 | 编辑器视图 |
| Features/Home/HomeView.swift | 195 | 首页视图 |
| Data/Repository/LocalAlbumRepository.swift | 175 | 本地相册仓库 |
| Features/Editor/EditorViewModel.swift | 161 | 编辑器视图模型 |
| Features/Library/AlbumSelectionView.swift | 153 | 相册选择视图 |
| Data/Storage/LocalImageStorage.swift | 131 | 本地图片存储 |
| Features/Library/LibraryViewModel.swift | 83 | 库视图模型 |
| UIComponents/ImagePicker.swift | 78 | 图片选择器 |
| UIComponents/DocumentPicker.swift | 68 | 文档选择器 |
| Core/Settings/AppSettings.swift | 50 | 应用设置 |
| Features/Settings/SettingsView.swift | 45 | 设置视图 |
| Features/Settings/SettingsViewModel.swift | 30 | 设置视图模型 |
| Domain/UseCases/LoadAlbumsUseCase.swift | 25 | 加载相册用例 |
| Domain/UseCases/SaveImagesToAlbumUseCase.swift | 20 | 保存图片到相册用例 |
| **总计** | **2,650** | **重构后代码** |

## 🎨 界面预览

### 首页（TabView）
- **导入选项卡**：导入单张/多张图片、拍摄负片
- **相册选项卡**：查看和管理图集

### 编辑器
- 图片预览区域
- 参数调整（Mask、WB、Tone）
- 转换按钮（单张/批量）
- 保存按钮（替换原来的导出）

### 图集管理
- 图集列表（2列网格）
- 图集详情（3列网格）
- 长按菜单（导出、删除）

### 设置界面
- 应用配置选项
- 用户偏好设置

## 🔧 配置要求

- **iOS 版本**：iOS 14.0+
- **Xcode 版本**：Xcode 13.0+
- **设备**：iPhone / iPad
- **权限**：相册访问权限

## 📝 更新日志

### v3.0.0 (2026-02-19) - 架构重构

#### 架构改进
- 🏗️ 采用 SwiftUI + MVVM + UseCase + Engine Adapter 架构
- 🏗️ 完全隔离 NEGEngine 与 UI 层
- 🏗️ 实现 Protocol-Oriented Programming 设计模式
- 🏗️ 引入 Dependency Injection 依赖注入
- 🏗️ 采用 NavigationStack 导航系统

#### 目录结构
- 📁 重新组织为功能模块化结构
- 📁 分离 Core、Data、Domain、Features 层
- 📁 集中管理 UIComponents 和 ImageProcessing
- 📁 按功能划分 Features 目录

#### 功能改进
- ✨ 优化图片动画效果，移除额外方框
- ✨ 改进相册封面显示，确保最新照片作为封面
- ✨ 修复相册详情页照片重叠问题
- ✨ 增强错误处理和边界情况处理
- ✨ 提升性能和响应速度
- ✨ 新增设置功能，管理应用配置和用户偏好

#### 技术改进
- 🔧 引擎适配器模式隔离核心逻辑
- 🔧 UseCase 模式封装业务逻辑
- 🔧 Repository 模式管理数据访问
- 🔧 完善的协议定义和接口设计
- 🔧 减少耦合，提高代码可测试性

### v2.0.0 (2026-02-14)

#### 新增功能
- ✨ 支持 DNG、TIFF、TIF 等 RAW 格式
- ✨ 图集管理系统
- ✨ 照片保存到图集
- ✨ 图集详情查看
- ✨ 照片导出到系统相册
- ✨ 批量操作
- ✨ 首页 TabView 结构

#### 改进
- 🎨 重构首页为 TabView 结构
- 🎨 编辑器"导出"改为"保存"
- 🎨 添加空状态引导
- 🎨 优化用户交互体验

#### 技术改进
- 🔧 数据持久化（JSON + FileManager）
- 🔧 图片存储管理
- 🔧 缩略图生成
- 🔧 批量操作优化

## ⚠️ 注意事项

1. **权限**：首次使用需要授予相册访问权限
2. **存储**：照片保存在应用的 Documents 目录
3. **备份**：重要照片建议导出到系统相册备份
4. **架构**：项目采用模块化架构，便于后续扩展和维护
5. **编译**：项目已成功编译，可直接在 Xcode 中运行

## 🐛 已知问题

1. 可能存在的枚举位运算警告（不影响功能）

## 🔮 未来计划

- [ ] 图集重命名功能
- [ ] 图集排序和搜索
- [ ] 照片编辑历史记录
- [ ] iCloud 同步
- [ ] 照片分享功能
- [ ] EXIF 信息显示
- [ ] 高级设置选项
- [ ] 深色模式支持
- [ ] 自定义处理参数预设

## 📄 许可证

Copyright © 2026 Yichen Lu. All rights reserved.

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📧 联系方式

如有问题或建议，请通过以下方式联系：
- 提交 Issue
- 发送邮件

---

**享受使用 NegMobile！** 📸✨
