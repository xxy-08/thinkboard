### **1. 前端框架**
前端使用了 **React**，并结合了以下技术和工具：
- **React Router**: 用于实现前端路由和页面导航。
- **Axios**: 用于与后端 API 进行 HTTP 请求。
- **Tailwind CSS**: 用于快速构建响应式和现代化的 UI。
- **React Hot Toast**: 用于显示用户友好的通知（如成功或错误提示）。
- **Lucide React**: 用于引入图标（如 `Trash2Icon`, `PenSquareIcon` 等）。

#### **前端目录结构**
```plaintext
frontend/
├── src/
│   ├── components/       # 可复用的组件（如 NoteCard, NotesNotFound 等）
│   ├── pages/            # 页面组件（如 HomePage, CreatePage, NoteDetailPage）
│   ├── lib/              # 工具库（如 axios 配置、日期格式化工具）
│   ├── App.jsx           # 应用的入口组件，定义路由
│   ├── index.jsx         # React 应用的入口文件
│   ├── styles/           # 全局样式文件（如果有）
│   └── assets/           # 静态资源（如图片、图标等）
```

#### **前端主要功能**
1. **主页 (HomePage)**:
   - 显示所有笔记的列表。
   - 使用 `NoteCard` 组件展示每条笔记的标题、内容和创建时间。
   - 提供导航到笔记详情页或创建新笔记的功能。

2. **笔记详情页 (NoteDetailPage)**:
   - 显示单条笔记的详细信息。
   - 提供编辑和删除笔记的功能。

3. **创建页 (CreatePage)**:
   - 提供表单，允许用户创建新笔记。
   - 使用 `axios` 向后端发送 POST 请求。

4. **复用组件**:
   - **`NoteCard`**: 用于显示单条笔记的卡片。
   - **`NotesNotFound`**: 当没有笔记时显示的提示组件。

---

### **2. 后端框架**
后端使用了 **Node.js** 和 **Express**，并结合了以下技术：
- **MongoDB**: 用于存储笔记数据。
- **Mongoose**: 用于定义数据模型和与 MongoDB 交互。
- **dotenv**: 用于加载环境变量（如 MongoDB 连接字符串）。
- **CORS**: 用于允许前端跨域访问后端 API。

#### **后端目录结构**
```plaintext
backend/
├── src/
│   ├── controllers/      # 控制器，处理业务逻辑（如 notesController.js）
│   ├── models/           # 数据模型（如 Note.js）
│   ├── routes/           # 路由定义（如 notesRoutes.js）
│   ├── config/           # 配置文件（如数据库连接）
│   ├── server.js         # 应用的入口文件
│   └── utils/            # 工具函数（如果有）
```

#### **后端主要功能**
1. **API 路由**:
   - **GET `/notes`**: 获取所有笔记。
   - **GET `/notes/:id`**: 获取单条笔记的详情。
   - **POST `/notes`**: 创建新笔记。
   - **PUT `/notes/:id`**: 更新笔记。
   - **DELETE `/notes/:id`**: 删除笔记。

2. **数据模型**:
   - 使用 Mongoose 定义 `Note` 模型，包含 `title`, `content`, `createdAt` 等字段。

3. **数据库连接**:
   - 使用 `mongoose.connect` 连接到 MongoDB 数据库。

4. **错误处理**:
   - 捕获 API 请求中的错误并返回适当的 HTTP 状态码和错误信息。

---

### **3. 项目运行脚本**
在 package.json 中定义了以下脚本：
- **`npm run bulid`**:
  - 安装前后端依赖并构建前端代码。
- **`npm run start`**:
  - 启动后端服务器。

---

### **4. 项目工作流程**
1. **用户访问主页**:
   - 前端通过 `axios` 向后端发送 `GET /notes` 请求，获取所有笔记并显示在主页。

2. **用户查看笔记详情**:
   - 点击某条笔记，前端通过 `axios` 向后端发送 `GET /notes/:id` 请求，获取笔记详情并显示。

3. **用户创建新笔记**:
   - 在创建页填写表单，前端通过 `axios` 向后端发送 `POST /notes` 请求，创建新笔记。

4. **用户编辑或删除笔记**:
   - 编辑：前端通过 `axios` 向后端发送 `PUT /notes/:id` 请求，更新笔记。
   - 删除：前端通过 `axios` 向后端发送 `DELETE /notes/:id` 请求，删除笔记。

---

### **5. 技术栈总结**
- **前端**:
  - React, React Router, Axios, Tailwind CSS, React Hot Toast, Lucide React
- **后端**:
  - Node.js, Express, MongoDB, Mongoose, dotenv, CORS

---

如果你需要更详细的说明或具体功能的实现，请告诉我！
