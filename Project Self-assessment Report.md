# Final project Self-assessment report

Team: 22120376-22120433-22120434

Backend Repository: https://github.com/DINH1022/aimail_be.git <br />
Frontend Repository: https://github.com/LTVINH24/AIEmail.git <br />
Video: https://www.youtube.com/watch?v=R7OlR-JEpaU

# **TEAM INFORMATION**

![alt text](Screenshot 2026-01-19 172335.png)

| Student ID | Full name       | Git account | Contribution                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | Contribution percentage (100% total) | Expected total points | Final total points |
| :--------- | :-------------- | :---------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------- | :-------------------- | :----------------- |
| 22120376   | Nguyễn Đức Toàn | DucToan137  | - Xây dựng giao diện Đăng ký, Đăng nhập.<br />- Xây dựng giao diện List View, Kanban View.<br />- Xây dựng tính năng Snoozed Email (Backend, Frontend). <br />- Xây dựng tính năng gửi mail (cc, bcc, reply, forward, đính kèm file,...) ở Frontend.<br /> - Xây dựng tính năng Thêm, Xóa, Đổi tên cột trong giao diện Kanban View (Frontend).<br />- Xây dựng tính năng Search, Sort, Filter trong giao diện Kanban View (Frontend).                                                                                                                                                                                                                                                                | 33%                                  | 10                    |                    |
| 22120433   | Lê Quang Vinh   | DINH1022    | - Xây dựng chức năng đăng nhập Google<br /> - Xây dựng chức năng tóm tắt email (Backend, Frontend) <br />- Xây dựng tính năng Sort, Filter trong giao diện List View (Frontend) <br />- Xây dựng giao diện cho các tính năng Fuzzy Search, Semantic Search, Auto Suggestion (Frontend)<br /> - Deploy ứng dụng (Frontend, Backend)| 33%                                  | 10                    |                    |
| 22120434   | Lê Thành Vinh   | LTVINH24    | - Xây dựng cơ bản giao diện List View 3 Columns (Mailboxes, EmailList, EmailDetail)<br /> - Xây dựng Proxy Mail (Backend): fetch email từ Gmail, phân trang email, hiển thị chi tiết email, danh sách các mailboxes, modify label, gửi mail (to, cc, bcc, reply, forward,…). <br /> - Xây dựng cơ bản giao diện Kanban View với các KanbanColumn, KanbanCard, thao tác Drag & Drop card giữa các column. <br /> - Xây dựng tính năng Fuzzy Search (Backend) <br /> - Xây dựng tính năng Sematic Search (Backend) <br /> - Xây dựng API quản lý KanbanColumn (create, delete, rename). <br /> - Xây dựng các tính năng nâng cao: Keyboard navigation, Multi-tab logout sync, Dockerfile cho frontend. | 34%                                  | 10                    |                    |

# **FEATURE LIST**

**Project:** React Email Client with Gmail Integration & AI-Powered Kanban

Students must input minus points to every uncompleted feature in the SE column.
\*SE: Self-evaluation

\*TR: Teacher review

