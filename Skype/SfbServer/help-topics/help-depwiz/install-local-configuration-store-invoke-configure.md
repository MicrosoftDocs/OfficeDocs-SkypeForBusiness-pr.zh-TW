---
title: 安裝本機設定存放區叫用 (設定)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 若要開始安裝儲存中央管理存放區之本機唯讀副本的資料庫，請選取 [從已安裝及已設定的中央管理存放區中使用拓撲產生器所發佈的定義設定]，或從其他媒體讀取已定義的設定。 針對組織內部網路上的機器，選取 [自動從中央管理存放區取回設定]。
ms.openlocfilehash: f0e2f54e83831cf6ad626b5d83cf068f40110f07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827203"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="7980c-104">安裝本機設定存放區叫用 (設定)</span><span class="sxs-lookup"><span data-stu-id="7980c-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="7980c-105">若要開始安裝儲存中央管理存放區之本機唯讀副本的資料庫，請選取 [從已安裝及已設定的中央管理存放區中使用拓撲產生器所發佈的定義設定]，或從其他媒體讀取已定義的設定。</span><span class="sxs-lookup"><span data-stu-id="7980c-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="7980c-106">針對組織內部網路上的機器，選取 **[自動從中央管理存放區取回** 設定]。</span><span class="sxs-lookup"><span data-stu-id="7980c-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="7980c-107">若要在 Edge Server 上安裝中央管理存放區的複本，請選取從便攜媒體（例如 USB 快閃記憶體磁片磁碟機、USB 硬碟、CD-ROM 或其他媒體）讀取設定檔的匯出副本。</span><span class="sxs-lookup"><span data-stu-id="7980c-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7980c-108">若要在 Edge Server 上安裝本機設定存放區，則設定資訊必須採用從中央管理存放區匯出的格式，方法是執行 Windows PowerShell Cmdlet：  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="7980c-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="7980c-109">選取適當的選項後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7980c-109">After you have selected the appropriate option, click **Next**.</span></span>
  

