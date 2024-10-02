# Obornes DevOps/SRE Challenge

## Playing with Metrics

Your task is to write a script that can parse metrics from a defined local container and send an alert to an email (to the person responsible for the tech interview) if some metric is above a defined threshold. Once the alert is triggered, the script should be able to perform some actions.

Run `docker-compose up` to have cAdvisor and Redis up and running to start playing with it.
You should be able to access the container metrics by accessing `http://localhost:8080/api/v1.3/docker/redis`

Requirements:

1) The script needs to be configurable by defining the container name, the metric name, the threshold, and the window to be evaluated in minutes. The script should be able to track more than one metric (ex, CPU, and memory). Keep in mind that you already have a Redis container to help you to test. You also can use a time series storage to store the metrics if you want to. 
2) Define how often the script will retrieve data.
3) If the alert gets triggered, we should be able to perform an action. You must implement a simple action like scaling up the number of instances in an AWS Auto Scaling group.
4) If the script is initialized with the --upload flag, all the metrics need to be dumped into a file and sent to a defined S3 bucket once the alert is triggered.
5) You should send the alert to an email (to the person responsible for the tech interview).
6) Create a Dockerfile and provide the instructions to run your script.

Bonus:

* You write unit tests
* Your script scales

PS: You can use any scripting language to solve this challenge.
PS2: You can use the AWS Free Tier account to solve the challenge without being charged: https://aws.amazon.com/free/

We hope you'll have fun doing this challenge. It shouldn't take more than a few hours: KISS. Happy coding!
