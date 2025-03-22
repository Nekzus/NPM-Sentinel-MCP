# MCP Server Nekzus

[![Github Workflow](https://github.com/nekzus/mcp-server/actions/workflows/publish.yml/badge.svg?event=push)](https://github.com/Nekzus/mcp-server/actions/workflows/publish.yml)
[![npm-version](https://img.shields.io/npm/v/@nekzus/mcp-server.svg)](https://www.npmjs.com/package/@nekzus/mcp-server)
[![npm-month](https://img.shields.io/npm/dm/@nekzus/mcp-server.svg)](https://www.npmjs.com/package/@nekzus/mcp-server)
[![npm-total](https://img.shields.io/npm/dt/@nekzus/mcp-server.svg?style=flat)](https://www.npmjs.com/package/@nekzus/mcp-server)
[![Donate](https://img.shields.io/badge/donate-paypal-blue.svg?style=flat-square)](https://paypal.me/maseortega)

<div align="center">

**A Model Context Protocol (MCP) server that provides utility tools for
development and testing** </br>_This implementation is built on top of the
official MCP SDK and offers an extensible architecture for adding new tools_

</div>

## 🌟 Features

- 🔄 MCP Protocol Implementation
- 🛠️ Integrated Utility Tools
- 📝 Schema Validation with Zod
- 🚀 ESM Support
- 🔒 Strict TypeScript Types
- 🧩 Extensible Architecture for New Tools

## 🛠️ Available Tools

### 1. greeting

Generates a personalized greeting message.

**Parameters:**

- `name` (string): Recipient's name

**Example:**

```typescript
// Result: 👋 Hello John! Welcome to the MCP server!
{
  name: "John";
}
```

### 2. card

Gets a random card from a standard poker deck.

**Parameters:**

- No parameters required

**Example:**

```typescript
// Result: 🎴 You drew: Ace of ♠️ Spades
{}
```

### 3. datetime

Gets the current date and time for a specific timezone.

**Parameters:**

- `timeZone` (string, optional): Timezone identifier (e.g., "America/New_York")
- `locale` (string, optional): Locale identifier (e.g., "en-US")

**Example:**

```typescript
// Result: 
// 🗓️ Date: March 20, 2024
// ⏰ Time: 7:25:25 PM
// 🌍 Timezone: America/New_York
{
  timeZone: "America/New_York",
  locale: "en-US"
}
```

### 4. calculator

Performs mathematical calculations with support for basic and advanced operations.

**Parameters:**

- `expression` (string): Mathematical expression (e.g., "2 + 2 * 3")
- `precision` (number, optional): Decimal places in the result (default: 2)

**Example:**

```typescript
// Result: 8
{
  expression: "2 + 2 * 3"
}
```

### 5. passwordGen

Generates secure passwords with customizable options.

**Parameters:**

- `length` (number, optional): Password length (default: 16)
- `includeNumbers` (boolean, optional): Include numbers (default: true)
- `includeSymbols` (boolean, optional): Include special characters (default: true)
- `includeUppercase` (boolean, optional): Include uppercase letters (default: true)

**Example:**

```typescript
// Result: 4v7&9G8$
{
  length: 16,
  includeNumbers: true,
  includeSymbols: true,
  includeUppercase: true
}
```

### 6. qrGen

Generates QR codes for text or URLs.

**Parameters:**

- `text` (string): Text or URL to encode
- `size` (number, optional): Size in pixels (default: 200)
- `dark` (string, optional): Dark module color (default: "#000000")
- `light` (string, optional): Light module color (default: "#ffffff")

**Example:**

```typescript
// Result: QR code for "https://example.com"
{
  text: "https://example.com"
}
```

### 7. kitchenConvert

Converts between common kitchen measurements and weights, including volume-to-weight conversions based on specific ingredients.

**Parameters:**

- `value` (number): Value to convert
- `from` (string): Source unit (e.g., "cup", "tbsp", "g", "oz", "ml")
- `to` (string): Target unit (e.g., "cup", "tbsp", "g", "oz", "ml")
- `ingredient` (string, optional): Ingredient for accurate volume-to-weight conversions

**Supported Units:**

*Volume:*
- ml (milliliters)
- l (liters)
- cup (US cup)
- tbsp (tablespoon)
- tsp (teaspoon)
- floz (fluid ounce)

*Weight:*
- g (grams)
- kg (kilograms)
- oz (ounces)
- lb (pounds)

**Supported Ingredients:**
- water
- milk
- flour
- sugar
- brown sugar
- salt
- butter
- oil
- honey
- maple syrup

**Examples:**

```typescript
// Simple volume conversion
// Result: 🔄 Conversion Result:
// • 1 cup = 236.59 ml
{
  value: 1,
  from: "cup",
  to: "ml"
}

// Volume to weight conversion with ingredient
// Result: 🔄 Conversion Result:
// • 1 cup of flour = 140.25 g
{
  value: 1,
  from: "cup",
  to: "g",
  ingredient: "flour"
}
```

## 🚀 Usage

### As MCP Server

1. **Global Installation:**

```bash
npm install -g @nekzus/mcp-server
```

2. **Execution:**

```bash
npx @nekzus/mcp-server
```

### As a Dependency

```typescript
import { McpUtilityServer } from "@nekzus/mcp-server";

const server = new McpUtilityServer();
server.start();
```

## 🔧 Development

```bash
# Clone repository
git clone https://github.com/nekzus/mcp-server.git

# Install dependencies
npm install

# Development mode
npm run dev

# Build
npm run build

# Run
npm start
```

## 📁 Project Structure

```
src/
├── types/          # Type definitions
│   └── index.ts    # Shared types
├── utils/          # Utilities
│   ├── cards.ts    # Card functions
│   ├── datetime.ts # Date/time functions
│   └── schema.ts   # Schema conversion
├── tools/          # Tool implementations
│   └── index.ts    # Tools registry
└── index.ts        # Main entry point
```

## 🔍 Technical Details

- **Transport:** Uses `StdioServerTransport` for communication
- **Validation:** Converts JSON schemas to Zod for input validation
- **Types:** Fully typed implementation with TypeScript
- **Error Handling:** Robust error handling and resource cleanup
- **Signals:** Handles SIGTERM and SIGINT signals for graceful shutdown

## 📄 License

This MCP server is licensed under the MIT License. This means you are free to use, modify, and distribute the software, subject to the terms and conditions of the MIT License. For more details, please see the LICENSE file in the project repository.

## 👤 Author

**Nekzus**

- GitHub: [@nekzus](https://github.com/nekzus)

## 🌟 Support

Give a ⭐️ if this project helped you!
