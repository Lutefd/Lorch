# Lorch

## Purpose

This project aims to create a comprehensive personal data aggregator that consolidates information from various services including Strava, Hevy, GitHub, Spotify, and RSS feeds. The goal is to provide a unified dashboard for tracking exercises, coding activities, music and podcast consumption, and other content consumption.

## Service Architecture

The following diagram represents the high-level architecture of our services and how they interact:

![service architecture diagram](/docs/service_architecture/service_architecture.png)

## Key Components

1. **Authorization Service**: Manages OAuth2 and API key authentication for various external services.
2. **Updater Service**: Periodically fetches data from external APIs and updates the central database.
3. **Central API**: Provides a unified interface for client applications to access aggregated data.
4. **PostgreSQL Database**: Stores all aggregated data from various services.
5. **Redis Cache**: Improves performance by caching frequently accessed data.
6. **RabbitMQ**: Implements a pub-sub architecture for real-time updates and decoupled communication between services.
7. **Web App**: Built with Astro and Svelte, provides a user-friendly interface to view aggregated data.
8. **CLI REPL**: Allows command-line interaction with the aggregated data.
9. **Logging & Monitoring Stack**: Uses Prometheus, Loki, and Grafana for comprehensive system observability.

## Design Decisions

1. **Microservices Architecture**: The project is structured as microservices to allow for better scalability, easier maintenance, and the flexibility to deploy and scale components independently.

2. **Golang for Backend**: Go was chosen for its performance, strong typing, and excellent support for concurrent operations, making it ideal for building efficient microservices.

3. **Astro + Svelte for Frontend**: This combination offers excellent performance and developer experience for building the web application.

4. **Docker Containers**: All services are containerized to ensure consistency across different environments and to facilitate easy deployment and scaling.

5. **Pub-Sub Architecture**: Utilizing RabbitMQ for a pub-sub system allows for real-time updates and decouples the updater service from the API, improving overall system responsiveness.

6. **PLG Stack for Logging**: The combination of Prometheus, Loki, and Grafana provides a comprehensive solution for metrics, logging, and visualization, crucial for monitoring the health and performance of the system.

7. **Separate Authorization Service**: Having a dedicated service for managing authentication and authorization ensures a centralized and secure approach to handling sensitive credentials.

## Getting Started

(This section will be updated with setup instructions as the project progresses)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
