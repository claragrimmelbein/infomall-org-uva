Rivanna has strict rules with allocated space for users. It is very important to understand how to deal with space to use Rivanna correctly.

The home directory on Rivanna has 50GB of storage capacity. It is only for personal use and is not shareable with other users. As a user on Rivanna, you have access to 10 TB of temporary storage. It is located in a subdirectory under /scratch and named with your userID. You are limited to 350,000 files in your scratch directory and you cannot share your scratch directory with others. You should run your jobs out of scratch because /scratch is on GPFS. It is a storage system designed specifically for parallel access. Make sure to keep copies of your programs and data in your home directory or leased storage.


You, and each of your bii_dsc_community group members, can see how much your storage share quota is by using the hdquota utility. Simply open a Terminal window and type hdquota at the command-line prompt. For instance, as thf2bn, you might see output like the following. It shows that bii_dsc_community’s storage share is 6 TB and that your group is currently using 5.6 TB and there is approximately 430 GB left of the bii_dsc_community storage quota:


```thf2bn@rivanna:~$ hdquota
Type             Location         Name                                        Size Used Avail Use%
====================================================================================================
home             /home            thf2bn                                     100G   80G   21G  80%
Project          /project         biocomplexity                              450T   26T  425T   6%
Project          /project         bii_nssac                                 800.0T 786.4T 13.6T  98%
Project          /project         nssac_bigdata                              1.0T  154G  870G  15%
Project          /project         nssac_STOMPflu                             2.0T  832G  1.2T  40%
Project          /project         bii_dsc                                   20.0T  4.9T 15.1T  24%
Project          /project         bii_dsc_community                          6.0T  5.6T  430G  93%
```

In terms of a temporary space where you might figure out how much space you want to request, from another request regarding Dr. Fox’s DGX A100 node, it appears that there is 27 TB of NVME mounted as /localscratch there.  RC does not perform any backups or snapshots of /localscratch.  Your group (bii_dsc and bii_dsc_community) currently have exclusive access to that server via the bi_fox_dgx reservation.
