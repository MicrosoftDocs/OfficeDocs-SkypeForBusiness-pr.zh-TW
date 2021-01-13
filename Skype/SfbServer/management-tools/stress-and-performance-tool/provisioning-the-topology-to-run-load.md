---
title: 在壓力和效能案例中布建拓撲以執行負載
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 商務用 Skype Server 2015 拓撲變更或布建，以允許使用者成功執行壓力和效能工具。
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814933"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="534b4-103">在壓力和效能案例中布建拓撲以執行負載</span><span class="sxs-lookup"><span data-stu-id="534b4-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="534b4-104">商務用 Skype Server 2015 拓撲變更或布建，以允許使用者成功執行壓力和效能工具。</span><span class="sxs-lookup"><span data-stu-id="534b4-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="534b4-105">根據您現有的商務用 Skype Server 2015 部署設定和設定，您可能需要在環境中進行一些變更。</span><span class="sxs-lookup"><span data-stu-id="534b4-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="534b4-106">以下是這些變更的清單：</span><span class="sxs-lookup"><span data-stu-id="534b4-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="534b4-107">設定 Windows PowerShell 執行原則為無限制。</span><span class="sxs-lookup"><span data-stu-id="534b4-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="534b4-108">如果您不確定目前的設定，您可以開啟商務用 Skype Server 管理命令介面，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="534b4-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="534b4-109">若未傳回無限制的值，則必須執行下列下一步：</span><span class="sxs-lookup"><span data-stu-id="534b4-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="534b4-110">若要有效地設定商務用 Skype Server，您必須：</span><span class="sxs-lookup"><span data-stu-id="534b4-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="534b4-111">熟悉商務用 Skype Server 2015 拓撲 (例如電腦名稱稱、服務實例、網站名稱和原則) 。</span><span class="sxs-lookup"><span data-stu-id="534b4-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="534b4-112">將一些建立的使用者指派給群組，例如回應群組搜尋群組 (例如，SIP URIs) 。</span><span class="sxs-lookup"><span data-stu-id="534b4-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="534b4-113">若要從命令列執行腳本，您可以使用：</span><span class="sxs-lookup"><span data-stu-id="534b4-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="534b4-114">一般來說，當您從這個套件執行腳本後，所產生的追蹤會儲存在執行腳本的相同路徑中。</span><span class="sxs-lookup"><span data-stu-id="534b4-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="534b4-115">也有命名格式 \<scriptname\> $h $ m $s.txt。</span><span class="sxs-lookup"><span data-stu-id="534b4-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="534b4-116">因此，如果您在 12:15 PM 執行 ArchivingPolicy.ps1，您會收到名為 ArchivingPolicy121500.txt 的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="534b4-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="534b4-117">當我們為伺服器設定提供這些範例後，您可以在完成執行負載測試後，修改設定並還原或回滾。</span><span class="sxs-lookup"><span data-stu-id="534b4-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

