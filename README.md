# BackEnd Project - Use Actix and SurrealDB to build a RESTful API

[![Actix](https://img.shields.io/badge/Actix-2.0.0-blue.svg)](https://actix.rs/)
[![SurrealDB](https://img.shields.io/badge/SurrealDB-0.1.0-blue.svg)](https://surrealdb.com)

## Project Description

This project is a RESTful API built with Actix and SurrealDB. It is a simple API that allows users to create, read, update, and delete users and items.

## Project Structure

The project is structured as follows:

```bash
.
├── Cargo.lock
├── Cargo.toml
├── README.md
├── src
│   ├── api
│   │   ├── item_api.rs
│   │   └── user_api.rs
│   ├── model
│   │   ├── item_model.rs
│   │   └── user_model.rs
│   ├── utils
│   │   ├── macros.rs
│   │   └── try_forms.rs
│   ├── error.rs
│   ├── main.rs
│   └── prelude.rs
└── tests
    ├── integration
    │   ├── item_api_test.rs
    │   └── user_api_test.rs
    └── unit
        ├── item_test.rs
        └── user_test.rs
```

## Project Setup

### Prerequisites

- Rust

### Installation

1. Clone the repository

```bash
git clone
```

2. Install dependencies

```bash
cargo build
```

3. Run the project

```bash
cargo run
```

## API Documentation

### User API

#### Get all Users

```bash
curl --location --request GET 'http://localhost:8080/users'
```

#### Create User

```bash
curl --location --request POST 'http://localhost:8080/users' \
--header 'Content-Type: application/json' \
--data-raw '{
    "cid": "1",
    "public_key": "0x1234567890",
    "private_key": "0x1234567890",
    "name": "John Doe",
    "version": 1,
    "avatar": "https://example.com/avatar.png",
    "email": "john.doe@example.example",
    "creation_date": "2020-01-01T00:00:00Z",
    "online_state": "online",
    "follow_ids": [
        "2",
        "3"
    ],
    "is_visible": true,
    "is_inactive": false,
  }'
```

#### Get User

```bash
curl --location --request GET 'http://localhost:8080/users/1'
```

#### Update User

```bash
curl --location --request PUT 'http://localhost:8080/users/1' \
--header 'Content-Type: application/json' \
--data-raw '{
    "cid": "1",
    "public_key": "0x1234567890",
    "private_key": "0x1234567890",
    "name": "John Doe",
    "version": 1,
    "avatar": "https://example.com/avatar.png",
    "email": "john.doe@example.example",
    "creation_date": "2020-01-01T00:00:00Z",
    "online_state": "online",
    "follow_ids": [
        "2",
        "3"
    ],
    "is_visible": true,
    "is_inactive": false,
  }'
```

#### Delete User

```bash
curl --location --request DELETE 'http://localhost:8080/users/1'
```

### Item API

#### Get all Items

```bash
curl --location --request GET 'http://localhost:8080/items'
```

#### Create Item

```bash
curl --location --request POST 'http://localhost:8080/items' \
--header 'Content-Type: application/json' \
--data-raw '{
    "cid": "1",
    "name": "Item 1",
    "owner_id": "1",
    "version": 1,
    "content": [ "1", "2", "3" ],
    "creation_date": "2020-01-01T00:00:00Z",
    "edit_date": "2020-01-01T00:00:00Z",
    "tag_ids": [
        "2",
        "3"
    ],
    "follower_ids": [
        "2",
        "3"
    ],
    "is_visible": true,
    "is_archived": false,
  }'
```

#### Get Item

```bash
curl --location --request GET 'http://localhost:8080/items/1'
```

#### Update Item

```bash
curl --location --request PUT 'http://localhost:8080/items/1' \
--header 'Content-Type: application/json' \
--data-raw '{
    "cid": "1",
    "name": "Item 1",
    "owner_id": "1",
    "version": 1,
    "content": [ "1", "2", "3" ],
    "creation_date": "2020-01-01T00:00:00Z",
    "edit_date": "2020-01-01T00:00:00Z",
    "tag_ids": [
        "2",
        "3"
    ],
    "follower_ids": [
        "2",
        "3"
    ],
    "is_visible": true,
    "is_archived": false,
  }'
```

#### Delete Item

```bash
curl --location --request DELETE 'http://localhost:8080/items/1'
```

## Testing

[soon]

## License

[MIT](https://choosealicense.com/licenses/mit/)
