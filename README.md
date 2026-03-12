# Store Management Backend API

B.Tech 4th Semester | AI308B - AI Driven Full Stack Development  
MSE-1 Examination (Practical), Even Sem. 2025-26

## Tech Stack
- **Node.js** + **Express.js** — Backend framework
- **MongoDB** + **Mongoose** — Database & ODM
- **dotenv** — Environment variable management
- **cors** — Cross-Origin Resource Sharing

---

## Project Setup

### 1. Clone the Repository
```bash
git clone https://github.com/<your-username>/store-management.git
cd store-management
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Configure Environment Variables
Create a `.env` file in the root directory:
```
PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/storeDB?retryWrites=true&w=majority
```

### 4. Run the Server
```bash
# Development (with nodemon)
npm run dev

# Production
npm start
```

---

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/products` | Add a new product |
| GET | `/products` | Get all products |
| GET | `/products/:id` | Get product by ID |
| PUT | `/products/:id` | Update product details |
| DELETE | `/products/:id` | Delete a product |
| GET | `/products/search?name=xyz` | Search product by name |
| GET | `/products/category?cat=xyz` | Filter by category |

---

## Product Schema

| Field | Type | Validation |
|-------|------|------------|
| productName | String | Required |
| productCode | String | Required, Unique |
| category | String | Enum: Electronics, Clothing, Food, Furniture, Other |
| supplierName | String | Required |
| quantityInStock | Number | Non-negative |
| reorderLevel | Number | > 0 |
| unitPrice | Number | Positive |
| manufactureDate | Date | Required |
| productType | String | Perishable / Non-Perishable |
| status | String | Default: Available |

---

## HTTP Status Codes Used
- `200` → Success
- `201` → Created
- `400` → Bad Request (validation errors, duplicate key)
- `404` → Not Found
- `500` → Server Error

---

## Deployment

- **GitHub**: https://github.com/<your-username>/store-management
- **Render**: https://<your-app>.onrender.com

### Deploy on Render
1. Push your code to GitHub
2. Go to [render.com](https://render.com) → New → Web Service
3. Connect your GitHub repository
4. Set:
   - **Build Command**: `npm install`
   - **Start Command**: `npm start`
5. Add environment variables (`MONGO_URI`, `PORT`) in Render dashboard
6. Click **Deploy**
