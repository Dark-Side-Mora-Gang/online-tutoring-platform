# online-tutoring-platform

```
tutoring-platform/
│
├── apps/
│   ├── api-gateway/
│   ├── auth-service/
│   ├── tutor-service/
│   ├── booking-service/
│   ├── payment-service/
│   ├── video-session-service/
│   └── frontend/ (Next.js)
│
├── libs/
│   ├── common/
│   │   ├── dto/
│   │   ├── guards/
│   │   ├── decorators/
│   │   ├── interceptors/
│   │   ├── filters/
│   │   └── constants/
│   │
│   ├── database/
│   │   ├── prisma/
│   │   └── migrations/
│   │
│   └── messaging/
│       ├── rabbitmq.module.ts
│       └── events/
│
├── docker/
│   ├── docker-compose.yml
│   └── k8s/
│
├── .env
└── package.json
```
