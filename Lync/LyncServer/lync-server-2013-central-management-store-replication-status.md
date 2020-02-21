---
title: Lync Server 2013： 中央管理存放區複寫狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ada48a9510be6d6deecedf063156abadbd59162f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="8deb1-102">Lync Server 2013 中的中央管理存放區複寫狀態</span><span class="sxs-lookup"><span data-stu-id="8deb1-102">Central management store replication status in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8deb1-103">_**主題上次修改日期：** 2015年-01-26_</span><span class="sxs-lookup"><span data-stu-id="8deb1-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="8deb1-104">當系統管理員進行變更的某種類型的 Lync Server （例如，當系統管理員會建立新的語音原則或變更的 Address Book Server 組態設定時） 會記錄該變更中央管理存放區中。</span><span class="sxs-lookup"><span data-stu-id="8deb1-104">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="8deb1-105">接著，變更然後必須複寫到所有執行 Lync Server 服務或伺服器角色的電腦。</span><span class="sxs-lookup"><span data-stu-id="8deb1-105">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="8deb1-106">若要將資料複寫，（中央管理伺服器上執行） 主要複寫器會建立已變更的組態資料的快照集。</span><span class="sxs-lookup"><span data-stu-id="8deb1-106">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="8deb1-107">此快照集的複本再傳送至每個執行 Lync Server 服務或伺服器角色的電腦。</span><span class="sxs-lookup"><span data-stu-id="8deb1-107">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="8deb1-108">在這些電腦上的複寫代理程式接收快照集，並將已變更的資料上傳。</span><span class="sxs-lookup"><span data-stu-id="8deb1-108">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="8deb1-109">代理程式接著會傳送主要複寫器郵件，報告的最新的複寫狀態。</span><span class="sxs-lookup"><span data-stu-id="8deb1-109">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="8deb1-110">Get-csmanagementstorereplicationstatus cmdlet 可讓您確認任何 （或所有） 在組織中的 Lync Server 電腦的複寫狀態。</span><span class="sxs-lookup"><span data-stu-id="8deb1-110">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="8deb1-111">誰可以執行此指令程式？</span><span class="sxs-lookup"><span data-stu-id="8deb1-111">Who can run this cmdlet?</span></span> <span data-ttu-id="8deb1-112">根據預設，下列群組的成員會獲授權在本機上執行 Get-csmanagementstorereplicationstatus cmdlet: RTCUniversalUserAdmins、 RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="8deb1-112">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="8deb1-113">若要傳回所有 （包括您自行建立的任何自訂 RBAC 角色） 已指派此 cmdlet 的 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8deb1-113">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="8deb1-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8deb1-114">See Also</span></span>


[<span data-ttu-id="8deb1-115">Get-csmanagementstorereplicationstatus</span><span class="sxs-lookup"><span data-stu-id="8deb1-115">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

