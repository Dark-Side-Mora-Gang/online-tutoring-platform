# online-tutoring-platform

```
online-tutoring-platform/
│
├── backend/
│    │
│    ├── api-gateway/
│    │   ├── src/
│    │   │   ├── main.ts                  # Bootstrap NestJS app
│    │   │   ├── app.module.ts            # Root module
│    │   │   ├── config/                  # Config for Redis, CORS, rate-limiter, etc.
│    │   │   │   ├── redis.config.ts
│    │   │   │   └── gateway.config.ts
│    │   │   ├── modules/                 # Feature modules (Auth, Tutor, Booking, Payment, Video)
│    │   │   │   ├── auth.module.ts
│    │   │   │   ├── tutor.module.ts
│    │   │   │   ├── booking.module.ts
│    │   │   │   ├── payment.module.ts
│    │   │   │   └── video.module.ts
│    │   │   ├── guards/                  # Global JWT guard
│    │   │   ├── interceptors/            # Logging, response formatting
│    │   │   └── middlewares/             # Rate limiting, request logging
│    │   └── Dockerfile
│    │
│    ├── auth-service/
│    │   ├── src/
│    │   │   ├── main.ts
│    │   │   ├── app.module.ts
│    │   │   ├── auth/                     # Auth module
│    │   │   │   ├── auth.controller.ts
│    │   │   │   ├── auth.service.ts
│    │   │   │   ├── jwt.strategy.ts
│    │   │   │   ├── auth.module.ts
│    │   │   │   └── dto/
│    │   │   ├── users/                    # User module
│    │   │   │   ├── users.service.ts
│    │   │   │   ├── users.repository.ts
│    │   │   │   └── users.module.ts
│    │   │   ├── prisma/                   # DB access
│    │   │   │   ├── prisma.module.ts
│    │   │   │   └── schema.prisma
│    │   │   └── redis/
│    │   │       └── redis.module.ts       # Session / token storage
│    │   └── Dockerfile
│    │
│    ├── tutor-service/
│    │   ├── src/
│    │   │   ├── main.ts
│    │   │   ├── app.module.ts
│    │   │   ├── tutor/
│    │   │   │   ├── tutor.controller.ts
│    │   │   │   ├── tutor.service.ts
│    │   │   │   └── dto/
│    │   │   ├── availability/
│    │   │   │   └── availability.service.ts
│    │   │   ├── search/
│    │   │   │   ├── elastic.service.ts
│    │   │   │   └── elastic.module.ts
│    │   │   └── prisma/
│    │   │       └── schema.prisma
│    │   └── Dockerfile
│    │
│    ├── booking-service/
│    │   ├── src/
│    │   │   ├── main.ts
│    │   │   ├── app.module.ts
│    │   │   ├── booking/
│    │   │   │   ├── booking.controller.ts
│    │   │   │   ├── booking.service.ts
│    │   │   │   └── dto/
│    │   │   ├── events/                   # RabbitMQ events / listeners
│    │   │   │   └── booking.events.ts
│    │   │   └── prisma/
│    │   │       └── schema.prisma
│    │   └── Dockerfile
│    │
│    ├── payment-service/
│    │   ├── src/
│    │   │   ├── main.ts
│    │   │   ├── app.module.ts
│    │   │   ├── payment/
│    │   │   │   ├── payment.controller.ts
│    │   │   │   ├── payment.service.ts
│    │   │   │   └── dto/
│    │   │   ├── stripe/
│    │   │   │   └── stripe.module.ts
│    │   │   └── prisma/
│    │   │       └── schema.prisma
│    │   └── Dockerfile
│    │
│    └── video-session-service/
│        ├── src/
│        │   ├── main.ts
│        │   ├── app.module.ts
│        │   ├── video/
│        │   │   ├── video.controller.ts
│        │   │   ├── video.service.ts
│        │   │   └── dto/
│        │   └── provider/
│        │       ├── jitsi.provider.ts
│        │       └── zoom.provider.ts
│        └── Dockerfile
│
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