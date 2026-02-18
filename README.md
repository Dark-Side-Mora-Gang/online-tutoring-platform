# online-tutoring-platform

```
online-tutoring-platform/
│
├── backend/                    # All microservices + API Gateway
│   ├── api-gateway/            # Single entry point, route traffic
│   │   ├── src/
│   │   │   ├── main.ts
│   │   │   ├── app.module.ts
│   │   │   ├── config/         # Redis, rate-limit, CORS, etc.
│   │   │   └── middlewares/
│   │   └── Dockerfile
│   │
│   ├── auth-service/           # User auth + JWT + roles
│   │   ├── src/
│   │   │   ├── main.ts
│   │   │   ├── auth/
│   │   │   ├── users/
│   │   │   └── prisma/
│   │   └── Dockerfile
│   │
│   ├── tutor-service/          # Tutor profiles, availability, ratings
│   │   ├── src/
│   │   │   ├── tutor/
│   │   │   ├── availability/
│   │   │   └── search/         # Elasticsearch integration
│   │   └── Dockerfile
│   │
│   ├── booking-service/        # Session booking & management
│   │   ├── src/
│   │   │   ├── booking/
│   │   │   └── events/
│   │   └── Dockerfile
│   │
│   ├── payment-service/        # Stripe / Payment handling
│   │   ├── src/
│   │   │   ├── payment/
│   │   │   └── stripe/
│   │   └── Dockerfile
│   │
│   └── video-session-service/  # Jitsi/Zoom integration
│       ├── src/
│       │   ├── video/
│       │   └── provider/
│       └── Dockerfile
│
├── libs/                       # Shared code across services
│   ├── common/                  # DTOs, Guards, Decorators, Interceptors, Filters, Enums
│   ├── database/                # Prisma schema + migrations + helpers
│   └── messaging/               # RabbitMQ modules + events contracts
│
├── web/                         # Next.js frontend
│   ├── pages/
│   ├── components/
│   ├── services/                # API calls (call API Gateway)
│   ├── hooks/
│   └── public/
│
├── mobile/                      # Flutter app
│   ├── lib/
│   │   ├── screens/
│   │   ├── widgets/
│   │   ├── services/            # API calls (call API Gateway)
│   │   ├── models/
│   │   └── utils/
│   └── pubspec.yaml
│
├── infrastructure/              # Docker + K8s + Nginx + CI/CD
│   ├── docker-compose.yml
│   ├── k8s/
│   └── nginx/
│
├── docs/                        # Architecture docs, ER diagrams, API contracts
│
├── .env                         # Environment variables for local dev
├── package.json
└── README.md

```
