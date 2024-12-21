# Coozila Apps - DragonflyDB Cluster

## Coozila Package for Memcached Cluster with DragonFly

### What is Memcached?

Memcached is a high-performance, distributed memory object caching system, generic in nature, but intended for use in speeding up dynamic web applications by alleviating database load. It is designed to cache data and reduce the number of times a database must be queried, thereby improving the speed and performance of applications.

### What is DragonFly?

DragonFly is a distributed database that provides a powerful, scalable, and fault-tolerant solution designed for high availability and performance. It is optimized for use cases that require efficient data retrieval and storage, making it an ideal complement to Memcached in clustered environments.

### Overview of Memcached and DragonFly

Memcached and DragonFly work together to provide a robust caching and database solution for high-demand applications. By utilizing Memcached for caching frequently accessed data, applications can significantly reduce response times and database load. DragonFly, with its distributed architecture, ensures that data is stored reliably and can be accessed quickly, supporting the demands of modern web applications.

---

## Copyright

```
Copyright (C) 2009 - 2024 Coozila! MIT License
Version: '3.9'
```

---

## Project Structure

- **Docker Compose Configuration**: Defines services for DragonflyDB and mcrouter.
- **Networks**: Configured for application services.
- **Volumes**: Data persistence for DragonflyDB instances.

## Services

### DragonflyDB Servers

Three instances of DragonflyDB are configured:

1. **dragonfly1**
2. **dragonfly2**
3. **dragonfly3**

Each instance:
- Uses the image `docker.dragonflydb.io/dragonflydb/dragonfly`.
- Sets memory lock limits.
- Maps port `11211` to local ports `11212`, `11213`, and `11214`.
- Persists data in separate volumes.

### Mcrouter

- Image: `coozila/mcrouter:latest`
- Links to the three DragonflyDB instances.
- Command configuration for routing operations.

---

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- Docker
- Docker Compose

---

## Getting Started

### 1. Clone the Repository

Clone the Coozila Apps repository to your local machine:

```bash
git clone https://github.com/coozila/apps.git
cd apps/dragonflydb
```

### 2. Launch the Application

Run the following command to build the Docker images and launch the application:

```bash
docker compose up -d --build
```

### 3. Accessing the Services

- DragonflyDB instances:
  - Instance 1: [http://127.0.0.1:11212](http://127.0.0.1:11212)
  - Instance 2: [http://127.0.0.1:11213](http://127.0.0.1:11213)
  - Instance 3: [http://127.0.0.1:11214](http://127.0.0.1:11214)

- Mcrouter interface:
  - [http://127.0.0.1:11211](http://127.0.0.1:11211)

---

## Cleanup

To stop and remove all containers, networks, and volumes, run:

```bash
docker compose down
```

---

## Additional Documentation

For more details, please refer to the official repository: [Coozila Apps](https://github.com/coozila/apps).

---

## Trademarks

This software listing is packaged by Coozila!. The respective trademarks mentioned in the offering are owned by the respective companies, and use of them does not imply any affiliation or endorsement.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Happy coding!
```