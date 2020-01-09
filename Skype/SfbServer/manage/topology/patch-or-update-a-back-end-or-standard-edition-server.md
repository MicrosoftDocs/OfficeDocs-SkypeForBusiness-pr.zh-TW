---
title: 在商務用 Skype Server 中修補或更新後端伺服器或標準版伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 摘要：瞭解如何在商務用 Skype Server 的後端伺服器上安裝更新或修補程式。
ms.openlocfilehash: a88224c508426d16217adb87693515314b03e40f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991498"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="21aef-103">在商務用 Skype Server 中修補或更新後端伺服器或標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="21aef-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="21aef-104">**摘要：** 瞭解如何在商務用 Skype Server 的後端伺服器上安裝更新或修補程式。</span><span class="sxs-lookup"><span data-stu-id="21aef-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="21aef-105">本主題說明如何在企業版後端伺服器或標準版伺服器上安裝更新。</span><span class="sxs-lookup"><span data-stu-id="21aef-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="21aef-106">如果後端伺服器在您升級時至少有30分鐘的時間，使用者可能會進入復原模式。</span><span class="sxs-lookup"><span data-stu-id="21aef-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="21aef-107">完成升級後，後端伺服器再次與池中的前端伺服器連線之後，使用者就會回到完整功能。</span><span class="sxs-lookup"><span data-stu-id="21aef-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="21aef-108">如果升級所需的時間少於30分鐘，使用者將不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="21aef-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="21aef-109">更新後端伺服器或標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="21aef-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="21aef-110">以 CsAdministrator 角色成員的身分登入您要升級的伺服器。</span><span class="sxs-lookup"><span data-stu-id="21aef-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="21aef-111">下載更新並將它解壓縮到本機硬碟。</span><span class="sxs-lookup"><span data-stu-id="21aef-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="21aef-112">啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype**]，然後按一下 [商務用**skype Server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="21aef-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="21aef-113">停止商務用 Skype Server 服務。</span><span class="sxs-lookup"><span data-stu-id="21aef-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="21aef-114">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="21aef-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="21aef-115">停止萬維網服務。</span><span class="sxs-lookup"><span data-stu-id="21aef-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="21aef-116">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="21aef-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="21aef-117">關閉所有商務用 Skype Server Management Shell 視窗。</span><span class="sxs-lookup"><span data-stu-id="21aef-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="21aef-118">安裝更新。</span><span class="sxs-lookup"><span data-stu-id="21aef-118">Install the update.</span></span>
    
8. <span data-ttu-id="21aef-119">啟動商務用 Skype Server 管理命令介面：請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype**]，然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="21aef-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="21aef-120">再次停止商務用 Skype Server services，以捕捉通用群組件緩存（GAC）-d 元件。</span><span class="sxs-lookup"><span data-stu-id="21aef-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="21aef-121">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="21aef-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="21aef-122">重新開機萬維網服務。</span><span class="sxs-lookup"><span data-stu-id="21aef-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="21aef-123">在命令列中，輸入：</span><span class="sxs-lookup"><span data-stu-id="21aef-123">At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="21aef-124">執行下列其中一項操作，以套用對 SQL Server 資料庫所做的變更：</span><span class="sxs-lookup"><span data-stu-id="21aef-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="21aef-125">如果這是企業版後端伺服器，且此伺服器上沒有 collocated 資料庫（例如 [封存] 或 [監視資料庫]），請在命令列中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="21aef-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="21aef-126">如果這是企業版後端伺服器，且此伺服器上有 collocated 資料庫，請在命令列中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="21aef-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="21aef-127">如果這是標準版 server，請在命令列輸入以下命令：</span><span class="sxs-lookup"><span data-stu-id="21aef-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
