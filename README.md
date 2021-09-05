kubectl port-forward -n monitoring prometheus-grafana-79fc544c99-txj9t --address 0.0.0.0 3000:3000
kubectl port-forward svc/frontend-service --address 0.0.0.0 8080:8080

**Note:** For the screenshots, you can store all of your answer images in the `answer-img` directory.

## Verify the monitoring installation

*DONE:* run `kubectl` command to show the running pods and services for the three components. Copy and paste the output or take a screenshot of the output and include it here to verify the installation
Monitoring: [Monitoring Namespace](answer-img/monitoring-pods-and-svc.png)
Observability: [Observability Namespace](answer-img/observability-pods-and-svc.png)
App: [Default Namespace](answer-img/app-pods-and-svc.png)

## Setup the Jaeger and Prometheus source
*DONE:* Expose Grafana to the internet and then setup Prometheus as a data source. Provide a screenshot of the home page after logging into Grafana.
Image: [Grafana Home](answer-img/grafana-home.png)

## Create a Basic Dashboard
*DONE:* Create a dashboard in Grafana that shows Prometheus as a source. Take a screenshot and include it here.
Image: [Prometheus Dashboard](answer-img/prometheus-dashboard.png)

## Describe SLO/SLI
*DONE:* Describe, in your own words, what the SLIs are, based on an SLO of *monthly uptime* and *request response time*.
SLIs are specific metrics that are used to measure the performance of a service. If we have an SLO that specifies a specific uptime objective, like 99% for the month, then the SLI would be the actual, measured uptime for the prior month. Request response time would be similar. If they defined a goal, like 500ms, then the SLI would be the average response time for all requests for the month.

## Creating SLI metrics.
*DONE:* It is important to know why we want to measure certain metrics for our customer. Describe in detail 5 metrics to measure these SLIs. 
1. Uptime: the amount of time that the service is available. This one captures exactly what the SLO requests. It will be useful for measuring compliance, even if it wouldn't help for diagnosing any underlying issues. 

2. Error Rate: the percent of requests that resulted in a 4xx or 5xx error. This is 

3. Average latency: the average response time for all successful (2xx) requests. This captures exactly what the SLO requests.

4. Percent of requests above the SLO defined response time. This will help us to dig into the requests that are problematic so that we can correct them.

5. Throughput per second: number of requests per second that the application handles on average. This can be useful to find trends of high utilization of the system.

## Create a Dashboard to measure our SLIs
*TODO:* Create a dashboard to measure the uptime of the frontend and backend services We will also want to measure to measure 40x and 50x errors. Create a dashboard that show these values over a 24 hour period and take a screenshot.

## Tracing our Flask App
*TODO:*  We will create a Jaeger span to measure the processes on the backend. Once you fill in the span, provide a screenshot of it here.

## Jaeger in Dashboards
*TODO:* Now that the trace is running, let's add the metric to our current Grafana dashboard. Once this is completed, provide a screenshot of it here.

## Report Error
*TODO:* Using the template below, write a trouble ticket for the developers, to explain the errors that you are seeing (400, 500, latency) and to let them know the file that is causing the issue.

TROUBLE TICKET

Name:

Date:

Subject:

Affected Area:

Severity:

Description:


## Creating SLIs and SLOs
*TODO:* We want to create an SLO guaranteeing that our application has a 99.95% uptime per month. Name three SLIs that you would use to measure the success of this SLO.

## Building KPIs for our plan
*TODO*: Now that we have our SLIs and SLOs, create KPIs to accurately measure these metrics. We will make a dashboard for this, but first write them down here.

## Final Dashboard
*TODO*: Create a Dashboard containing graphs that capture all the metrics of your KPIs and adequately representing your SLIs and SLOs. Include a screenshot of the dashboard here, and write a text description of what graphs are represented in the dashboard.  
