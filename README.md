# ITT440 INDIVIDUAL ASSIGNMENT WEB PERFORMANCE TESTING
* NAME: KHALID BIN SHUKRY TALIB
* ID: 2023822836
* GROUP: NBCS2555A
* PREPARED FOR: SIR SHAHADAN BIN SAAD
* TESTING SELECTED: LOAD, SPIKE, AND VOLUME
* TARGETED SITE: https://www.deepseek.com/
* TOOL: LOCUST

# 1.	What is Performance Testing? 

Performance testing is a type of software testing that evaluates how well an application or system behaves under different levels of workload. It identifies whether the system is fast, stable, and reliable when multiple users interact with it at the same time.

The main objectives of performance testing are to measure:

**Response time** – how quickly the system reacts to a request

**Throughput** – the number of requests the system can process per second

**Scalability** – how well the system handles increasing traffic

**Stability** – the system’s consistency during continuous or heavy usage

Overall, performance testing ensures that the system can handle real-world usage without slowing down, failing, or affecting the user experience.

<img width="646" height="610" alt="image" src="https://github.com/user-attachments/assets/853e39db-5d5c-41ef-b9e8-ee1327ea8e32" />


# 2.	Introduction to Spike, Load, and Volume Testing Using Locust


In this project, three types of performance tests were carried out using Locust, an open-source performance testing tool. All tests were executed against a publicly accessible website https://www.deepseek.com/ used as the target system for performance testing.

This API was used as the target system to observe how it responds under different traffic conditions.


**Load Testing**

Load testing is used to measure how the system performs under normal or expected levels of traffic. Using Locust, a consistent number of virtual users were simulated to send requests to the deepseek website. This test helps determine whether the API can handle everyday usage without performance degradation.


**Spike Testing**

Spike testing evaluates how the system behaves when there is a sudden and rapid increase in user load. The API was intentionally exposed to a sharp jump in traffic to observe its reaction. This test helps identify whether the system can handle unexpected traffic spikes and how quickly it recovers afterward.


**Volume Testing**

Volume testing checks the system’s ability to handle large amounts of data or a high number of continuous requests. In this test, the API was repeatedly hit with heavy data or request volume to assess stability and consistency over time.


By performing these three tests on the deepseek website using Locust, we can analyze the API’s stability, responsiveness, and overall performance behaviour under different stress levels.

# 3 Test Enviroment

accessible website https://www.deepseek.com/ used as the target system for performance testing.

<img width="978" height="246" alt="image" src="https://github.com/user-attachments/assets/b439249a-52ff-4359-8d59-90bc4c856392" />

<img width="1903" height="468" alt="image" src="https://github.com/user-attachments/assets/1060dc86-2f1e-4f79-9f90-48fb87c9c7f6" />


**Tools Used**

Locust (Python-based load testing tool)
Used to simulate virtual users, generate traffic, and collect performance metrics such as response time, throughput, and failures.

Python 3.14.1
Required to run the Locust scripts and execute test scenarios.

