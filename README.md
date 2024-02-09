# Schedule Machine Images: Backup and DR solution for Google Compute VM Instances

## Introduction
Backup and Disaster Recovery (DR) are important for Google Cloud Platform (GCP) VMs to protect against data loss and ensure business continuity in the event of a disaster or outage.
While Google Cloud does not offer a single, comprehensive managed solution for backup and DR of Compute VMs, it provides a range of services that can be utilized to implement backup and DR strategies based on specific business needs.

## Options Available in Google Cloud
1. Snapshot(If multiple disk attached to a VM then it will be difficult to identify latest snapshot)
2. Machine Image(not use because no scheduling feature available for this)
3. Backup and DR service(this new service is not suitable or mature enough for use in production environments.)

## Then what is the solution now?

![image](https://github.com/prabhatu012345/gcp-vm-instances-backup/assets/44310215/3520a722-3ed1-4826-8576-a0ac39535281)

## Cloud Function set up

1. Use the attached Python script to create machine images daily and delete machine images from the previous day to maintain a single latest copy. You can customize frequency based on your need.
2. Create 2nd gen — Pub/Sub triggered Cloud function with given details.
3.  Use “create_machineimage” as an entry point for the cloud function as we are using this function name for our script.
4.  Make sure Cloud Function is deployed successfully


![image](https://github.com/prabhatu012345/gcp-vm-instances-backup/assets/44310215/36b7c132-0310-4498-be78-89538bac75f8)

## Cloud Scheduler Setup

1. Create Cloud Scheduler Job with the required schedule.
2. Use the same Pub/Sub topic as the target, which is used for the Cloud function.
3. Monitor Cloud Scheduler Job and Cloud Function execution.(you also force start it)
4. Once it is successfully set up, it should create machine images on daily basis by deleting older machine images.

 ![image](https://github.com/prabhatu012345/gcp-vm-instances-backup/assets/44310215/5ee185a9-f610-4759-b3a6-9972bf31b786)

 ### Reference Link

 https://medium.com/google-cloud/schedule-machine-images-backup-and-dr-solution-for-google-compute-vm-instances-f8b605b04f95

 
  



      




