# docker-promtail-loki
Docker Compose Stack with Grafana Loki, Promtail and the Grafana [Explore Logs](https://grafana.com/blog/2024/04/09/find-your-logs-data-with-explore-logs-no-logql-required/) plugin.

> [!NOTE]  
> For a full example with prometheus, alertmanager, cadvisor, node-exporter and loki, please see the following repo:
> - https://github.com/ruanbekker/docker-monitoring-stack-gpnc

## Usage

Start the stack with:

```bash
make up
```

Access nginx on http://localhost:8080

## View Logs

<img width="1113" alt="image" src="https://user-images.githubusercontent.com/567298/202505252-3cbc2d03-d1d2-48e6-bea7-5db54233b9a2.png">

Then navigate to grafana on http://localhost:3000 and select explore on the left and select the container:

<img width="560" alt="image" src="https://user-images.githubusercontent.com/567298/202504989-e05a08a2-eb2f-41a1-85f4-9a11a8affd7c.png">

And you will see the logs:

<img width="1425" alt="image" src="https://user-images.githubusercontent.com/567298/202505099-c47b76cc-3090-4eb9-8459-db659d0aac18.png">

## Explore Logs

The grafana explore-logs app can be found under explore:

![image](https://github.com/user-attachments/assets/14aa2b93-8baf-441b-bd18-eeade5dd575c)

Any application that logs to Loki can be discovered here:

<img width="1329" alt="image" src="https://github.com/user-attachments/assets/2d03c559-1046-4897-9429-eb9bc6fc89ee">

Here we can view the log content for the selected `service_name`:

<img width="1327" alt="image" src="https://github.com/user-attachments/assets/1eb0e32f-5019-437e-b760-b1a63cbc8beb">

This view we can explore the different labels thats available for our selected service:

<img width="1333" alt="image" src="https://github.com/user-attachments/assets/a222ab21-5c3f-4f66-b01e-9e882c1a8df2">

For example, we can select the `level` label, which will then append that to our LogQL query and present us with this view:

<img width="1330" alt="image" src="https://github.com/user-attachments/assets/f805b460-6f70-4298-a8b3-2118e4931266">

We can then include `error` for example and we will see all the error logs for our selected service:

<img width="1332" alt="image" src="https://github.com/user-attachments/assets/d1502c06-5cae-498d-81e0-470afd7890dd">

We can then also select "Open in Explore" and our query will be pre-populated for us, eg. `{service_name="tempo-ingester", level="error"} | logfmt`:

<img width="1330" alt="image" src="https://github.com/user-attachments/assets/974b8916-c9f6-466a-994e-52d10e771353">

We can also explore logs by fields:

<img width="1336" alt="image" src="https://github.com/user-attachments/assets/3b459123-f132-422c-8ac3-ea69898e7f94">

As well as patterns:

<img width="1334" alt="image" src="https://github.com/user-attachments/assets/f2adc9b8-b808-45a5-8dab-d17accd31aa0">

For more information about exploring logs without LogQL, view Grafana's blog post:
- [Find your logs data with Explore Logs: No LogQL required!](https://grafana.com/blog/2024/04/09/find-your-logs-data-with-explore-logs-no-logql-required/)
