---
title: 設定 SCOM 監視
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 遷移至 Microsoft 商務用 Skype Server 2019 之後, 您必須完成幾個工作, 才能設定商務用 Skype Server 2019, 以搭配 System Center Operations Manager 使用。
ms.openlocfilehash: 141154a8bd678f15fcc919b2dd70a50ca9d4dcca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190024"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="16203-103">設定 SCOM 監視</span><span class="sxs-lookup"><span data-stu-id="16203-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="16203-104">遷移到商務用 Skype Server 2019 之後, 您必須完成幾個工作, 才能設定商務用 Skype Server 2019, 以搭配 System Center Operations Manager 使用。</span><span class="sxs-lookup"><span data-stu-id="16203-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="16203-105">將更新套用至選擇的伺服器以管理集中式發現邏輯。</span><span class="sxs-lookup"><span data-stu-id="16203-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="16203-106">更新中央探索候選伺服器登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="16203-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="16203-107">設定您的主要系統中心作業管理員管理伺服器來覆寫候選的中央探索節點。</span><span class="sxs-lookup"><span data-stu-id="16203-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="16203-108">以下提供執行其中每個任務的指示。</span><span class="sxs-lookup"><span data-stu-id="16203-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="16203-109">將更新套用至選擇的伺服器以管理集中式發現邏輯。</span><span class="sxs-lookup"><span data-stu-id="16203-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="16203-110">選擇安裝系統中心作業管理員代理檔案的伺服器, 並將其設定為候選搜尋節點。</span><span class="sxs-lookup"><span data-stu-id="16203-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="16203-111">將更新套用至此伺服器。</span><span class="sxs-lookup"><span data-stu-id="16203-111">Apply updates to this server.</span></span> <span data-ttu-id="16203-112">請參閱主題 [套用[更新](apply-updates.md)]。</span><span class="sxs-lookup"><span data-stu-id="16203-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="16203-113">更新中央探索候選伺服器登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="16203-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="16203-114">在伺服器上選擇要管理中央探索邏輯, 請開啟 Windows PowerShell 命令視窗。</span><span class="sxs-lookup"><span data-stu-id="16203-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="16203-115">在命令列中, 輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="16203-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="16203-116">每當您編輯註冊表時, 如果登錄機碼已存在, 您可能會遇到「命令失敗」的錯誤。</span><span class="sxs-lookup"><span data-stu-id="16203-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="16203-117">如果您遇到這種情況, 您可以放心地忽略錯誤。</span><span class="sxs-lookup"><span data-stu-id="16203-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="16203-118">設定您的主要系統中心作業管理員管理伺服器, 以覆寫候選的中央探索觀察程式節點。</span><span class="sxs-lookup"><span data-stu-id="16203-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="16203-119">在已安裝 System Center Operations Manager 主控台的電腦上, 展開 [**管理套件物件**], 然後選取 [**物件發現**]。</span><span class="sxs-lookup"><span data-stu-id="16203-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="16203-120">按一下 [**變更範圍**]</span><span class="sxs-lookup"><span data-stu-id="16203-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="16203-121">從 [**範圍管理套件物件**] 頁面上, 選取 [ **LS 探索候選**]。</span><span class="sxs-lookup"><span data-stu-id="16203-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="16203-122">在先前的程式中, 將**LS 搜尋候選生效值**覆寫為所選擇的候選伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="16203-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="16203-123">若要完成您的變更, 請重新開機 System Center Operations Manager 根管理伺服器上的健康情況服務。</span><span class="sxs-lookup"><span data-stu-id="16203-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

