[Cloud Functions]
* Configuration Steps for starting and stopping VMs with Cloud Functions
   1. A GCP Project
   2. Billing enabled
   3. Project ID, VM(s) name(s), and zone(s)
   4. Enable Cloud Functions, & Cloud Build APIs
   5. A dedicated service account
* Links to refer
   - start&stop Vms: https://www.youtube.com/watch?v=52A-Qdf5-6o


[IAP (Identity Aware Proxy)]
* Applicable target resources
   1. HTTPS: Appengine, backends, load balancer...
   2. SSH & TCP: VMs (tunneled with SSH, RDP ...)
* Configuration Steps
   1. Enable IAP API
   2. Setup the required firewall rules (from IAP proxy to VMs)
   3. Remove Public IPs from the VMs
   4. Add the required permissions to VMs (IAP secured Tunnel User)
* Connection test examples
   - GCP Console: VM "SSH" button    
   - CMD: gcloud compute ssh instance-name --tunnel-through-iap --zone=us-central1-a
   - IAP Desktop app by google
   - Local port forwading: 
     1) gcloud compute start-iap-tunnel instance-name 3389 --local-host-port=3390 --zone=us-central1-a
     2) connect to localhost:3390
* Links to refer
  - SSH & TCP: https://www.youtube.com/watch?v=MQJqSMZrnUA (About IAP)
               https://www.youtube.com/watch?v=Vfxf2LdsXfs
  - HTTPS: https://www.youtube.com/watch?v=52A-Qdf5-6o (How to protect cloud function with IAP)
