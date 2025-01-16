# MonitorCPU---Task3-2-
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Name : Lavisha Ulkesh Desai <br>
Company : CODTECH IT SOLUTIONS <br>
ID : CT08EHV<br>
Domain : Power BI<br>
Duration : 17, December,2024 to 17, January ,2025 <br>
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Objective : SET UP A REAL-TIME DASHBOARD USING STREAMING DATA (E.G., FROM AZURE OR A SIMULATED API FEED). REAL-TIME DASHBOARD DELIVERABLE: A LIVE POWER BI DASHBOARD THAT UPDATES IN REAL-TIME.
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# 🔥 Real-Time CPU & Memory Monitoring with Power BI 🚀

This project demonstrates how to monitor **CPU and Memory usage** in real time using **Power BI** streaming datasets and **PowerShell** scripting. Below is a breakdown of how we achieved this functionality:

---

## 📊 Step 1: Creating a Streaming Dataset in Power BI
- We set up a **Streaming Dataset** in Power BI using the `API` mode.  
- The dataset contains fields for `Date`, `Time`, `CPU`, and `Memory` usage.  
- Power BI automatically generates an API endpoint for data ingestion. 🌐  
---

## 🛠️ Step 2: Using PowerShell to Push Real-Time Data
- Leveraged **PowerShell** to send live CPU and memory metrics to the Power BI API endpoint.  
- A JSON payload containing system metrics is generated and pushed using the `Invoke-RestMethod` command.  

![Screenshot 2025-01-17 041417](https://github.com/user-attachments/assets/f7fd7782-7e36-4f04-bcf7-eb23de1b2f75)
![Screenshot 2025-01-17 041707](https://github.com/user-attachments/assets/60e221c4-bedf-4803-a8e2-378b71bf8db0)
![Screenshot 2025-01-17 031908](https://github.com/user-attachments/assets/62116dcc-f071-4e15-98d6-beb1541b702e)
<br>

### PowerShell Script Example
```powershell
$endpoint = "YOUR_API_ENDPOINT_HERE"
$payload = @{
    "Date"   = "2025-01-16T21:11:37.867Z"
    "Time"   = "2025-01-16T21:11:37.867Z"
    "CPU"    = 98.6
    "Memory" = 98.6
}
Invoke-RestMethod -Method Post -Uri $endpoint -Body (ConvertTo-Json @($payload)) 
