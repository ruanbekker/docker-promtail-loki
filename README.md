# docker-promtail-loki
Docker Compose Stack with Grafana Loki and Promtail

## Usage

Start the stack with:

```bash
docker-compose up -d
```

Access nginx on http://localhost:8080

<img width="1113" alt="image" src="https://user-images.githubusercontent.com/567298/202505252-3cbc2d03-d1d2-48e6-bea7-5db54233b9a2.png">

Then navigate to grafana on http://localhost:3000 and select explore on the left and select the container:

<img width="560" alt="image" src="https://user-images.githubusercontent.com/567298/202504989-e05a08a2-eb2f-41a1-85f4-9a11a8affd7c.png">

And you will see the logs:

<img width="1425" alt="image" src="https://user-images.githubusercontent.com/567298/202505099-c47b76cc-3090-4eb9-8459-db659d0aac18.png">

