---
title: 在壓力與效能案例中，配拓拓撲以執行負載
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: 商務用 Skype Server 2015 拓撲變更或提供，以允許使用者成功執行壓力與效能工具。
ms.openlocfilehash: e58bfce5e618c6e62f272c0acb0b415cbb471d40
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992490"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="67801-103">在壓力與效能案例中，配拓拓撲以執行負載</span><span class="sxs-lookup"><span data-stu-id="67801-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="67801-104">商務用 Skype Server 2015 拓撲變更或提供，以允許使用者成功執行壓力與效能工具。</span><span class="sxs-lookup"><span data-stu-id="67801-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="67801-105">您可能需要在您的環境中進行一些變更，這取決於您現有的設定與商務用 Skype Server 2015 部署的配置。</span><span class="sxs-lookup"><span data-stu-id="67801-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="67801-106">以下是這些變更的清單：</span><span class="sxs-lookup"><span data-stu-id="67801-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="67801-107">將 [Windows PowerShell 執行原則] 設定為 [無限制]。</span><span class="sxs-lookup"><span data-stu-id="67801-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="67801-108">如果您不確定目前所設定的專案，您可以開啟商務用 Skype Server Management 命令介面，然後執行此命令：</span><span class="sxs-lookup"><span data-stu-id="67801-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="67801-109">如果沒有傳回不受限制的值，您必須執行下一步：</span><span class="sxs-lookup"><span data-stu-id="67801-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="67801-110">若要有效地設定商務用 Skype Server，您必須：</span><span class="sxs-lookup"><span data-stu-id="67801-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="67801-111">熟悉商務用 Skype Server 2015 拓撲（例如電腦名稱稱、服務實例、網站名稱及原則）。</span><span class="sxs-lookup"><span data-stu-id="67801-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="67801-112">指派一些建立給群組的使用者，例如回應群組查尋群組（例如 SIP Uri）。</span><span class="sxs-lookup"><span data-stu-id="67801-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="67801-113">若要從命令列執行腳本，您可以使用：</span><span class="sxs-lookup"><span data-stu-id="67801-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="67801-114">通常，在您執行此套件中的腳本之後，產生的追蹤會儲存在執行腳本之位置相同路徑中的檔案中。</span><span class="sxs-lookup"><span data-stu-id="67801-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="67801-115">還有命名格式， \<$h scriptname\>$ m $ s .txt。</span><span class="sxs-lookup"><span data-stu-id="67801-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="67801-116">因此，如果您在 12:15 PM 執行 ArchivingPolicy，您將會收到名為 ArchivingPolicy121500 的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="67801-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="67801-117">雖然我們為伺服器設定提供了這些範例，但在執行完負載測試之後，您可以修改配置並還原或回滾。</span><span class="sxs-lookup"><span data-stu-id="67801-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