| ID     | Features                                   | Grade     |          |          | Notes                                                                                                                             |
| ------ | :----------------------------------------- | --------- | :------- | :------- | :-------------------------------------------------------------------------------------------------------------------------------- |
|        |                                            | **Point** | **SE\*** | **TR\*** |                                                                                                                                   |
| **1**  | **Overall requirements**                   |           |          |          |                                                                                                                                   |
|        | User-centered design                       | \-5       | 5        |          | Built with user experience in mind. Kanban-style email management, AI summarization, semantic search for efficient email workflow |
|        | Database design                            | \-1       | 1        |          | Database with tables: users, emails, email_vectors, kanban_columns, snooze_schedules, labels                                      |
|        | Database mock data                         | \-1       | 1        |          | Sample emails, kanban configurations, and test data                                                                               |
|        | Website layout                             | \-2       | 2        |          | 3-column layout: mailbox list, email list, email detail. Kanban board view                                                        |
|        | Website architect                          | \-3       | 3        |          | React SPA with backend API. Clear separation of concerns. OAuth2 flow, token handling                                             |
|        | Website stability and compatibility        | \-4       | 4        |          | Responsive design, tested on Chrome, Safari, Firefox, and Edge                                                                    |
|        | Document                                   | \-2       | 2        |          | README with setup guide, API endpoints, Google OAuth setup, token storage explanation, security considerations                    |
|        | Demo video                                 | \-5       | 5        |          | Video demonstrating: Gmail login, inbox sync, Kanban board, AI summarization, semantic search, drag-drop                          |
|        | Publish to public hosts                    | \-1       | 1        |          | Frontend deployed (Netlify/Vercel), Backend deployed (Render/Railway/Cloud Run)                                                   |
|        | Development progress is recorded in Github | \-7       | 7        |          | Git history with meaningful commits, branches for features, pull requests                                                         |
| **2**  | **Authentication & Token Management**      |           |          |          |                                                                                                                                   |
|        | Google OAuth 2.0 integration               | \-0.5     | 0.5      |          | Login with Google, grant Gmail access permissions                                                                                 |
|        | Authorization Code flow                    | \-0.5     | 0.5      |          | Backend exchanges code for tokens, stores refresh token securely                                                                  |
|        | Token storage & security                   | \-0.5     | 0.5      |          | Access token in-memory (frontend), refresh token server-side only                                                                 |
|        | Automatic token refresh                    | \-0.5     | 0.5      |          | Backend refreshes expired access tokens automatically                                                                             |
|        | Concurrency handling                       | \-0.25    | 0.25     |          | Single refresh request when multiple 401s occur                                                                                   |
|        | Forced logout on invalid refresh           | \-0.25    | 0.25     |          | Clear tokens and logout if refresh token fails                                                                                    |
|        | Logout & token cleanup                     | \-0.25    | 0.25     |          | Clear all tokens server-side and client-side on logout                                                                            |
| **3**  | **Email Synchronization & Display**        |           |          |          |                                                                                                                                   |
|        | Fetch emails from Gmail                    | \-0.5     | 0.5      |          | Use Gmail API to fetch inbox emails                                                                                               |
|        | Email list with pagination                 | \-0.25    | 0.25     |          | Paginated/virtualized email list                                                                                                  |
|        | Email detail view                          | \-0.25    | 0.25     |          | Full email content with HTML/plain text support                                                                                   |
|        | Mailbox/Labels list                        | \-0.25    | 0.25     |          | Display Gmail labels/folders in sidebar                                                                                           |
|        | Open in Gmail link                         | \-0.25    | 0.25     |          | Button/icon to open email in Gmail                                                                                                |
| **4**  | **Kanban Board Interface**                 |           |          |          |                                                                                                                                   |
|        | Kanban board layout                        | \-0.5     | 0.5      |          | Board with columns: Inbox, To Do, Done, etc.                                                                                      |
|        | Email cards display                        | \-0.25    | 0.25     |          | Cards showing sender, subject, snippet                                                                                            |
|        | Drag-and-drop between columns              | \-0.5     | 0.5      |          | Drag cards to change email status                                                                                                 |
|        | Status persistence                         | \-0.25    | 0.25     |          | Status changes saved and persisted                                                                                                |
|        | Dynamic Kanban Configuration               |           |          |          |                                                                                                                                   |
|        | › Settings interface                       | \-0.25    | 0.25     |          | Modal/page to create, rename, delete columns                                                                                      |
|        | › Configuration persistence                | \-0.25    | 0.25     |          | Custom columns saved and restored after reload                                                                                    |
|        | › Gmail label mapping                      | \-0.5     | 0.5      |          | Columns map to Gmail labels, moving cards syncs labels                                                                            |
| **5**  | **Snooze Mechanism**                       |           |          |          |                                                                                                                                   |
|        | Select snooze time                         | \-0.25    | 0.25     |          | Choose snooze duration (Tomorrow, Next week, custom)                                                                              |
|        | Hide snoozed emails                        | \-0.25    | 0.25     |          | Email disappears from Kanban after snooze                                                                                         |
|        | Auto-return on schedule                    | \-0.5     | 0.5      |          | Email automatically returns to board at scheduled time                                                                            |
| **6**  | **AI Features**                            |           |          |          |                                                                                                                                   |
|        | AI Summarization                           |           |          |          |                                                                                                                                   |
|        | › Backend summarization API                | \-0.5     | 0.5      |          | LLM integration (OpenAI/Gemini) to summarize email content                                                                        |
|        | › Summary UI on cards                      | \-0.25    | 0.25     |          | Display 2-3 line summary on email cards                                                                                           |
|        | Text Embedding                             |           |          |          |                                                                                                                                   |
|        | › Embedding generation                     | \-0.5     | 0.5      |          | Generate vector embeddings for emails using embedding model                                                                       |
|        | › Vector database storage                  | \-0.5     | 0.5      |          | Store embeddings in vector database (pgvector, etc.)                                                                              |
| **7**  | **Search Features**                        |           |          |          |                                                                                                                                   |
|        | Fuzzy Search (Backend)                     |           |          |          |                                                                                                                                   |
|        | › Typo tolerance                           | \-0.5     | 0.5      |          | "marketng" finds "marketing"                                                                                                      |
|        | › Partial matches                          | \-0.5     | 0.5      |          | "Nguy" finds "Nguyen Van A"                                                                                                       |
|        | › Relevance ranking                        | \-0.25    | 0.25     |          | Best matches ranked first                                                                                                         |
|        | Fuzzy Search UI (Frontend)                 |           |          |          |                                                                                                                                   |
|        | › Search bar integration                   | \-0.25    | 0.25     |          | Search bar in header/main UI                                                                                                      |
|        | › Search results as cards                  | \-0.25    | 0.25     |          | Results displayed as email cards with sender, subject, snippet                                                                    |
|        | › Loading/empty/error states               | \-0.25    | 0.25     |          | Handle UX states properly                                                                                                         |
|        | › Navigation back to main view             | \-0.25    | 0.25     |          | Clear way to return to Kanban view                                                                                                |
|        | Semantic Search                            |           |          |          |                                                                                                                                   |
|        | › Conceptual relevance search              | \-0.5     | 0.5      |          | Query "money" finds "invoice", "price", "salary"                                                                                  |
|        | › Semantic search API endpoint             | \-0.25    | 0.5      |          | POST /api/search/semantic endpoint                                                                                                |
|        | Search Auto-Suggestion                     |           |          |          |                                                                                                                                   |
|        | › Type-ahead dropdown                      | \-0.25    | 0.25     |          | Dropdown appears while typing with 3-5 suggestions                                                                                |
|        | › Suggestions from contacts/keywords       | \-0.25    | 0.25     |          | Suggestions populated from sender names, subject keywords                                                                         |
|        | › Trigger search on selection              | \-0.25    | 0.25     |          | Clicking suggestion triggers semantic search                                                                                      |
| **8**  | **Filtering & Sorting**                    |           |          |          |                                                                                                                                   |
|        | Sort by date (newest/oldest)               | \-0.25    |          |          | At least two sorting options                                                                                                      |
|        | Filter by unread                           | \-0.25    | 0.25     |          | Show only unread emails                                                                                                           |
|        | Filter by attachments                      | \-0.25    | 0.25     |          | Show only emails with attachments                                                                                                 |
|        | Real-time filter updates                   | \-0.25    | 0.25     |          | Changes apply immediately without page reload                                                                                     |
| **9**  | **Email Actions**                          |           |          |          |                                                                                                                                   |
|        | Mark as read/unread                        | \-0.25    | 0.25     |          | Toggle read status via Gmail API                                                                                                  |
|        | Compose modal                              | \-0.25    | 0.25     |          | Modal to compose new email                                                                                                        |
|        | Reply/Forward flow                         | \-0.25    | 0.25     |          | Reply to and forward emails                                                                                                       |
|        | Send via Gmail API                         | \-0.25    | 0.25     |          | Send emails through Gmail API                                                                                                     |
|        | View attachments                           | \-0.25    | 0.25     |          | Display attachments in email detail                                                                                               |
|        | Download attachments                       | \-0.25    | 0.25     |          | Download attachment files                                                                                                         |
|        | Delete emails                              | \-0.25    | 0.25     |          | Move to trash via Gmail API                                                                                                       |
| **10** | **Advanced features**                      |           |          |          |                                                                                                                                   |
|        | Gmail Push Notifications                   | 0.25      | 0        |          | Real-time inbox updates via Gmail watch + Pub/Sub                                                                                 |
|        | Multi-tab logout sync                      | 0.25      | 0.25     |          | BroadcastChannel for logout sync across tabs                                                                                      |
|        | Offline caching                            | 0.25      | 0        |          | IndexedDB + stale-while-revalidate for emails                                                                                     |
|        | Keyboard navigation                        | 0.25      | 0.25     |          | Navigate emails with keyboard shortcuts                                                                                           |
|        | Dockerize your project                     | 0.25      | 0.25     |          | Docker containers for backend, frontend                                                                                           |
|        | CI/CD                                      | 0.25      | 0.25     |          | Automated testing and deployment pipeline                                                                                         |

