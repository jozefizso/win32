---
title: Creating a Job
description: To create a transfer job, call the IBackgroundCopyManager CreateJob method.
ms.assetid: 'a7d9feef-4beb-4ae5-9453-9157ee3ec0e8'
keywords: ["transfer job BITS", "transfer job BITS , creating"]
---

# Creating a Job

To create a transfer job, call the [**IBackgroundCopyManager::CreateJob**](ibackgroundcopymanager-createjob.md) method. After BITS creates the job, [add files to the job](adding-files-to-a-job.md) and [modify the job's properties](setting-and-retrieving-the-properties-of-a-job.md) as appropriate for your application. To activate the job in the queue, call the [**IBackgroundCopyJob::Resume**](ibackgroundcopyjob-resume.md) method.

The [**CreateJob**](ibackgroundcopymanager-createjob.md) method creates a GUID that uniquely identifies the job. You use the GUID to [retrieve the job from the transfer queue](ibackgroundcopymanager-getjob.md). The display name that you provide when you create the job is not unique; more than one job can use the same name.

BITS limits the number of jobs in the queue to 300 jobs and the number of jobs that a user can create to 60 job. These limits do not apply to administrators or services. To change these default limits, see [Group Policies](group-policies.md).

**Prior to Windows Vista:** There are no limits to the number of jobs in the queue or the number of jobs that a user can create.

The following example shows how to create a download job. The example assumes the g\_pbcm variable is a valid [**IBackgroundCopyManager**](ibackgroundcopymanager.md) interface pointer. For details on how to create the **IBackgroundCopyManager** interface pointer, see [Connecting to the BITS Service](connecting-to-the-bits-service.md).


```C++
HRESULT hr;
GUID JobId;
IBackgroundCopyJob* pJob = NULL;

//To create an upload job, replace BG_JOB_TYPE_DOWNLOAD with 
//BG_JOB_TYPE_UPLOAD or BG_JOB_TYPE_UPLOAD_REPLY.
hr = g_pbcm->CreateJob(L"MyJobName", BG_JOB_TYPE_DOWNLOAD, &amp;JobId, &amp;pJob);
if (SUCCEEDED(hr))
{
  //Save the JobId for later reference. 
  //Modify the job's property values.
  //Add files to the job.
  //Activate (resume) the job in the transfer queue.
}
```



To get the latest [**IBackgroundCopyJob**](ibackgroundcopyjob.md) interface, call the **IBackgroundCopyJob::QueryInterface** method. The following example shows how to get the [**IBackgroundCopyJob4**](ibackgroundcopyjob4.md) interface.


```C++
  HRESULT hr = S_OK;
  IBackgroundCopyJob* pJob = NULL;
  IBackgroundCopyJob4* pJob4 = NULL;

  hr = pJob->QueryInterface(__uuidof(IBackgroundCopyJob4), (void**)&amp;pJob4);
  pJob->Release();
  if (FAILED(hr))
  {
    wprintf(L"pJob->QueryInterface failed with 0x%x.\n", hr);
    goto cleanup;
  }
```



 

 



