---
title: 確認已完成使用者複製
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d883b5446c843ac8b79e2b29d15f8a1c99f0089
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="ffcd6-102">確認已完成使用者複製</span><span class="sxs-lookup"><span data-stu-id="ffcd6-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffcd6-103">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="ffcd6-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="ffcd6-104">執行**Move-CsUser** Cmdlet 時，可能會發生失敗，因為 Active Directory 網域服務（AD DS）和 Lync Server 2013 資料庫之間的使用者資訊因初始複寫不完整而不同步。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-104">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="ffcd6-105">成功完成 Lync Server 2013 User 複寫器服務的初始同步處理所需的時間，取決於主控 Lync Server 2013 集區之 Active Directory 樹系中主控的網域控制站數目。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="ffcd6-106">當您第一次啟動 Lync Server 2013 前端伺服器時，就會發生 Lync Server 2013 使用者複寫器服務初始同步處理常式。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="ffcd6-107">完成後，則是根據使用者複寫器間隔來進行同步化。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="ffcd6-108">在執行 **Move-CsUser** Cmdlet 之前，請完成下列步驟來確認已完成使用者複寫。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-108">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="ffcd6-109">確認使用者複寫已完成</span><span class="sxs-lookup"><span data-stu-id="ffcd6-109">To verify user replication has completed</span></span>

1.  <span data-ttu-id="ffcd6-110">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-110">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="ffcd6-111">按一下 [開始]\*\*\*\* 功能表，然後按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-111">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="ffcd6-112">輸入 **eventvwr.exe**，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-112">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="ffcd6-113">在事件檢視器中，按一下 [應用程式及服務記錄檔]\*\*\*\* 予以展開，然後選取 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-113">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="ffcd6-114">在 [動作]\*\*\*\* 窗格中，按一下 [篩選目前的記錄]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-114">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="ffcd6-115">在 [事件來源]\*\*\*\* 清單中，按一下 [LS 使用者複寫器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-115">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="ffcd6-116">在 **\<All Event IDs\>** [輸入**30024** ] 中，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-116">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="ffcd6-117">在篩選後事件清單的 [一般]\*\*\*\* 索引標籤上，尋找有無任何項目指出使用者複寫成功的項目。</span><span class="sxs-lookup"><span data-stu-id="ffcd6-117">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

