# Google Play Console - Camera Permission Declaration

## Version Information
- App Version: 1.0.1 (version code: 2)
- Target SDK: 35 (Android 15)
- Min SDK: 24 (Android 7.0)
- Compile SDK: 35

## Lý do sử dụng quyền Camera (CAMERA permission)

App sử dụng quyền camera cho các mục đích sau:

### 1. QR Code Scanning (Quét mã QR)
- Sử dụng plugin: `mobile_scanner: ^7.0.1`
- Mục đích: Quét QR code để kết nối thiết bị IoT
- Loại sử dụng: **Camera access for QR code scanning**

### 2. Image Picking (Chọn ảnh)
- Sử dụng plugin: `image_picker: ^1.0.4`
- Mục đích: Chụp ảnh để upload avatar hoặc ảnh thiết bị
- Loại sử dụng: **Camera access for image capture**

## Khi submit lên Google Play Console:

1. **Trong phần "App content" > "Sensitive app permissions"**
2. **Chọn "Camera"**
3. **Khai báo sử dụng cho:**
   - ✅ QR code scanning
   - ✅ Image capture (for profile/device photos)
4. **KHÔNG chọn:**
   - ❌ Video recording
   - ❌ Real-time photo effects
   - ❌ Augmented reality features

## Privacy Policy cần bao gồm:

```
Our app uses camera permission for:
- Scanning QR codes to connect IoT devices
- Taking photos for user profile and device images
We do not store or share camera data with third parties.
```

## Lưu ý quan trọng:
- Camera feature đã được đánh dấu `android:required="false"` để app vẫn hoạt động trên thiết bị không có camera
- App sẽ kiểm tra quyền camera trước khi sử dụng
- Người dùng có thể từ chối quyền camera và vẫn sử dụng app bình thường (chỉ mất tính năng quét QR và chụp ảnh)
