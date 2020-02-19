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
ms.openlocfilehash: 73fccbc093365565fdc4062715b517e62eed3e7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="41387-102">設定 SCOM 監控</span><span class="sxs-lookup"><span data-stu-id="41387-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41387-103">_**主題上次修改日期：** 2012年-10-04_</span><span class="sxs-lookup"><span data-stu-id="41387-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="41387-104">移轉至 Microsoft Lync Server 2013 之後，您必須完成幾項工作來設定 Lync Server 2013 來使用 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="41387-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="41387-105">將 Lync Server 2010 更新套用至選取來管理集中探索邏輯的伺服器。</span><span class="sxs-lookup"><span data-stu-id="41387-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="41387-106">更新集中探索候選伺服器登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="41387-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="41387-107">設定主要的 System Center Operations Manager 管理伺服器以覆寫候選集中探索節點。</span><span class="sxs-lookup"><span data-stu-id="41387-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="41387-108">執行各項工作的指示提供於下。</span><span class="sxs-lookup"><span data-stu-id="41387-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="41387-109">**將 Lync Server 2010 更新套用至選取來管理集中探索邏輯的伺服器。**</span><span class="sxs-lookup"><span data-stu-id="41387-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="41387-110">選取安裝有 System Center Operations Manager 代理程式檔案，並設定為候選探索節點的伺服器。</span><span class="sxs-lookup"><span data-stu-id="41387-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="41387-111">將 Lync Server 2010 更新套用至這台伺服器。</span><span class="sxs-lookup"><span data-stu-id="41387-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="41387-112">請參閱主題[適用於 Lync Server 2010 的更新](apply-lync-server-2010-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="41387-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="41387-113">**更新集中探索候選伺服器登錄機碼。**</span><span class="sxs-lookup"><span data-stu-id="41387-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="41387-114">選取來管理集中探索邏輯的伺服器，開啟 [Windows PowerShell 命令視窗。</span><span class="sxs-lookup"><span data-stu-id="41387-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="41387-115">在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="41387-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="41387-p102">編輯登錄時，如果登錄機碼已經存在，可能會顯示命令失敗的錯誤。如果您遇到這個問題，可以安心忽略錯誤。</span><span class="sxs-lookup"><span data-stu-id="41387-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="41387-118">**設定主要的 System Center Operations Manager 管理伺服器以覆寫候選集中探索監看員節點。**</span><span class="sxs-lookup"><span data-stu-id="41387-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="41387-119">在已安裝 System Center Operations Manager 主控台的電腦上，展開 **[管理組件物件]**，然後選取 **[物件探索]**。</span><span class="sxs-lookup"><span data-stu-id="41387-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="41387-120">按一下 **[變更領域...]**。</span><span class="sxs-lookup"><span data-stu-id="41387-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="41387-121">從 **[管理組件物件領域]** 頁面，選取 **[LS 探索候選]**。</span><span class="sxs-lookup"><span data-stu-id="41387-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="41387-122">將 **[LS 探索候選有效值]** 覆寫為先前程序中選取的候選伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="41387-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="41387-123">最後，為了完成變更，請重新啟動 System Center Operations Manager Root Management Server 上的健全狀況服務。</span><span class="sxs-lookup"><span data-stu-id="41387-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

