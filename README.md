# CNM-ZELOO - Ứng Dụng Chat Realtime

<div align="center">
  <h3>📱 Nền tảng nhắn tin và gọi video đa nền tảng</h3>
  <p>Ứng dụng chat realtime với tính năng đầy đủ, hỗ trợ cả Web và Mobile</p>
</div>

---

## 📋 Mục Lục

- [Giới Thiệu](#-giới-thiệu)
- [Tính Năng](#-tính-năng)
- [Công Nghệ](#-công-nghệ)
- [Kiến Trúc Hệ Thống](#-kiến-trúc-hệ-thống)
- [Cài Đặt](#-cài-đặt)
- [Cấu Hình](#-cấu-hình)
- [Sử Dụng](#-sử-dụng)
- [API Documentation](#-api-documentation)
- [Đóng Góp](#-đóng-góp)
- [License](#-license)

---

## 🎯 Giới Thiệu

**CNM-ZELOO** là một ứng dụng nhắn tin realtime được xây dựng với mục tiêu cung cấp trải nghiệm chat mượt mà trên cả nền tảng Web và Mobile. Ứng dụng sử dụng WebSocket (Socket.IO) để đảm bảo tin nhắn được gửi và nhận tức thì, kèm theo các tính năng video call, quản lý nhóm, và nhiều tính năng khác.

### 🌟 Điểm Nổi Bật

- ⚡ **Realtime Communication**: Tin nhắn và thông báo realtime với Socket.IO
- 🎥 **Video Calling**: Tích hợp VideoSDK cho cuộc gọi video chất lượng cao
- 📱 **Cross-Platform**: Hỗ trợ cả Web (React) và Mobile (React Native)
- 🔐 **Security**: Xác thực JWT, mã hóa mật khẩu với bcrypt
- 📦 **Media Storage**: Upload và lưu trữ media trên AWS S3
- 👥 **Group Management**: Quản lý nhóm chat với phân quyền chi tiết

---

## ✨ Tính Năng

### 🔑 Xác Thực & Bảo Mật
- ✅ Đăng ký tài khoản với xác thực email OTP
- ✅ Đăng nhập với JWT token
- ✅ Quên mật khẩu & đặt lại mật khẩu qua OTP
- ✅ Bảo mật mật khẩu với bcrypt hashing
- ✅ Cookie-based authentication

### 💬 Chat & Messaging
- ✅ Chat 1-1 realtime
- ✅ Chat nhóm (Group chat)
- ✅ Gửi tin nhắn văn bản
- ✅ Gửi hình ảnh, video, audio
- ✅ Gửi vị trí (location)
- ✅ Phản hồi tin nhắn (Reply)
- ✅ Xóa tin nhắn
- ✅ Thu hồi tin nhắn (Unsend)
- ✅ Reaction emoji
- ✅ Hiển thị trạng thái online/offline
- ✅ Hiển thị thời gian hoạt động cuối

### 🎥 Video & Voice Call
- ✅ Tạo phòng meeting tự động
- ✅ Video call 1-1
- ✅ Video call nhóm
- ✅ Thông báo cuộc gọi đến
- ✅ Chấp nhận/Từ chối cuộc gọi

### 👥 Quản Lý Bạn Bè & Nhóm
- ✅ Gửi lời mời kết bạn
- ✅ Chấp nhận/Từ chối lời mời kết bạn
- ✅ Danh sách bạn bè
- ✅ Danh sách lời mời kết bạn
- ✅ Tạo nhóm chat
- ✅ Thêm/Xóa thành viên nhóm
- ✅ Phân quyền trong nhóm (Owner, Admin, Member)
- ✅ Ghim tin nhắn trong nhóm
- ✅ Rời khỏi nhóm

### 🔔 Thông Báo
- ✅ Thông báo realtime
- ✅ Thông báo cuộc gọi đến
- ✅ Thông báo tin nhắn mới
- ✅ Thông báo lời mời kết bạn

---

## 🛠 Công Nghệ

### Backend (BE)
```
Node.js + Express.js
├── Database: MongoDB (Mongoose ODM)
├── Realtime: Socket.IO
├── Authentication: JWT + bcrypt
├── Email Service: Nodemailer
├── File Upload: Multer
├── Cloud Storage: AWS SDK (S3)
├── Validation: Joi + Validator
├── Video SDK: VideoSDK API
└── Dev Tools: Nodemon
```

**Dependencies:**
- `express` - Web framework
- `mongoose` - MongoDB ODM
- `socket.io` - WebSocket library
- `jsonwebtoken` - JWT authentication
- `bcrypt` - Password hashing
- `aws-sdk` - AWS S3 integration
- `multer` - File upload handling
- `nodemailer` - Email sending
- `joi` - Schema validation
- `validator` - String validation
- `cors` - Cross-origin resource sharing

### Frontend Web (FE-Web)
```
React.js
├── Routing: React Router DOM v6
├── UI Framework: React Bootstrap + Bootstrap 5
├── Icons: Font Awesome + Bootstrap Icons + React Icons
├── Realtime: Socket.IO Client
├── HTTP Client: Axios
├── Video SDK: @videosdk.live/react-sdk
├── Styling: SASS/SCSS + Styled Components
├── State Management: React Hooks Global State
├── Components: 
│   ├── Chat Interface
│   ├── Video Meeting
│   ├── Friend Management
│   └── Authentication Forms
└── Deployment: Firebase Hosting
```

**Dependencies:**
- `react` v18.2.0 - UI library
- `react-router-dom` v6.22.3 - Routing
- `axios` - HTTP client
- `socket.io-client` - WebSocket client
- `react-bootstrap` - UI components
- `@videosdk.live/react-sdk` - Video calling
- `react-toastify` - Notifications
- `react-input-emoji` - Emoji input
- `react-player` - Media player
- `js-cookie` - Cookie handling

### Frontend Mobile (FE-Mobile)
```
React Native + Expo
├── Navigation: React Navigation v7
│   ├── Native Stack Navigator
│   └── Stack Navigator
├── Realtime: Socket.IO Client
├── HTTP Client: Axios
├── Storage: AsyncStorage
├── Media: 
│   ├── Expo Image Picker
│   ├── Expo AV (Audio/Video)
│   └── Expo Location
├── Icons: React Native Vector Icons
└── Screens:
    ├── Authentication (Login, Register, OTP, Forgot Password)
    ├── Chat (Chat List, Chat Detail, Online Chat)
    ├── Friends (Friend List, Friend Requests)
    ├── Meeting (Video Call)
    ├── Profile
    └── News
```

**Dependencies:**
- `react-native` v0.79.2
- `expo` v53.0.9
- `@react-navigation/native` - Navigation
- `axios` - HTTP client
- `socket.io-client` - WebSocket client
- `@react-native-async-storage/async-storage` - Local storage
- `expo-image-picker` - Image selection
- `expo-av` - Audio/Video playback
- `expo-location` - Location services
- `react-native-vector-icons` - Icons

---

## 🏗 Kiến Trúc Hệ Thống

```
CNM-ZELOO/
│
├── BE/ (Backend - Node.js)
│   ├── server/
│   │   ├── controllers/      # Business logic
│   │   │   ├── userController.js
│   │   │   ├── chatRoomController.js
│   │   │   ├── messageController.js
│   │   │   ├── groupController.js
│   │   │   ├── directController.js
│   │   │   └── otpController.js
│   │   ├── models/           # MongoDB schemas
│   │   │   ├── user.js
│   │   │   ├── chatRoom.js
│   │   │   ├── message.js
│   │   │   ├── group.js
│   │   │   ├── groupDetail.js
│   │   │   ├── direct.js
│   │   │   └── otpModel.js
│   │   ├── routes/           # API routes
│   │   │   ├── index.js
│   │   │   ├── site.js
│   │   │   └── message.js
│   │   ├── middleware/       # Middleware functions
│   │   ├── utils/            # Utility functions
│   │   │   ├── apicode.js
│   │   │   ├── mailSender.js
│   │   │   ├── permission.js
│   │   │   ├── rolesEnum.js
│   │   │   └── pagination.js
│   │   ├── api.js            # VideoSDK integration
│   │   └── index.js          # Server entry + Socket.IO setup
│   ├── package.json
│   └── .env
│
├── FE-Web/ (Frontend Web - React)
│   ├── src/
│   │   ├── components/       # Reusable components
│   │   │   ├── chat/
│   │   │   ├── LoginForm.js
│   │   │   ├── RegisterForm.js
│   │   │   ├── FriendRequest.js
│   │   │   └── SendOtp.js
│   │   ├── pages/            # Page components
│   │   │   ├── Home.js
│   │   │   ├── Chat.js
│   │   │   ├── MeetingView.js
│   │   │   ├── Friend.js
│   │   │   ├── ListFriendRequest.js
│   │   │   └── Register.js
│   │   ├── layout/           # Layout components
│   │   ├── api/              # API services
│   │   ├── configs/          # Configuration files
│   │   ├── authToken/        # Auth utilities
│   │   ├── GlobalStyle/      # Global styles
│   │   ├── assets/           # Static assets
│   │   ├── App.js            # App entry + routing
│   │   └── index.js
│   ├── public/
│   ├── package.json
│   ├── firebase.json         # Firebase hosting config
│   └── .env
│
└── FE-Mobile/ (Frontend Mobile - React Native)
    ├── screens/              # Screen components
    │   ├── LoginScreen.js
    │   ├── RegisterScreen.js
    │   ├── ForgotPasswordScreen.js
    │   ├── OTPScreen.js
    │   ├── ResetPasswordScreen.js
    │   ├── ChatListScreen.js
    │   ├── ChatDetailScreen.js
    │   ├── OnlineChatScreen.js
    │   ├── FriendListScreen.js
    │   ├── FriendListRequest.js
    │   ├── GroupMemberManagement.js
    │   ├── MeetingScreen.js
    │   ├── NewsScreen.js
    │   ├── Profile.js
    │   └── Footer.js
    ├── assets/               # Images, fonts, etc.
    ├── App.js                # App entry + navigation
    ├── config.js             # API configuration
    ├── app.json              # Expo configuration
    ├── package.json
    └── index.js
```

### Database Schema

**User Schema:**
```javascript
{
  username: String,
  password: String (hashed),
  email: String,
  phoneNumber: String,
  displayName: String,
  photoURL: String,
  dateOfBirth: Date,
  gender: String,
  isOnline: Boolean,
  lastOnlineTime: Date,
  friends: [ObjectId],
  friendRequests: [ObjectId]
}
```

**ChatRoom Schema:**
```javascript
{
  active: Boolean,
  thumbnailURL: String,
  type: String (direct/group),
  lastMessage: String,
  lastMessageTime: Date
}
```

**Message Schema:**
```javascript
{
  senderID: ObjectId,
  content: String,
  counter: Number,
  chatRoomId: ObjectId,
  createAt: Date,
  reply: Object,
  reaction: Object,
  type: String,
  isDeleted: Boolean,
  media: [{
    type: String,
    url: String
  }]
}
```

**Group Schema:**
```javascript
{
  name: String,
  ownerId: ObjectId,
  chatRoomId: ObjectId,
  photoURL: String,
  description: String,
  members: [ObjectId]
}
```

---

## 🚀 Cài Đặt

### Yêu Cầu Hệ Thống

- **Node.js**: v14.x trở lên
- **MongoDB**: v4.x trở lên
- **npm** hoặc **yarn**
- **Expo CLI** (cho mobile)
- **Git**

### Clone Repository

```bash
git clone https://github.com/your-username/CNM-ZELOO.git
cd CNM-ZELOO
```

### 1️⃣ Cài Đặt Backend

```bash
cd BE
npm install
```

Tạo file `.env`:
```env
PORT=3000
MONGO_URL=mongodb://127.0.0.1:27017/zeloo
JWT_SECRET=your_jwt_secret_key_here
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_email_app_password
AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
AWS_REGION=your_aws_region
AWS_BUCKET_NAME=your_bucket_name
VIDEOSDK_API_KEY=your_videosdk_api_key
VIDEOSDK_SECRET_KEY=your_videosdk_secret
```

Khởi chạy server:
```bash
npm start
# hoặc
npm run start
```

Server sẽ chạy tại: `http://localhost:3000`

### 2️⃣ Cài Đặt Frontend Web

```bash
cd FE-Web
npm install
```

Tạo file `.env`:
```env
REACT_APP_API_URL=http://localhost:3000
REACT_APP_SOCKET_URL=http://localhost:3000
```

Khởi chạy web app:
```bash
npm start
```

Web app sẽ chạy tại: `http://localhost:3000` (hoặc cổng khác nếu 3000 đã được sử dụng)

### 3️⃣ Cài Đặt Frontend Mobile

```bash
cd FE-Mobile
npm install
```

Cập nhật `config.js`:
```javascript
export const BASE_URL = 'http://your-backend-url:3000';
// Hoặc sử dụng ngrok cho development
```

Khởi chạy Expo:
```bash
npm start
# hoặc
npx expo start
```

Scan QR code bằng Expo Go app (iOS/Android) để test trên thiết bị thật.

---

## ⚙️ Cấu Hình

### MongoDB Setup

1. Cài đặt MongoDB Community Edition
2. Start MongoDB service:
```bash
# Windows
net start MongoDB

# macOS/Linux
sudo systemctl start mongodb
```

3. Tạo database:
```bash
mongosh
use zeloo
```

### AWS S3 Configuration

1. Tạo AWS account và S3 bucket
2. Tạo IAM user với quyền S3
3. Copy Access Key và Secret Key vào `.env`
4. Cấu hình CORS cho bucket:
```json
[
  {
    "AllowedHeaders": ["*"],
    "AllowedMethods": ["GET", "PUT", "POST", "DELETE"],
    "AllowedOrigins": ["*"],
    "ExposeHeaders": []
  }
]
```

### VideoSDK Configuration

1. Đăng ký tài khoản tại [VideoSDK.live](https://www.videosdk.live/)
2. Lấy API Key và Secret Key
3. Update vào `BE/server/api.js` hoặc `.env`

### Email Service (Nodemailer)

Sử dụng Gmail với App Password:
1. Bật 2-factor authentication cho Gmail
2. Tạo App Password: https://myaccount.google.com/apppasswords
3. Copy password vào `.env`

---

## 📖 Sử Dụng

### Đăng Ký Tài Khoản

1. Mở app (Web hoặc Mobile)
2. Click "Đăng ký"
3. Nhập thông tin: email, username, password
4. Nhận OTP qua email
5. Nhập OTP để xác thực
6. Hoàn tất đăng ký

### Đăng Nhập

1. Nhập username/email và password
2. Click "Đăng nhập"
3. Token sẽ được lưu tự động

### Chat 1-1

1. Vào danh sách bạn bè
2. Click vào bạn bè để mở chat
3. Gửi tin nhắn văn bản, hình ảnh, video
4. Sử dụng emoji, reply, reaction

### Tạo Nhóm

1. Click "Tạo nhóm"
2. Nhập tên nhóm
3. Chọn thành viên từ danh sách bạn bè
4. Click "Tạo"

### Video Call

1. Trong chat, click icon video call
2. Đợi người nhận chấp nhận
3. Bắt đầu cuộc gọi

---

## 📡 API Documentation

### Authentication Endpoints

#### Register
```http
POST /api/register
Content-Type: application/json

{
  "username": "string",
  "email": "string",
  "password": "string"
}
```

#### Login
```http
POST /api/login
Content-Type: application/json

{
  "username": "string",
  "password": "string"
}

Response: {
  "token": "jwt_token",
  "user": {...}
}
```

#### Send OTP
```http
POST /api/send-otp
Content-Type: application/json

{
  "email": "string"
}
```

### Chat Endpoints

#### Get Chat List
```http
GET /api/chatrooms/:userId
Authorization: Bearer {token}

Response: [
  {
    "_id": "chatRoomId",
    "lastMessage": "string",
    "lastMessageTime": "date",
    ...
  }
]
```

#### Send Message
```http
POST /api/messages
Authorization: Bearer {token}

{
  "chatRoomId": "string",
  "content": "string",
  "type": "text|image|video|audio|location",
  "media": []
}
```

### Socket Events

#### Client → Server

- `setup` - Initialize user connection
- `join chat` - Join a chat room
- `message` - Send message
- `delete message` - Delete message
- `unsend message` - Unsend message
- `react message` - Add reaction
- `call` - Initiate video call
- `notify` - Send notification
- `accept meeting` - Accept call
- `decline` - Decline call

#### Server → Client

- `setup` - Connection confirmed
- `message` - New message received
- `delete message` - Message deleted
- `unsend message` - Message unsent
- `react message` - Reaction added
- `call` - Incoming call
- `incomingCall` - Call notification
- `decline` - Call declined

---

## 👥 Team

**CNM-ZELOO Development Team**

---

## 📞 Liên Hệ

- **Project Link**: https://github.com/your-username/CNM-ZELOO
- **Issues**: https://github.com/your-username/CNM-ZELOO/issues
- **Backend API**: 

---

## 🙏 Acknowledgments

- [VideoSDK.live](https://www.videosdk.live/) - Video calling solution
- [Socket.IO](https://socket.io/) - Realtime engine
- [MongoDB](https://www.mongodb.com/) - Database
- [React](https://react.dev/) - UI library
- [React Native](https://reactnative.dev/) - Mobile framework
- [Expo](https://expo.dev/) - React Native toolchain
- [AWS](https://aws.amazon.com/) - Cloud storage