# PFE
# NexaCRM — Project Architecture
# PFE 2026 | SOTETEL

```
code/
│
├── 📄 README.md
├── 📄 .gitignore
├── 📄 docker-compose.yml
│
│
├── 📁 nexacrm_backend_django/          ← Django REST API (Python 3.12)
│   │
│   ├── 📄 manage.py
│   ├── 📄 pyproject.toml               ← UV dependencies
│   ├── 📄 .env                         ← DB credentials, JWT secret, etc.
│   ├── 📄 .env.example
│   ├── 📄 Dockerfile
│   ├── 📄 requirements.txt
│   │
│   ├── 📁 nexacrm/                     ← Django project config
│   │   ├── __init__.py
│   │   ├── settings/
│   │   │   ├── base.py
│   │   │   ├── development.py
│   │   │   └── production.py
│   │   ├── urls.py
│   │   ├── wsgi.py
│   │   └── asgi.py
│   │
│   ├── 📁 apps/                        ← All Django apps
│   │   │
│   │   ├── 📁 authentication/          ← JWT login, register, permissions
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 users/                   ← Team & client users, roles (RBAC)
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 clients/                 ← Client companies + contacts
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 leads/                   ← Lead pipeline + kanban
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 projects/                ← Projects, milestones, Gantt
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 tasks/                   ← Tasks, assignments, recurring
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 invoices/                ← Invoices, estimates, line items
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 payments/                ← Payments, Stripe, PayPal
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 expenses/                ← Business expenses + receipts
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 tickets/                 ← Support tickets + replies
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 contracts/               ← Contracts + proposals
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 calendar/                ← Events, reminders
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   ├── urls.py
│   │   │   └── tests.py
│   │   │
│   │   ├── 📁 knowledgebase/           ← KB articles + categories
│   │   │   ├── models.py
│   │   │   ├── views.py
│   │   │   ├── serializers.py
│   │   │   └── urls.py
│   │   │
│   │   ├── 📁 reports/                 ← Financial + activity reports
│   │   │   ├── views.py
│   │   │   └── urls.py
│   │   │
│   │   └── 📁 notifications/           ← In-app + email notifications
│   │       ├── models.py
│   │       ├── views.py
│   │       └── urls.py
│   │
│   ├── 📁 core/                        ← Shared utilities
│   │   ├── permissions.py
│   │   ├── pagination.py
│   │   ├── utils.py
│   │   └── exceptions.py
│   │
│   └── 📁 media/                       ← Uploaded files (avatars, receipts)
│
│
├── 📁 nexacrm_frontend_vue/            ← Vue 3 + Vite + TypeScript
│   │
│   ├── 📄 index.html
│   ├── 📄 vite.config.ts
│   ├── 📄 package.json
│   ├── 📄 tsconfig.json
│   ├── 📄 .env
│   ├── 📄 .env.example
│   ├── 📄 Dockerfile
│   │
│   ├── 📁 public/
│   │   └── favicon.ico
│   │
│   └── 📁 src/
│       ├── 📄 main.ts
│       ├── 📄 App.vue
│       │
│       ├── 📁 assets/                  ← Fonts, images, global CSS
│       │   ├── main.css
│       │   └── fonts/
│       │
│       ├── 📁 components/              ← Reusable UI components
│       │   ├── layout/
│       │   │   ├── AppSidebar.vue
│       │   │   ├── AppTopbar.vue
│       │   │   └── AppLayout.vue
│       │   ├── ui/
│       │   │   ├── BaseButton.vue
│       │   │   ├── BaseCard.vue
│       │   │   ├── BaseModal.vue
│       │   │   ├── BaseTable.vue
│       │   │   ├── BaseBadge.vue
│       │   │   ├── BaseInput.vue
│       │   │   └── BaseToast.vue
│       │   ├── charts/
│       │   │   ├── BarChart.vue
│       │   │   ├── DonutChart.vue
│       │   │   └── LineChart.vue
│       │   └── kanban/
│       │       ├── KanbanBoard.vue
│       │       └── KanbanCard.vue
│       │
│       ├── 📁 views/                   ← One folder per module
│       │   ├── auth/
│       │   │   ├── LoginView.vue
│       │   │   └── ForgotPasswordView.vue
│       │   ├── dashboard/
│       │   │   └── DashboardView.vue
│       │   ├── clients/
│       │   │   ├── ClientsView.vue
│       │   │   └── ClientDetailView.vue
│       │   ├── leads/
│       │   │   ├── LeadsView.vue          ← Kanban pipeline
│       │   │   └── LeadDetailView.vue
│       │   ├── projects/
│       │   │   ├── ProjectsView.vue
│       │   │   └── ProjectDetailView.vue
│       │   ├── tasks/
│       │   │   └── TasksView.vue
│       │   ├── invoices/
│       │   │   ├── InvoicesView.vue
│       │   │   └── InvoiceDetailView.vue
│       │   ├── payments/
│       │   │   └── PaymentsView.vue
│       │   ├── expenses/
│       │   │   └── ExpensesView.vue
│       │   ├── tickets/
│       │   │   ├── TicketsView.vue
│       │   │   └── TicketDetailView.vue
│       │   ├── contracts/
│       │   │   └── ContractsView.vue
│       │   ├── calendar/
│       │   │   └── CalendarView.vue
│       │   ├── reports/
│       │   │   └── ReportsView.vue
│       │   └── settings/
│       │       └── SettingsView.vue
│       │
│       ├── 📁 router/                  ← Vue Router routes
│       │   └── index.ts
│       │
│       ├── 📁 stores/                  ← Pinia state management
│       │   ├── auth.ts
│       │   ├── clients.ts
│       │   ├── leads.ts
│       │   ├── projects.ts
│       │   ├── invoices.ts
│       │   ├── tickets.ts
│       │   └── notifications.ts
│       │
│       ├── 📁 composables/             ← Reusable Vue logic
│       │   ├── useApi.ts
│       │   ├── useAuth.ts
│       │   ├── usePagination.ts
│       │   └── useToast.ts
│       │
│       ├── 📁 services/                ← Axios API calls
│       │   ├── api.ts                  ← Axios instance + interceptors
│       │   ├── authService.ts
│       │   ├── clientService.ts
│       │   ├── leadService.ts
│       │   ├── projectService.ts
│       │   ├── invoiceService.ts
│       │   └── ticketService.ts
│       │
│       └── 📁 types/                   ← TypeScript interfaces
│           ├── client.ts
│           ├── lead.ts
│           ├── invoice.ts
│           └── user.ts
│
│
├── 📁 database/                        ← SQL files
│   ├── nexacrm_postgresql.sql          ← Full schema (PostgreSQL)
│   └── seeds/                          ← Test data
│       └── demo_data.sql
│
│
└── 📁 docs/                            ← Project documentation
    ├── cahier_de_charge.pdf
    ├── ch2_conception.pdf
    ├── ch3_installation.pdf
    └── api/
        └── openapi.yaml                ← Swagger/OpenAPI docs
```
