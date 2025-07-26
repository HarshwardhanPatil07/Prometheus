# Alerting
- You want to get notified when something happens so you can check dashboard

![prometheus-alert-rules](/assests/prometheus-alert-rules.png)

![prometheus-alert-firing](/assests/prometheus-alert-firing.png)

# Create own alert rules
- 1st rule: Alert when cpu usage > 50%
- 2nd rule: Alert when pod cannot start
- Prometheus Operator extends the k8s api so we can create custom k8s resources (alert rules); Operator takes our custom k8s resource and tells prometheus to reload the alert rules

# To see CPU Stress
- Go to docker hub and serch it tap on image and see the cmd to run it below after scrolling
- Convert that docker cmd into kubernetes cmd `kubectl run cpu-test --image-containerstack/cpustress -- --cpu 4 --timeout 30s -metrics-brief`
![cpu-load-increasing](/assests/cpu-load-increasing.png)
![cpu-high-load-firing](/assests/cpu-high-load-firing.png)

# Firing alert to Email via AlertManager
![alertmanager-email-workflow](/assests/alertmanager-email-workflow.png)
- To run do same port forwading
![alertmanager-portforwading](/assests/alertmanager-portforwading.png)
![alertmanager-ui](/assests/alertmanager-ui.png)

- In routes you can define which notification channel gets the notification via alertname:
- Top-Level Route - Every alert enters the routing tree at the top level route, It is configuration applying to all alerts.
- can refer docs https://docs.redhat.com/en/documentation/openshift_container_platform/4.7/html/monitoring/managing-alerts

# Monitor third party with Exporters