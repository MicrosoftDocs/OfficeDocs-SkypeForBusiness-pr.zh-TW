---
title: Lync Server 2013：執行及監視備份
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b79fdbaceff06155389d101570b23d6143b9bbcc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536746"
---
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="73f75-102">在 Lync Server 2013 中執行及監視備份</span><span class="sxs-lookup"><span data-stu-id="73f75-102">Performing and monitoring backups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73f75-103">_**主題上次修改日期：** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="73f75-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="73f75-104">您的業務優先順序應該會推動組織的備份與還原需求規格。</span><span class="sxs-lookup"><span data-stu-id="73f75-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="73f75-105">在規劃災難時，執行伺服器和資料的備份是第一項防禦工作。</span><span class="sxs-lookup"><span data-stu-id="73f75-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="73f75-106">執行 Lync Server 2013 服務或伺服器角色的電腦必須具有目前拓撲的複本、目前的設定，以及目前的原則，才能在其所指的角色中運作。</span><span class="sxs-lookup"><span data-stu-id="73f75-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="73f75-107">Lync Server 負責確保將此資訊傳送給每個需要的電腦。</span><span class="sxs-lookup"><span data-stu-id="73f75-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="73f75-108">**Export-CsConfiguration**和**Import-CsConfiguration** Cmdlet 是用來備份及還原您的 Lync Server 拓撲、設定設定，以及在中央管理存放區升級期間的原則。</span><span class="sxs-lookup"><span data-stu-id="73f75-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="73f75-109">**Export-CsConfiguration** Cmdlet 可讓您將資料匯出至。ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="73f75-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="73f75-110">然後，您可以使用 **Import-CsConfiguration** Cmdlet 來讀取該。ZIP 檔案，並將拓撲、設定設定和原則還原至中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="73f75-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="73f75-111">之後，Lync Server 的複寫服務會將還原的資訊複製到其他執行 Lync Server 服務的電腦。</span><span class="sxs-lookup"><span data-stu-id="73f75-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="73f75-112">在周邊網路中的電腦初始設定時，也會使用匯出及匯入設定資料的功能 (例如，Edge Servers) 。</span><span class="sxs-lookup"><span data-stu-id="73f75-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="73f75-113">當您設定周邊網路中的電腦時，您必須先使用 CsConfiguration Cmdlet 執行手動複寫：您必須使用 **Export-CsConfiguration** 匯出設定資料，然後再複製。在周邊網路中的電腦的 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="73f75-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="73f75-114">之後，您可以使用 **Import-CsConfiguration** 和 LocalStore 參數匯入資料。</span><span class="sxs-lookup"><span data-stu-id="73f75-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="73f75-115">您只需執行一次。</span><span class="sxs-lookup"><span data-stu-id="73f75-115">You only have to do this one time.</span></span> <span data-ttu-id="73f75-116">之後，就會自動進行複寫。</span><span class="sxs-lookup"><span data-stu-id="73f75-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="73f75-117">誰可以執行此 Cmdlet：根據預設，會授權下列群組的成員在本機執行 **Export-CsConfiguration** Cmdlet： RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="73f75-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="73f75-118">若要傳回所有 RBAC 角色的清單，此 Cmdlet 會指派給 (包含您自行建立的任何自訂 RBAC 角色) ，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="73f75-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="73f75-119">所有的 SQL 2012 後端資料庫應該依照每個 [sql 的最佳作法](https://go.microsoft.com/fwlink/p/?linkid=290716)來備份。</span><span class="sxs-lookup"><span data-stu-id="73f75-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](https://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="73f75-120">定期測試 Lync Server 2013 基礎結構的嚴重損壞修復計畫時，應該會在盡可能模仿實際執行環境的實驗室環境中執行。</span><span class="sxs-lookup"><span data-stu-id="73f75-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="73f75-121">如需有關嚴重損壞修復測試的詳細資訊，請參閱每月任務。</span><span class="sxs-lookup"><span data-stu-id="73f75-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="73f75-122">請注意，根據您的還原點和復原點目標，可以調整備份頻率。</span><span class="sxs-lookup"><span data-stu-id="73f75-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="73f75-123">最佳作法是在一天內定期進行定期快照。</span><span class="sxs-lookup"><span data-stu-id="73f75-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="73f75-124">一般來說，您應該每24小時執行一次完整備份。</span><span class="sxs-lookup"><span data-stu-id="73f75-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="73f75-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="73f75-125">See Also</span></span>


[<span data-ttu-id="73f75-126">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="73f75-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="73f75-127">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="73f75-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="73f75-128">SQL 最佳作法</span><span class="sxs-lookup"><span data-stu-id="73f75-128">SQL best practices</span></span>](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

