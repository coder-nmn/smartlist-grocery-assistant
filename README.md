# SmartList – Intelligent Grocery Cart Assistant

A responsive AI-powered web application that helps users manage grocery shopping smartly by using past data, real-time cart tracking, budget alerts, and voice input.

## 🚀 Features

### ✅ Smart Grocery List
- Auto-suggest previously bought items (simulated with mock data)
- Allow users to add/remove items manually
- Search functionality for products
- Essential items highlighting

### 🗣️ Voice-Enabled List Creation
- Uses browser speech-to-text (Web Speech API)
- AI-powered voice parsing using OpenRouter API with GPT-4o
- Input example: "Add milk, eggs, and cheese under ₹800"
- Customizable AI system prompt

### 💸 Budget Watchdog
- Set custom budget amounts
- Track cart total in real-time
- Visual progress bar with color coding
- Warn user visually if they exceed the budget
- Show remaining budget or overage amount

### 💡 Budget-Friendly Swaps
- Show cheaper alternatives from product dataset
- Example: "Amul Butter ₹52 → Mother Dairy ₹46"
- Calculate and display savings
- One-click alternative selection

### 🧾 Deals and Coupons Panel
- Display list of available coupons/offers
- Show expiry dates and minimum purchase requirements
- Apply coupons to reduce cart total
- Support for fixed amount and percentage discounts
- Visual feedback for applied coupons

## 🔧 Tech Stack

- **Frontend**: Next.js 15 with React 19 and TypeScript
- **Styling**: Tailwind CSS with shadcn/ui components
- **Voice Input**: Web Speech API
- **AI Processing**: OpenRouter API with GPT-4o model
- **State Management**: React Context API
- **Data**: JSON mock data files
- **Development**: Turbopack for fast development

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ 
- npm or yarn
- OpenRouter API key (for voice parsing)

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd smartlist-grocery-assistant
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.local.example .env.local
   ```
   
   Add your OpenRouter API key to `.env.local`:
   ```
   OPENROUTER_API_KEY=your_openrouter_api_key_here
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

5. **Open your browser**
   Navigate to `http://localhost:8000`

## 🌐 Live Demo & Deployment

### 🔗 **Shareable Links**

**Current Local Development:**
- `http://localhost:8000` (while your dev server is running)

**For Public Sharing - Deploy to Vercel:**

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/your-username/smartlist-grocery-assistant)

### Quick Deployment Steps:

1. **Push to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: SmartList Grocery Assistant"
   git branch -M main
   git remote add origin https://github.com/your-username/smartlist-grocery-assistant.git
   git push -u origin main
   ```

2. **Deploy to Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import your GitHub repository
   - Add environment variable: `OPENROUTER_API_KEY`
   - Click "Deploy"

3. **Get Your Shareable URL**
   After deployment, you'll get a public URL like: 
   **`https://smartlist-grocery-assistant.vercel.app`**

### Alternative Hosting Options
- **Netlify**: Free hosting with drag-and-drop deployment
- **Railway**: One-click GitHub deployment
- **Render**: Free tier with automatic deployments
- **Vercel**: Best for Next.js (recommended)

## 🎯 Usage Guide

### Setting a Budget
1. Enter your desired budget amount in the "Set Your Budget" section
2. Click "Set Budget" to activate budget tracking
3. The Budget Watchdog will show progress and warnings

### Adding Items
1. Browse available products in the "Smart Grocery List"
2. Click "Add" to add items to your cart
3. Use "Cheaper Options" to find alternatives
4. Search for specific products using the search bar

### Voice Input
1. Click "🎤 Start Listening" in the Voice-Enabled section
2. Say something like: "Add milk, eggs, and cheese under ₹800"
3. The AI will parse your input and add items + set budget
4. Customize the AI system prompt as needed

### Applying Coupons
1. View available coupons in the "Deals and Coupons Panel"
2. Check minimum purchase requirements
3. Click "Apply" on eligible coupons
4. See the discount reflected in your cart total

## 🔍 API Endpoints

### `/api/products`
- **GET**: Retrieve all products
- **Query**: `?q=search_term` for filtering

### `/api/coupons`
- **GET**: Retrieve all available coupons

### `/api/parse-voice`
- **POST**: Parse voice input using AI
- **Body**: `{ transcript: "voice input text" }`
- **Response**: `{ items: [...], budget: number }`

## 🧠 AI Integration

The application uses OpenRouter's GPT-4o model for intelligent voice parsing:

- **Model**: `openai/gpt-4o` (multimodal, multilingual)
- **Endpoint**: `https://openrouter.ai/api/v1/chat/completions`
- **Purpose**: Parse natural language voice input into structured data
- **Input**: Voice transcript
- **Output**: JSON with items array and budget number

## 🧪 Mock Data

### Products (20 items)
- Categorized by: dairy, poultry, bakery, grains, grocery, vegetables, fruits
- Each item includes: name, brand, price, category, unit, essential flag
- Price range: ₹20 - ₹200

### Coupons (5 coupons)
- SAVE30: ₹30 off on ₹100+ purchase
- 50OFF500: ₹50 off on ₹500+ purchase
- 15PERCENT: 15% off on ₹200+ purchase
- EXPIRED10: Expired coupon (for testing)
- BIGDEAL100: ₹100 off on ₹1000+ purchase

## 🎨 UI Features

- **Clean, modern design** with Tailwind CSS
- **Responsive layout** that works on all devices
- **Color-coded feedback** (green for success, red for warnings, yellow for caution)
- **Interactive elements** with hover effects and transitions
- **Accessibility** considerations with proper contrast and focus states
- **No external icons or images** - clean typography-focused design

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License.

## 🙏 Acknowledgments

- OpenRouter for AI API services
- shadcn/ui for beautiful UI components
- Tailwind CSS for styling system
- Next.js team for the amazing framework

---

**SmartList** - Making grocery shopping smarter, one voice command at a time! 🛒✨