# **GIT HISTORY**

## **Contributors**

| Username   | Commits            | Additions | Deletions |
| :--------- | :----------------- | :-------- | :-------- |
| DucToan137 | \<git_username_1\> |           |           |
| DINH1022   | \<git_username_2\> |           |           |
| LTVINH24   | \<git_username_3\> |           |           |

## **Commits**

_List significant commits here with format:_

| Date       | Author     | Commit Message                                                | Files Changed | Repository |
| :--------- | :--------- | :------------------------------------------------------------ | :------------ | :--------- |
| 19-11-2025 | DINH1022   | normal auth                                                   | 1             | Backend    |
| 27-11-2025 | LTVINH24   | feat: implement get list email and get email detail           | 10            | Backend    |
| 01-12-2025 | DINH1022   | google auth                                                   | 7             | Backend    |
| 02-12-2025 | DucToan137 | feat(mail): stream attachments                                | 2             | Backend    |
| 09-12-2025 | DucToan137 | feat(snooze): add workflow Email entity, snooze email         | 12            | Backend    |
| 10-12-2025 | DINH1022   | summary mail                                                  | 3             | Backend    |
| 14-01-2026 | LTVINH24   | feat: CURD kanban column for user                             | 7             | Backend    |
| 18-11-2025 | LTVINH24   | initial project and mock email dashboard ui                   | 39            | Frontend   |
| 02-12-2025 | DucToan137 | feat(email): lazy-load thread details + skeleton UI           | 4             | Frontend   |
| 03-12-2025 | DINH1022   | oauth flow                                                    | 4             | Frontend   |
| 09-12-2025 | LTVINH24   | feat: create kanban view layout                               | 5             | Frontend   |
| 09-12-2025 | DucToan137 | feat(snooze): connect services                                | 8             | Frontend   |
| 17-12-2025 | DINH1022   | feat : sort email                                             | 1             | Frontend   |
| 23-12-2025 | DucToan137 | feat(search): implement Semantic search and integrate service | 6             | Frontend   |
| 18-01-2026 | DucToan137 | feat: Multi-tab logout sync                                   | 2             | Frontend   |

