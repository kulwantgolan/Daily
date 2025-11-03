<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Create lightsail instance

Use Ubuntu OS, instance \$7 per month ( free for 3 months)
Go to Console:
sudo -i
curl -sSL [https://get.easypanel.io](https://get.easypanel.io) | sh

## output of above command is location where n8n is available - port 3000

Go to netwrok tab, add IPv4 firewall riule - custom TCP - 3000; https, 443
Access n8n
set up username and password
Create New n8n project
Service - n8n - provide service name: main, service image: n8nio/n8n:1.64.0 - Create
Acces https route - set up owner account; send me free key;
use key - user - setting - usage and plan - enter activation key => Community edition
crexate step by step instruction

Here are **step-by-step instructions** for setting up your own self-hosted n8n instance on AWS Lightsail using Ubuntu and EasyPanel:

***

**STEP 1: Create AWS Lightsail Instance**

- Log in to your AWS account and open the Lightsail service.
- Click **Create Instance**.
- Choose **Linux/Unix** as the platform and **Ubuntu (e.g. 24.04 LTS)** as the OS.
- Select the \$7/month plan (**free for the first 3 months for new users**).
- Name your instance and click **Create**.

***

**STEP 2: Connect to the Instance via SSH Console**

- From the Lightsail dashboard, open your new instance.
- Click **Connect** (browser SSH terminal).

***

**STEP 3: Become Root**

```bash
sudo -i
```


***

**STEP 4: Install EasyPanel**

```bash
curl -sSL https://get.easypanel.io | sh
```

- This script will:
    - Check you are root and on Ubuntu
    - Ensure Docker is installed (may install Docker if missing)
    - Download and install EasyPanel as a Docker service
    - Output the EasyPanel port (default is **3000**)
<img width="1869" height="375" alt="image" src="https://github.com/user-attachments/assets/4f506730-c1e5-4abc-a735-08d9a97af7af" />
<img width="1354" height="614" alt="image" src="https://github.com/user-attachments/assets/8e24ad06-5b71-45bd-9c8d-5767dbf84b0d" />


***

**STEP 5: Configure AWS Network Firewall**

- Go to your Lightsail instance page → **Networking** tab.
- In **Firewall** section, add the following rules:
    - **Custom TCP Rule**: Port 3000 (for EasyPanel dashboard)
    - **HTTPS Rule**: Port 443
    - **(Optional) HTTP Rule**: Port 80 if you want non-SSL access

***

**STEP 6: Access EasyPanel Dashboard**

- In your browser, visit:
`http://<your-public-ip>:3000`
- Set up your **username** and **password** for EasyPanel admin.
<img width="870" height="815" alt="image" src="https://github.com/user-attachments/assets/da332c31-dd5c-41e8-9875-4fdceaeb1f12" />
<img width="1832" height="807" alt="image" src="https://github.com/user-attachments/assets/81b4eb1e-9c65-4ac2-b778-572eda569993" />

***

**STEP 7: Create New n8n Project**

- In the EasyPanel dashboard:
    - Click **Create Project** (name it whatever you like).
    - Inside the project, click **Add Service**.
        - Search in "Templates" -> n8n
        - **Service Name**: main (or your choice)
        - **Service Image**: `n8nio/n8n:1.64.0`
    - Click **Create**.
<img width="946" height="633" alt="image" src="https://github.com/user-attachments/assets/5b25aaae-8aa9-4d28-925f-c058632a1e38" />
<img width="1270" height="783" alt="image" src="https://github.com/user-attachments/assets/8a2cb184-4945-41d1-8d15-6f0849cfb426" />
<img width="1207" height="671" alt="image" src="https://github.com/user-attachments/assets/79830c45-424a-4d6b-8fae-1a61592422f6" />

***

**STEP 8: Access n8n Web Route**

- Once EasyPanel starts n8n, you’ll get a public URL, usually `http://<your-public-ip>:<port>` (either port 443/https or a mapped port).
- Open this in your browser.
<img width="1124" height="941" alt="image" src="https://github.com/user-attachments/assets/2ae2166f-dad7-409b-aa73-7825ff81eb3c" />

***

**STEP 9: Set Up n8n Owner Account \& Activation Key**

- Go through n8n’s onboarding:
    - Set up owner **username** and **password**.
    - When prompted, click **Send me free key** (for Community Edition).
        - You’ll get the key by email or the dashboard.
    - In n8n, go to **Settings → Usage \& Plan → Enter Activation Key**.
        - Paste the community key to unlock full features.
<img width="830" height="829" alt="image" src="https://github.com/user-attachments/assets/daa7de4a-11c5-4043-a156-1a8bf56d0640" />
<img width="505" height="461" alt="image" src="https://github.com/user-attachments/assets/f6c52cd6-3e6b-41fd-a2cf-844769ab3ea9" />

***

**STEP 10: Your Instance is Live!**

- You can now use n8n:
    - Build workflows.
    - Connect services.
    - Enjoy local, private automation.

***

**Notes:**

- If the instance ever stops, restart it from Lightsail.
- If you want SSL, you can set up a domain and use EasyPanel’s SSL tools.
- Record your passwords safely.
- If you need to update n8n, change the Docker image version from EasyPanel.

If you want direct guidance (step-by-step via screenshots or video), let me know!
<span style="display:none">[^1]</span>

<div align="center">⁂</div>

[^1]: https://get.easypanel.io

