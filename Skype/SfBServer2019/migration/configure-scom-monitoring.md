---
title: 設定 SCOM 監控
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在遷移至 Microsoft 商務用 Skype Server 2019 之後，您必須完成一些工作以設定商務用 Skype Server 2019，以與 System Center Operations Manager 搭配使用。
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754043"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="6cab8-103">設定 SCOM 監控</span><span class="sxs-lookup"><span data-stu-id="6cab8-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="6cab8-104">在遷移至商務用 Skype Server 2019 之後，您必須完成一些工作以設定商務用 Skype Server 2019，以與 System Center Operations Manager 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="6cab8-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="6cab8-105">將更新套用至選擇用來管理集中探索邏輯的伺服器。</span><span class="sxs-lookup"><span data-stu-id="6cab8-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="6cab8-106">更新集中探索候選伺服器登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="6cab8-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="6cab8-107">設定您的主要 System Center Operations Manager 管理伺服器以覆寫候選的中央探索節點。</span><span class="sxs-lookup"><span data-stu-id="6cab8-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="6cab8-108">執行各項工作的指示提供於下。</span><span class="sxs-lookup"><span data-stu-id="6cab8-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="6cab8-109">將更新套用至選擇用來管理集中探索邏輯的伺服器。</span><span class="sxs-lookup"><span data-stu-id="6cab8-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="6cab8-110">選取安裝有 System Center Operations Manager 代理程式檔案，並設定為候選探索節點的伺服器。</span><span class="sxs-lookup"><span data-stu-id="6cab8-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="6cab8-111">將更新套用至此伺服器。</span><span class="sxs-lookup"><span data-stu-id="6cab8-111">Apply updates to this server.</span></span> <span data-ttu-id="6cab8-112">請參閱主題套用[更新](apply-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="6cab8-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="6cab8-113">更新集中探索候選伺服器登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="6cab8-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="6cab8-114">在選擇用來管理集中探索邏輯的伺服器上，開啟 [Windows PowerShell] 命令視窗。</span><span class="sxs-lookup"><span data-stu-id="6cab8-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="6cab8-115">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="6cab8-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="6cab8-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span><span class="sxs-lookup"><span data-stu-id="6cab8-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="6cab8-117">If you experience this, you can safely ignore the error.</span><span class="sxs-lookup"><span data-stu-id="6cab8-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="6cab8-118">設定您的主要 System Center Operations Manager 管理伺服器以覆寫候選的中央探索觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="6cab8-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="6cab8-119">在已安裝 System Center Operations Manager 主控台的電腦上，展開 **[管理組件物件]**，然後選取 **[物件探索]**。</span><span class="sxs-lookup"><span data-stu-id="6cab8-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="6cab8-120">按一下 [**變更範圍**]</span><span class="sxs-lookup"><span data-stu-id="6cab8-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="6cab8-121">從 **[管理組件物件領域]** 頁面，選取 **[LS 探索候選]**。</span><span class="sxs-lookup"><span data-stu-id="6cab8-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="6cab8-122">將 **[LS 探索候選有效值]** 覆寫為先前程序中選取的候選伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="6cab8-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="6cab8-123">若要完成變更，請重新開機 System Center Operations Manager Root Management Server 上的健康情況服務。</span><span class="sxs-lookup"><span data-stu-id="6cab8-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