---

# **PROJECT SUMMARY**

## System Overview

**React Email Client with Gmail Integration** is a web-based email client that transforms Gmail into a Kanban-style productivity tool:

- Gmail OAuth2 authentication with secure token handling
- Kanban board interface for email workflow management (Inbox, To Do, Done)
- AI-powered email summarization using LLM (OpenAI/Gemini)
- Snooze mechanism to temporarily hide and auto-return emails
- Fuzzy search with typo tolerance and partial matching
- Semantic search using vector embeddings for conceptual relevance
- Dynamic Kanban configuration with Gmail label mapping
- Full email actions: compose, reply, forward, delete, attachments

## Technology Stack

- **Architecture:** React SPA + Backend API (Spring boot)
- **Frontend:** React, react-window (virtualization), drag-and-drop library
- **Backend:** Java + Spring boot
- **Database:** PostgreSQL with pgvector for embeddings
- **Authentication:** Google OAuth2 (Authorization Code flow)
- **AI/ML:** Gemini API for summarization and embeddings
- **Email:** Gmail REST API
- **Vector Search:** pgvector
- **Deployment:** Frontend (Vercel), Backend (Render)

## API Endpoints

| Endpoint                                          | Description                                  |
| :------------------------------------------------ | :------------------------------------------- |
| POST /auth/login                                  | Login with Username & Password               |
| POST /auth/register                               | Register with Username & Password            |
| POST /auth/logout                                 | Clear all tokens and logout                  |
| POST /auth/refresh                                | Refresh Token                                |
| POST /auth/me                                     | Get My Information                           |
| POST /auth/google/authorize                       | Redirect user to Google authorization screen |
| POST /auth/google/callback                        | Exchange Google auth code for tokens         |
| GET /mailboxes                                    | List Gmail labels/folders                    |
| GET /mailboxes/:id/emails                         | List emails in mailbox with pagination       |
| POST /mailboxes                                   | Create label                                 |
| PATCH /mailboxes                                  | Update label                                 |
| DELETE /mailboxes                                 | Delete label                                 |
| GET /emails/:id                                   | Get email detail                             |
| POST /emails/send                                 | Send new email                               |
| POST emails/:id/modify                            | Mark read/unread, star, delete               |
| GET /emails/:messageId/attachments/:attachmentsId | Stream attachment                            |
| POST /emails/:id/snooze                           | Snooze Email                                 |
| GET /emails/search/fuzzy                          | Fuzzy search emails                          |
| GET /emails/search/semantic                       | Semantic search with embeddings              |
| GET /emails/:id/summary                           | Summary email with AI                        |
| GET /kanban/columns                               | Get Kanban column configuration              |
| DELETE /kanban/columns/:id                        | Delete kanban column                         |

