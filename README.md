# IntelliPHP - VSCode AI Code Completion Extension

A professional-grade AI code completion extension for VSCode powered by ONNX-based deep learning model.

## 🚀 Features

- **Real-time Code Completion** - Intelligent suggestions as you type
- **PHP, JavaScript, TypeScript Support** - Multi-language backend
- **ONNX Runtime Integration** - Lightweight and fast inference
- **Beam Search Algorithm** - Top-3 suggestions with confidence scores
- **KV Cache Optimization** - Reduced latency for sequential generation
- **Code-Specific Tokenization** - Specialized for programming languages

## 📋 Project Structure

```
.
├── vscode-extension/          # VSCode Extension (TypeScript)
├── backend/                   # C# ASP.NET Core Backend
├── models/                    # Model files and tokenizers
│   ├── intelliphp_v3/
│   │   ├── model.onnx
│   │   ├── metadata.json
│   │   ├── vocab.json
│   │   ├── tokenizer.bin
│   │   └── literals.json
├── docs/                      # Documentation
└── tests/                     # Unit & Integration Tests
```

## 🔧 Setup

### Backend (C# ASP.NET Core)

```bash
cd backend
dotnet restore
dotnet build
dotnet run
```

Server will run on `http://localhost:5000`

### VSCode Extension

```bash
cd vscode-extension
npm install
npm run compile
code --extensionDevelopmentPath=$(pwd)
```

## 📡 API Endpoints

### POST /api/inference/complete

Request:
```json
{
  "prompt": "function validateEmail(",
  "language": "php",
  "numBeams": 3,
  "maxNewTokens": 20
}
```

Response:
```json
{
  "suggestions": [
    { "text": "$email", "confidence": 0.92 },
    { "text": "$input", "confidence": 0.87 },
    { "text": "$data", "confidence": 0.81 }
  ],
  "latency_ms": 145
}
```

## 🎯 Model Details

- **Name**: IntelliPHP_Compose v1.3.76
- **Architecture**: Transformer (8 layers, 8 attention heads, 512 embeddings)
- **Inference Engine**: ONNX Runtime
- **Tokenization**: Code-specific with special tokens
- **Max Input**: 512 tokens

## 📚 Documentation

See `/docs` for detailed guides on:
- Architecture overview
- Tokenizer usage
- Extension development
- Deployment

## 📝 License

MIT
