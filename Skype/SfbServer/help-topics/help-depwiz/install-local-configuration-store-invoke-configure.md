---
title: 安裝本機配置存儲區 (設定)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 若要開始安裝將保留中央管理儲存區的本機唯讀複本的資料庫, 您可以在從已安裝和設定的中央的 [拓撲建立器] 中, 選取 [使用拓撲建立器] 來檢索已定義的設定管理儲存, 或從其他媒體讀取已定義的配置。 針對貴組織內部網路上的電腦, 選取 [從中央管理儲存庫自動取得設定]。
ms.openlocfilehash: a9f72ca18c1e8848c52545ecc254dd2b142b8137
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193472"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="8d0a1-104">安裝本機配置存儲區 (設定)</span><span class="sxs-lookup"><span data-stu-id="8d0a1-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="8d0a1-105">若要開始安裝將保留中央管理儲存區的本機唯讀複本的資料庫, 您可以在從已安裝和設定的中央的 [拓撲建立器] 中, 選取 [使用拓撲建立器] 來檢索已定義的設定管理儲存, 或從其他媒體讀取已定義的配置。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="8d0a1-106">針對貴組織內部網路上的電腦, 選取 **[從中央管理儲存庫自動取得**設定]。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="8d0a1-107">如果您要在 Edge 伺服器上安裝中央管理儲存體的複本, 您可以選取以從便攜媒體 (例如 USB 快閃磁碟機、USB 硬碟磁碟機、cd-rom 或其他媒體) 讀取設定檔的匯出複本。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8d0a1-108">如果您要在 Edge 伺服器上安裝本機配置存放區, 則配置資訊必須是從中央管理存儲匯出的格式, 方法是執行 Windows PowerShell Cmdlet:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="8d0a1-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="8d0a1-109">選取適當的選項之後, 請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8d0a1-109">After you have selected the appropriate option, click **Next**.</span></span>
  

