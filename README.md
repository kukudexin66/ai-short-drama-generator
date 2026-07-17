# AI 小短剧视频生成平台

一个全栈 AI 小短剧视频生成网站，支持用户上传视频、AI 配音、虚拟形象、自动生成视频等功能。参考集梦AI、海螺AI等市面产品功能。

## 功能特性

- ✅ 视频上传和解析
- ✅ 文本转语音 (TTS) - 支持多种语言和声音
- ✅ AI 虚拟形象库 - 选择或自定义角色
- ✅ 剧本编辑器 - 灵活编辑对白和场景
- ✅ 视频合成引擎 - 生成最终短视频
- ✅ 项目管理 - 保存、编辑、导出
- ✅ 用户系统 - 注册、登录、配额管理
- ✅ 视频预览 - 实时预览效果
- ✅ 批量处理 - 支持多个视频并行生成

## 技术栈

### 前端
- **框架**: React 18 + Next.js 14
- **UI库**: Tailwind CSS + shadcn/ui
- **状态管理**: Zustand
- **API**: Axios
- **富文本编辑**: Monaco Editor
- **视频播放**: Video.js

### 后端
- **运行时**: Node.js
- **框架**: Express.js
- **数据库**: PostgreSQL
- **ORM**: Prisma
- **认证**: JWT + bcrypt
- **文件存储**: AWS S3 / 本地存储
- **视频处理**: FFmpeg
- **TTS服务**: Google Cloud Speech-to-Text / ElevenLabs

### 基础设施
- **容器化**: Docker + Docker Compose
- **部署**: Docker / AWS / Vercel / 自建服务器

## 项目结构

```
ai-short-drama-generator/
├── frontend/                 # React 前端应用
│   ├── public/
│   ├── src/
│   │   ├── pages/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── utils/
│   │   ├── styles/
│   │   └── services/
│   ├── next.config.js
│   ├── package.json
│   └── tailwind.config.js
├── backend/                  # Node.js 后端应用
│   ├── src/
│   │   ├── routes/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── middleware/
│   │   ├── services/
│   │   ├── utils/
│   │   ├── config/
│   │   └── app.ts
│   ├── prisma/
│   │   └── schema.prisma
│   ├── package.json
│   ├── tsconfig.json
│   └── .env.example
├── docker-compose.yml
├── .gitignore
└── README.md
```

## 快速开始

### 前置要求
- Node.js >= 16
- Docker & Docker Compose
- PostgreSQL (或使用 Docker)
- FFmpeg

### 本地开发

```bash
# 1. 克隆项目
git clone https://github.com/kukudexin66/ai-short-drama-generator.git
cd ai-short-drama-generator

# 2. 启动 Docker 服务 (PostgreSQL + Redis)
docker-compose up -d

# 3. 配置后端
cd backend
cp .env.example .env
npm install
npx prisma migrate dev
npm run dev

# 4. 配置前端 (新终端)
cd frontend
npm install
npm run dev
```

访问 http://localhost:3000

### 配置文件

后端 `.env`:
```
DATABASE_URL="postgresql://user:password@localhost:5432/ai_drama"
JWT_SECRET="your-secret-key"
NODE_ENV="development"
API_PORT=3001
GOOGLE_CLOUD_API_KEY="your-google-cloud-key"
ELEVENLABS_API_KEY="your-elevenlabs-key"
AWS_ACCESS_KEY_ID="your-aws-key"
AWS_SECRET_ACCESS_KEY="your-aws-secret"
AWS_S3_BUCKET="your-bucket-name"
```

## 核心功能模块

### 1. 用户系统
- 用户注册/登录
- JWT 认证
- 配额管理（免费/付费计划）
- 个人资料管理

### 2. 视频管理
- 上传和存储
- 视频元数据提取
- 场景识别
- 视频库管理

### 3. 剧本编辑
- 文本编辑器
- 角色分配
- 对白编辑
- 场景管理

### 4. AI 配音
- 文本转语音
- 多种语言支持
- 声音库管理
- 音频同步

### 5. 虚拟形象
- 形象库
- 自定义形象
- 动作库
- 表情管理

### 6. 视频合成
- 视频渲染
- 音频混合
- 字幕添加
- 特效应用

### 7. 导出和分享
- 多格式导出 (MP4, WebM)
- 视频分享
- 下载管理

## API 文档

详见 [API文档](./docs/API.md)

## 贡献

欢迎提交 Issue 和 Pull Request！

## 许可证

MIT License

## 支持

有问题？请提交 Issue 或联系开发者。
