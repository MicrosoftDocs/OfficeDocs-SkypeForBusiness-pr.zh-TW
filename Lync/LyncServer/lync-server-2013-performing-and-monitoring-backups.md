---
title: Lync Server 2013： 執行與監控備份
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
ms.openlocfilehash: cf3ba3dc27bf3849ad6c3434f4baf1fa28c07780
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="73604-102">執行與監控備份 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="73604-102">Performing and monitoring backups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73604-103">_**上次修改主題：** 2014年-05-15_</span><span class="sxs-lookup"><span data-stu-id="73604-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="73604-104">您的業務優先順序應磁碟機規格的備份和還原您的組織需求。</span><span class="sxs-lookup"><span data-stu-id="73604-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="73604-105">執行備份的伺服器和資料是國防版的第一行中規劃嚴重損壞。</span><span class="sxs-lookup"><span data-stu-id="73604-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="73604-106">執行 Lync Server 2013 服務或伺服器角色的電腦必須具備一份目前的拓撲、 目前的組態設定，與目前的原則，才能他們可以在其指定角色中的運作。</span><span class="sxs-lookup"><span data-stu-id="73604-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="73604-107">Lync Server 負責確保此資訊會傳遞至需要它每一部電腦。</span><span class="sxs-lookup"><span data-stu-id="73604-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="73604-108">**Export-csconfiguration**和**Import-csconfiguration**指令程式可用來備份及還原 Lync Server 拓撲、 組態設定和原則期間中央管理存放區升級。</span><span class="sxs-lookup"><span data-stu-id="73604-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="73604-109">**Export-csconfiguration** cmdlet 可讓您匯出的資料。ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="73604-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="73604-110">您可以再使用**Import-csconfiguration** cmdlet 可讀取的。ZIP 檔案，並還原中央管理存放區的拓撲、 組態設定和原則。</span><span class="sxs-lookup"><span data-stu-id="73604-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="73604-111">之後，Lync Server 複寫服務會將已還原的資訊複寫至其他執行 Lync Server 服務的電腦。</span><span class="sxs-lookup"><span data-stu-id="73604-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="73604-112">匯出及匯入組態資料的能力也會在位於周邊網路 (例如 Edge Server) 的電腦的初始設定期間使用。</span><span class="sxs-lookup"><span data-stu-id="73604-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="73604-113">當在周邊網路中設定的電腦，您必須先執行使用 CsConfiguration cmdlet 手動複寫： 您必須使用**Export-csconfiguration**匯出組態資料，然後複製。ZIP 檔案，以在周邊網路的電腦。</span><span class="sxs-lookup"><span data-stu-id="73604-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="73604-114">在那之後，您可以使用**Import-csconfiguration**和 LocalStore 參數匯入資料。</span><span class="sxs-lookup"><span data-stu-id="73604-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="73604-115">您只需要進行此一次。</span><span class="sxs-lookup"><span data-stu-id="73604-115">You only have to do this one time.</span></span> <span data-ttu-id="73604-116">在那之後，將會自動進行複寫。</span><span class="sxs-lookup"><span data-stu-id="73604-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="73604-117">誰可以執行此 cmdlet： 根據預設，下列群組的成員會獲授權在本機上執行**Export-csconfiguration** cmdlet: RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="73604-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="73604-118">若要傳回的所有 RBAC 角色清單，此 cmdlet 會指派給 （包括任何自訂 RBAC 角色，您自行建立），請在 Windows PowerShell 提示字元中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="73604-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="73604-119">所有的 SQL 2012 後端資料庫是應該備份根據[SQL 最佳作法](https://go.microsoft.com/fwlink/p/?linkid=290716)。</span><span class="sxs-lookup"><span data-stu-id="73604-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](https://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="73604-120">應執行的災害復原規劃 Lync Server 2013 基礎結構的一般測試，盡可能模擬實際執行環境在實驗室環境中。</span><span class="sxs-lookup"><span data-stu-id="73604-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="73604-121">如需有關嚴重損壞修復測試每月的工作，請參閱。</span><span class="sxs-lookup"><span data-stu-id="73604-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="73604-122">請注意的備份頻率可以都調整，根據您的還原點和復原點目標。</span><span class="sxs-lookup"><span data-stu-id="73604-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="73604-123">最佳作法是，快照一般、 定期一天之內。</span><span class="sxs-lookup"><span data-stu-id="73604-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="73604-124">一般而言，您應該執行完整備份，每隔 24 小時。</span><span class="sxs-lookup"><span data-stu-id="73604-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="73604-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="73604-125">See Also</span></span>


[<span data-ttu-id="73604-126">Import-csconfiguration</span><span class="sxs-lookup"><span data-stu-id="73604-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="73604-127">Export-csconfiguration</span><span class="sxs-lookup"><span data-stu-id="73604-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="73604-128">SQL 最佳作法</span><span class="sxs-lookup"><span data-stu-id="73604-128">SQL best practices</span></span>](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