## Key User Flows

1. **Authentication:** Google Sign-In → Backend token exchange → Session created → Redirect to Kanban
2. **Email Sync:** Login → Fetch Gmail inbox → Display as Kanban cards → Real-time updates
3. **Kanban Workflow:** View cards → Drag to columns → Status synced → Gmail labels updated
4. **AI Summary:** Email synced → LLM summarizes → Summary displayed on card
5. **Semantic Search:** User types query → Embedding generated → Vector search → Related emails returned
6. **Snooze:** Select email → Choose snooze time → Email hidden → Auto-returns at scheduled time

## Development Timeline

| Week   | Focus                                        | Key Deliverables                                          |
| :----- | :------------------------------------------- | :-------------------------------------------------------- |
| Week 1 | Basic Application                            | Gmail OAuth, email sync, Kanban interface with cards      |
| Week 2 | Core Workflow & AI                           | Drag-and-drop, snooze mechanism, AI summarization         |
| Week 3 | Fuzzy Search & Filtering                     | Fuzzy search (BE+FE), sorting, filtering on Kanban        |
| Week 4 | Semantic Search & Config                     | Vector embeddings, semantic search, dynamic Kanban config |
| Week 5 | Advanced Feature & Deployment & Deliverables | Testing, deployment, demo video                           |

## Security Considerations

- **Access Token:** Stored in-memory on frontend only
- **Refresh Token:** Stored server-side in secure datastore (never exposed to frontend)
- **OAuth Flow:** Authorization Code flow for security
- **Token Refresh:** Handled server-side with concurrency protection
- **Logout:** Clears all tokens and optionally revokes OAuth refresh token

---

## Note:

All evidence for the self-evaluated features is demonstrated in the demo video.

## Total self-assessment point: 10/10