DeepSeek website (https://www.deepseek.com/)
A publicly available REST API used as the target system for testing.


**Hardware Specifications**

The performance tests were executed on a personal desktop with the following specifications:

Processor: Intel (Intel i5)

RAM: 16GB

Operating System: Windows 10

Storage: 1TB HDD + 500GB SSD

**Network Environment**

Connection Type: Home Wi-Fi
Average Speed: 50–100 Mbps
Stability: Normal residential connection

The environment above provides a realistic setup for simulating small-scale performance tests and observing how the DeepSeek API behaves under different load conditions.


# 4 Test Scenarios

In this project, three different performance test scenarios were designed to evaluate how the DeepSeek API (https://www.deepseek.com/) behaves under various types of workloads. Each scenario targets a specific aspect of performance, allowing detailed analysis of system behaviour.


**Load Test Scenario**

Objective:
To measure how the API performs under a normal and steady flow of user traffic.

Scenario Description:
Locust simulates a consistent number of virtual users sending continuous GET and POST requests to the DeepSeek API. This test helps determine whether the API can maintain stable response times and throughput during regular usage.



**Spike Test Scenario**

Objective:
To evaluate how the API reacts when there is a sudden and rapid increase in user load.

Scenario Description:
A small number of users is started initially, followed by an abrupt jump to a high number of users within a very short time. This test helps identify whether the API can handle sudden spikes without crashing, and how quickly it stabilizes after the traffic surge.



**Volume Test Scenario**

Objective:
To assess how the API behaves when processing a large volume of cumulative requests or data over a specific period.

Scenario Description:
Locust repeatedly hits the API with heavy request volume, focusing on endpoints that return multiple records or require more data handling. The purpose is to check for any latency buildup, failures, or API throttling due to high request volume.

# 5 Test Configurations

This section explains how each performance test (Load, Spike, and Volume) was configured in Locust when testing the DeepSeek API (https://www.deepseek.com/). The configurations include the number of users, spawn rate, duration, and targeted endpoints.



**Load Test Configuration**

Purpose:
To simulate normal, steady traffic to observe system stability under expected usage.

Configuration Details:
Number of Users: 50
Spawn Rate: 5 users per second
Test Duration: Approximately 3–5 minutes

Endpoints Tested:
https://www.deepseek.com/

Traffic Pattern:
Users increase gradually and remain stable throughout the test.



**Spike Test Configuration**

Purpose:
To test how the system behaves under a sudden and extreme increase in user load.

Configuration Details:
Initial Users: 1
Sudden Jump To: 100 users
Spike Spawn Rate: 50 users per second (very rapid increase)
Test Duration: Short period (1minute+)

Endpoints Tested:
https://www.deepseek.com/

Traffic Pattern:
Fast ramp-up to high traffic, followed by immediate observation of response times.


**Volume Test Configuration**

Purpose:
To evaluate how the system handles a large volume of continuous requests.

Configuration Details:
Number of Users: 30
Spawn Rate: 2 users per second
Test Duration: Long-running (12 minutes+)

Endpoints Tested:
https://www.deepseek.com/

Traffic Pattern:
A steady flow of repeated API calls to observe cumulative performance and stability.

# 6 Test Results and Analysis

This section presents the results of the Load Test, Spike Test, and Volume Test performed using Locust. Each subsection includes the required charts and a short analysis of the system’s behaviour.



## Load Test Results 

Load Test Configuration
•	Number of Users: 50
•	Spawn Rate: 5 users/second
•	Target Website: https://www.deepseek.com/
•	Duration: ~2 minutes (based on timestamps)

<img width="951" height="576" alt="image" src="https://github.com/user-attachments/assets/3c6553f7-354f-4828-b9d3-95023a158957" />

**Figure X: Load Test** – Requests per Second, Response Times, and Number of Users for DeepSeek.com.


## Analysis of Load Test 

**1.	 Total Requests per Second (RPS)**

-	RPS increased rapidly as users ramped up, peaking around 27–29 requests per second.

-	After stabilizing at 50 users, the RPS curve remained steady and consistent, showing that the website handled the traffic smoothly.

-	The Failures/s line stays at zero, meaning the system returned successful responses for all simulated requests.



**2.	 Response Times**

-	The response time initially spiked to around 280–300 ms, which is common during rapid user ramp-up.

-	After the system stabilized, the:

o	50th percentile (median) response time decreased to 150–180 ms

o	95th percentile eventually dropped back down close to 0 ms (which indicates caching or very fast static content response)

-	This shows that once the site handled the initial surge, the performance became very fast and efficient.



**3.	 Number of Users**

-	The user ramp-up graph shows a smooth increase from 0 to 50 concurrent users within seconds.

-	Once 50 users were reached, the load remained stable throughout the test.

-	This demonstrates that Locust successfully applied the intended load consistently.

## Conclusion (Load Test) 

The Load Test on DeepSeek.com shows:

•	The site can handle 50 concurrent users without performance issues.

•	RPS remained stable at nearly 30 requests per second.

•	Response times dropped to stable, low values after ramp-up.

•	No failures occurred throughout the test.

Overall, the website demonstrated strong performance and stability under normal load conditions.


## Spike Test Results


Spike Test Configuration
•	Starting Users: 1
•	Sudden Jump To: 100 users
•	Spawn Rate: 50 users/second
•	Target Website: https://www.deepseek.com/
•	Duration: ~1 minute

<img width="983" height="546" alt="image" src="https://github.com/user-attachments/assets/a93a6c4a-c48b-4ae0-9291-6da8b2ed29d0" />

**Figure X: Spike Test** – RPS, Response Times, and User Count showing sudden traffic surge.


## Analysis of Spike Test

This spike test evaluates how DeepSeek.com reacts when traffic increases very suddenly from low to extremely high within seconds.


**1.	 Total Requests per Second (RPS)**

-	At the spike moment (around 8:00 PM), RPS jumps sharply to approximately 55–60 requests per second.

-	After reaching the peak, the RPS stabilizes at around 50+ RPS, indicating that the system can process the sudden high volume of requests efficiently.

-	The Failures per second remain at 0, which means the site handled the spike without producing errors.


**2.	Response Times**

-	A clear surge in response time occurs immediately after the spike:

o	50th percentile jumps above 150 ms

o	95th percentile spikes above 300 ms

-	This is expected because the server is suddenly loaded with 100 virtual users.

-	After the initial spike, the response times drop back down close to 0–10 ms, showing:

o	Rapid recovery

o	Good caching behaviour

o	Strong backend performance

-	The system stabilizes quickly after absorbing the traffic shock.


**3.	 Number of Users**

The number of users increases instantly from near zero to 100 users within a very short timeframe.

The user graph shows a plateau at 100 users, meaning Locust successfully simulated the spike.

The drop at the end indicates the test stopped normally after a short spike duration.


## Conclusion (Spike Test) 

The results show that DeepSeek.com handles sudden, extreme traffic increases very well:

•	The system survived a fast jump to 100 users

•	RPS remained stable above 50

•	No failures occurred at any point

•	Response times spiked briefly (expected) but recovered quickly

•	The system demonstrated strong resilience and scalability

Overall, the Spike Test indicates that the website can withstand sudden heavy traffic loads without crashing or producing errors.



## Volume Test Results 

**Volume Test Configuration**
•	Number of Users: 30
•	Spawn Rate: 2 users/second
•	Duration: Approximately 12 minutes
•	Target Website: https://www.deepseek.com/
•	Test Window: 8:55 PM – 9:07 PM


<img width="839" height="565" alt="image" src="https://github.com/user-attachments/assets/035bfdbf-6043-4155-a7d0-9ad420787e3f" />


**Figure X: Volume Test** – RPS, Response Times, and User Count for DeepSeek.com.


## Analysis of Volume Test 

The Volume Test was performed to evaluate how DeepSeek.com handles extended, continuous traffic over a longer period. This test is different from load and spike tests because the focus is on sustained performance rather than sudden pressure.


**1.	 Total Requests per Second (RPS)**

-	At the beginning of the volume test (~8:55 PM), RPS jumps to around 12–14 requests per second as users increase.
-	Once the test stabilizes, RPS rises further and peaks at 15–17 RPS, maintaining consistency.
-	The green RPS line remains smooth during the 12-minute test window.
-	Failures/s stayed at 0 throughout the entire run, indicating no errors or crashes.

This shows that the website can reliably handle prolonged incoming traffic.


**2.	 Response Times**

-	Response time initially spikes:
o	50th percentile: ~180–200 ms
o	95th percentile: ~280–300 ms

-	This is normal as the system adjusts to new users.

-	After stabilizing, the response times drop back toward 0–10 ms, showing:
o	Efficient request handling
o	Possible caching improvements
o	Strong backend optimization

-	Response times remain consistently low for the remainder of the test.

This demonstrates that performance does not degrade over time, even with continuous requests.

**3.	Number of Users**

-	At 8:55 PM, users gradually climb to 30 concurrent users following the configured spawn rate of 2 users/sec.
-	Users stay at 30 throughout the volume test period until the test ends at ~9:07 PM.
-	The stable user plateau confirms that Locust maintained the intended long-duration workload.

## Conclusion (Volume Test)

The Volume Test results indicate that DeepSeek.com performs strongly under long-duration, repetitive traffic, showing:

Stable RPS between 12–17

Consistently low response times after ramp-up

Zero failures across the entire 12-minute run

No gradual slowdown or degradation

This confirms the system’s endurance, reliability, and efficiency during prolonged traffic periods.

# 7.	Comparison of Test Results

The three performance tests (Load, Spike, and Volume) each provide different insights into how DeepSeek.com behaves under various traffic conditions. The table below summarizes the key observations.

<img width="953" height="283" alt="image" src="https://github.com/user-attachments/assets/a231f760-bc06-4c81-8281-5ea3f0d5a88e" />

## Comparative Analysis

**•	Load Test:**
Demonstrated that the website can easily manage typical day-to-day traffic. Response times remain stable, and no failures occurred.

**•	Spike Test:**
This is the most stressful test. The sudden jump to 100 users caused noticeable response time spikes, but the system recovered quickly and processed high RPS with zero failures — showing resilience under unexpected traffic surges.

**•	Volume Test:**
Focused on endurance. The website maintained low response times throughout a 12-minute continuous load with no signs of slowing down, indicating strong long-term stability.

# 8.	 Conclusion and Recommendations

## Conclusion

The performance testing conducted using Locust on DeepSeek.com covering Load, Spike, and Volume scenarios shows that the website performs efficiently, reliably, and consistently under different traffic conditions.

**Key takeaways:**

•	The system handles normal traffic without performance degradation.
•	It can survive sudden spikes in user load with no crashes or errors.
•	It maintains high stability and speed during long-duration continuous requests.
•	Across all tests, zero failures were recorded, demonstrating strong backend reliability.

Overall, DeepSeek.com shows excellent performance characteristics and is capable of supporting both steady and dynamic traffic patterns.


## Recommendations

Although the system performs well, the following recommendations can further improve performance in high-traffic environments:

**1.	Implement more aggressive caching strategies**
Helps reduce response spikes during sudden load increases.

**2.	Consider autoscaling capability (if applicable)**
Allows the system to automatically adjust resources during peak usage.

**3.	Monitor API latency in real-time**
Continuous monitoring helps detect anomalies early.

**4.	Test more endpoints**
Different endpoints may behave differently; future tests could include authentication or search endpoints.

