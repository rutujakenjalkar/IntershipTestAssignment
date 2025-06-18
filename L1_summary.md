# Repository Structure & Agent Workflow

This document outlines the structure and functionality of the `idosal/scira-mcp-ui-chat` repository.

##  Directory Overview

### `ai/`

* **`providers.ts`**

  * Sets up API keys and connects to model providers like Anthropic, Groq.
  * Registers models and offers consistent access.

### `app/`

* **`api/chat/route.ts`**

  * Handles POST chat initiation.
  * Extracts user/model info, generates `chatId`, streams AI response.

* **`api/chats/[id]/route.ts`**

  * **GET**: Fetches chat for user.
  * **DELETE**: Deletes chat (validates `userId`).

* **`chat/[id]/page.tsx`**

  * Prefetches chat using `chatId` & `userId`.
  * Returns `404` if chat is missing.

* **`page.tsx`**

  * Renders main chat UI using `Chat` component.

### `components/`

* Houses reusable UI components.

#### Key Files:

* **`tool-invocation.tsx`**

  * Improved error handling, imports, styling.
* **`chat.tsx`**

  * Fetches chat by ID, includes error fallback.
* **`mcp-server-manager.tsx`**

  * Adds/removes selected servers, restart logic, error handling.

### `drizzle/`

* Schema and migration files for PostgreSQL.

### `hooks/`

* Custom React hooks.

### `lib/`

* **`user-id.ts`**

  * Gets/sets user ID using `USER_ID_KEY`.

* **`mcp-sandbox.ts`**

  * Starts sandbox with env variables and command (uvx/python).

* **`mcp-client.ts`**

  * Initializes MCP clients, loads server tools.

* **`chat-store.ts`**

  * Handles DB operations and format conversions:

    * `getChats`, `getChatById`, `deleteChat`, `saveChat`

* **`mcp-content.tsx`**

  * Defines context types and server lifecycle functions.

* **`db/schema.ts`**

  * Defines DB schema and types for chats/messages.

* **`db/index.ts`**

  * Connects to PostgreSQL using Drizzle ORM.

* **`constants.ts`**

  * Shared localStorage keys (servers/sidebar).

### `public/`

* Static files: images, icons, etc.

### Root Config Files

* Project settings and dependencies:

  * `tsconfig.json`, `next.config.ts`, `package.json`

---

##  Agent Workflow

1. `chat.tsx` loads `chatId` and `userId`.
2. `api/chats/route.ts` checks `userId` validity.
3. `textarea.tsx` uses `useChat()` to send user input.
4. `route.ts` initializes MCP clients and sets headers.
5. Server response is streamed, and `chat-store.ts` saves data.
6. To retrieve chats:

   * Frontend sends GET to `/api/chats/[id]` with `userId`.
   * `getChatById()` fetches or returns 404/500 error.




