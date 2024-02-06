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


