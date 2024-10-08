# Basic-GCP-resource-object-management-CLI-commands

10.138.0.2
35.230.75.126


Creating buckets
```gcloud storage buckets create -l "ASIA" gs://qwiklabs-gcp-02-8288bf2664c0```

Copying from buckets to buckets
```gcloud storage cp gs://cloud-training/gcpfci/my-excellent-blog.png gs://qwiklabs-gcp-02-8288bf2664c0```


Listing the contents of buckets,
```gcloud storage ls gs://qwiklabs-gcp-02-8288bf2664c0/```

examples
```gcloud storage buckets list: Lists all buckets in your project.
gcloud storage ls gs://your-bucket-name: Lists the contents of the specified bucket.
gcloud storage ls gs://your-bucket-name/directory/: Lists the contents of the specified directory within the bucket.
```
Modify the Access Control List of the object you just created so that it's readable by everyone

`gsutil` to check hash of storage bucket
```student_02_61105cf27e30@cloudshell:~ (qwiklabs-gcp-02-8288bf2664c0)$ gsutil hash gs://$DEVSHELL_PROJECT_ID/my-excellent-blog.png
Hashes [base64] for my-excellent-blog.png:
        Hash (md5):             /19M4m9ZPqpnORdfmozrTQ==
        Hash (crc32c):          uMTJWg==
```
Display object status
```student_02_61105cf27e30@cloudshell:~ (qwiklabs-gcp-02-8288bf2664c0)$ gsutil stat gs://$DEVSHELL_PROJECT_ID/my-excellent-blog.png
gs://qwiklabs-gcp-02-8288bf2664c0/my-excellent-blog.png:
    Creation time:          Tue, 08 Oct 2024 11:08:46 GMT
    Update time:            Tue, 08 Oct 2024 11:08:46 GMT
    Storage class:          STANDARD
    Content-Length:         8425
    Content-Type:           image/png
    Hash (crc32c):          uMTJWg==
    Hash (md5):             /19M4m9ZPqpnORdfmozrTQ==
    ETag:                   CP+G9snS/ogDEAE=
    Generation:             1728385726120831
    Metageneration:         1
```

Lets make use of gsutil compose command
```
student_02_61105cf27e30@cloudshell:~ (qwiklabs-gcp-02-8288bf2664c0)$ vi beo.txt
student_02_61105cf27e30@cloudshell:~ (qwiklabs-gcp-02-8288bf2664c0)$ cp beo.txt bro.txt
student_02_61105cf27e30@cloudshell:~ (qwiklabs-gcp-02-8288bf2664c0)$ cp beo.txt khdb.txt
student_02_61105cf27e30@cloudshell:~ (qwiklabs-gcp-02-8288bf2664c0)$ gsutil cp beo.txt gs://DEVSHELL_PROJECT_ID
student_02_61105cf27e30@cloudshell:~ (qwiklabs-gcp-02-8288bf2664c0)$ gsutil cp bro.txt gs://$DEVSHELL_PROJECT_ID
Copying file://bro.txt [Content-Type=text/plain]...
/ [1 files][   91.0 B/   91.0 B]                                                
Operation completed over 1 objects/91.0 B.                                       
student_02_61105cf27e30@cloudshell:~ (qwiklabs-gcp-02-8288bf2664c0)$ gsutil cp beo.txt gs://$DEVSHELL_PROJECT_ID
Copying file://beo.txt [Content-Type=text/plain]...
/ [1 files][   91.0 B/   91.0 B]                                                
Operation completed over 1 objects/91.0 B.                                       
student_02_61105cf27e30@cloudshell:~ (qwiklabs-gcp-02-8288bf2664c0)$ gsutil cp khdb.txt gs://$DEVSHELL_PROJECT_ID
Copying file://khdb.txt [Content-Type=text/plain]...
/ [1 files][   91.0 B/   91.0 B]                                                
Operation completed over 1 objects/91.0 B.                                       
student_02_61105cf27e30@cloudshell:~ (qwiklabs-gcp-02-8288bf2664c0)$
```
![image](https://github.com/user-attachments/assets/38d69ce9-896a-4e1a-b91a-27c5da7f6a4d)
