![image](https://github.com/nhvu95/aws-handbook/assets/26276890/5f49f31b-8ec1-4e47-bfdc-5db5431d16c6)

* Make a backup (snapshot) of your EBS at a point in time
* Not necessary to detach volume to do snapshot, but recommended
* Can copy snapshots across AZ or Region => This is the way we sen data between EBS in different AZ

* EBS Snapshot Archive
    * Move a snapshot to an "archive tier" that is 75% cheaper
    * Takes within 24 to 72 hours for restoring the archive

* Recycle Bin for EBS Snapshots
    * Setup rules to retain deleted snapshots so you can recover them after an accidental deletion
    * Specify retention ( from 1 day to 1 year)

* Fast snapshot restore (FSR)
    * Force full initialization of snapshot to have no latency on the first use ($$$)
