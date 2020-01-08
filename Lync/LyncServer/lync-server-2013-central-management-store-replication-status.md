---
title: Lync Server 2013：一般管理存放區覆寫狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ce46b403e27d0a2b69f705b5bada026882eec7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="eb89f-102">Lync Server 2013 中的一般管理存放區覆寫狀態</span><span class="sxs-lookup"><span data-stu-id="eb89f-102">Central management store replication status in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb89f-103">_**主題上次修改日期：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="eb89f-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="eb89f-104">當系統管理員將某種類型變更為 Lync Server 時（例如，當系統管理員建立新的語音原則，或變更 [通訊錄服務器] 配置設定）時，這些變更會記錄在中央管理儲存區中。</span><span class="sxs-lookup"><span data-stu-id="eb89f-104">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="eb89f-105">接著，必須將變更複製到所有執行 Lync Server 服務或伺服器角色的電腦上。</span><span class="sxs-lookup"><span data-stu-id="eb89f-105">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="eb89f-106">若要複製資料，主要複製器（在中央管理伺服器上執行）會建立變更之設定資料的快照。</span><span class="sxs-lookup"><span data-stu-id="eb89f-106">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="eb89f-107">然後，會將此快照的複本傳送給執行 Lync Server 服務或伺服器角色的每個電腦。</span><span class="sxs-lookup"><span data-stu-id="eb89f-107">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="eb89f-108">在這些電腦上，複製代理程式會接收快照，並上傳已變更的資料。</span><span class="sxs-lookup"><span data-stu-id="eb89f-108">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="eb89f-109">然後，agent 就會傳送一封郵件的主複製器，報告最新的複製狀態。</span><span class="sxs-lookup"><span data-stu-id="eb89f-109">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="eb89f-110">CsManagementStoreReplicationStatus Cmdlet 可讓您確認貴組織中所有（或所有） Lync Server 電腦的複製狀態。</span><span class="sxs-lookup"><span data-stu-id="eb89f-110">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="eb89f-111">誰可以執行這個 Cmdlet？</span><span class="sxs-lookup"><span data-stu-id="eb89f-111">Who can run this cmdlet?</span></span> <span data-ttu-id="eb89f-112">根據預設，下列群組的成員有權在本機執行 CsManagementStoreReplicationStatus Cmdlet： RTCUniversalUserAdmins、RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="eb89f-112">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="eb89f-113">若要傳回這個 Cmdlet 所指派的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請在 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="eb89f-113">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="eb89f-114">請參閱</span><span class="sxs-lookup"><span data-stu-id="eb89f-114">See Also</span></span>


[<span data-ttu-id="eb89f-115">CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="eb89f-115">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

