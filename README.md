# JournalStack

> A full-stack mobile journal built with React Native, Express, and PostgreSQL.

![React Native](https://img.shields.io/badge/React_Native-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)

## Overview

JournalStack is a mobile journaling project that connects a React Native interface to a small Express API and PostgreSQL database. It helped me move beyond local-only state and understand how screens, HTTP requests, relational data, and user-specific records work together.

## Features

- Register and sign in with a user account
- Store the active user ID locally
- Create journal entries with a title and body
- Load entries belonging to the signed-in user
- Open individual entry detail screens
- Display a motivational quote from an external API

## Stack

| Layer | Technology |
| --- | --- |
| Mobile frontend | React Native, Expo, Expo Router |
| Language | TypeScript, JavaScript |
| API | Node.js, Express |
| Database | PostgreSQL, node-postgres |
| Local session | AsyncStorage |

## API surface

```text
POST /giris
POST /kayit
POST /gunluk-ekle
GET  /gunlukleri-getir/:kullanici_id
```

## Data model

The database uses a one-to-many relationship: one user can own multiple journal entries, and every entry references its owner through `kullanici_id`.

## Run locally

```bash
git clone https://github.com/mustafasenyusz/JournalStack.git
cd JournalStack
npm install
node database.js
npx expo start
```

Create the PostgreSQL tables described by the API code, then update the local database connection and client API base URL.

## Engineering roadmap

- Move connection values into environment configuration
- Add password hashing and token-based sessions
- Add update and delete operations for entries
- Introduce schema migrations, validation, and API tests

JournalStack documents my progress on the backend and database side while keeping a mobile-first frontend at the center.

## Developer

Built by [Mustafa Şenyüz](https://github.com/mustafasenyusz).
