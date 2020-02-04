---
title: 設定 SCOM 監控
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7904edf9723dacdd28f69a75bec17cb5db3c2061
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="321a7-102">設定 SCOM 監控</span><span class="sxs-lookup"><span data-stu-id="321a7-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="321a7-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="321a7-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="321a7-104">遷移至 Microsoft Lync Server 2013 之後，您必須完成幾項工作，才能將 Lync Server 2013 設定為與 System Center Operations Manager 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="321a7-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="321a7-105">將 Lync Server 2010 更新套用至選擇的伺服器，以管理集中式發現邏輯。</span><span class="sxs-lookup"><span data-stu-id="321a7-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="321a7-106">更新中央探索候選伺服器登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="321a7-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="321a7-107">設定您的主要系統中心作業管理員管理伺服器來覆寫候選的中央探索節點。</span><span class="sxs-lookup"><span data-stu-id="321a7-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="321a7-108">以下提供執行其中每個任務的指示。</span><span class="sxs-lookup"><span data-stu-id="321a7-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="321a7-109">**將 Lync Server 2010 更新套用至選擇的伺服器，以管理集中式發現邏輯。**</span><span class="sxs-lookup"><span data-stu-id="321a7-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="321a7-110">選擇安裝系統中心作業管理員代理檔案的伺服器，並將其設定為候選搜尋節點。</span><span class="sxs-lookup"><span data-stu-id="321a7-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="321a7-111">將 Lync Server 2010 更新套用至此伺服器。</span><span class="sxs-lookup"><span data-stu-id="321a7-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="321a7-112">請參閱[應用 Lync Server 2010 更新](apply-lync-server-2010-updates.md)主題。</span><span class="sxs-lookup"><span data-stu-id="321a7-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="321a7-113">**更新中央探索候選伺服器登錄機碼。**</span><span class="sxs-lookup"><span data-stu-id="321a7-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="321a7-114">在伺服器上選擇要管理中央探索邏輯，請開啟 Windows PowerShell 命令視窗。</span><span class="sxs-lookup"><span data-stu-id="321a7-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="321a7-115">在命令列中，輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="321a7-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="321a7-116">每當您編輯註冊表時，如果登錄機碼已存在，您可能會遇到「命令失敗」的錯誤。</span><span class="sxs-lookup"><span data-stu-id="321a7-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="321a7-117">如果您遇到這種情況，您可以放心地忽略錯誤。</span><span class="sxs-lookup"><span data-stu-id="321a7-117">If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="321a7-118">**設定您的主要系統中心作業管理員管理伺服器，以覆寫候選的中央探索觀察程式節點。**</span><span class="sxs-lookup"><span data-stu-id="321a7-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="321a7-119">在已安裝 System Center Operations Manager 主控台的電腦上，展開 [**管理套件物件**]，然後選取 [**物件發現**]。</span><span class="sxs-lookup"><span data-stu-id="321a7-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="321a7-120">按一下 [**變更範圍]。**</span><span class="sxs-lookup"><span data-stu-id="321a7-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="321a7-121">從 [**範圍管理套件物件**] 頁面上，選取 [ **LS 探索候選**]。</span><span class="sxs-lookup"><span data-stu-id="321a7-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="321a7-122">在先前的程式中，將**LS 搜尋候選生效值**覆寫為所選擇的候選伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="321a7-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="321a7-123">最後，若要完成您的變更，請重新開機 System Center Operations Manager 根管理伺服器上的健康情況服務。</span><span class="sxs-lookup"><span data-stu-id="321a7-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

