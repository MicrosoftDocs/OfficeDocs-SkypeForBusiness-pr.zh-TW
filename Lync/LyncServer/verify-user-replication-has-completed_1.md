---
title: 確認已完成使用者複製
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13f4fbd2e0d0236f9dc404ffa84ab2f0ce385e2a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="436f8-102">確認已完成使用者複製</span><span class="sxs-lookup"><span data-stu-id="436f8-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="436f8-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="436f8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="436f8-104">當您執行**CsLegacyUser** Cmdlet 時，您可能會因 Active Directory 網域服務（AD DS）與 Lync Server 2013 資料庫之間的使用者資訊無法同步處理，而導致無法同步處理，因為初始複製不完整。</span><span class="sxs-lookup"><span data-stu-id="436f8-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="436f8-105">成功完成 Lync Server 2013 使用者複製程式服務的初始同步處理所需的時間，取決於託管在 Lync Server 2013 池之 Active Directory 林中的網網域控制站數目。</span><span class="sxs-lookup"><span data-stu-id="436f8-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="436f8-106">Lync server 2013 的使用者複製服務初始同步處理常式是在 Lync Server 2013 前端伺服器第一次啟動時進行。</span><span class="sxs-lookup"><span data-stu-id="436f8-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="436f8-107">之後，就會根據使用者複製程式間隔來同步處理。</span><span class="sxs-lookup"><span data-stu-id="436f8-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="436f8-108">完成下列步驟以驗證使用者複製已完成，然後再執行**CsLegacyUser** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="436f8-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="436f8-109">驗證使用者複製已完成</span><span class="sxs-lookup"><span data-stu-id="436f8-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="436f8-110">從 Lync Server 2013 前端伺服器，按一下 [**開始**] 功能表，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="436f8-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="436f8-111">輸入**eventvwr.exe** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="436f8-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="436f8-112">在事件檢視器中，按一下 [**應用程式和服務記錄**] 加以展開，然後選取 [Lync Server]。</span><span class="sxs-lookup"><span data-stu-id="436f8-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="436f8-113">在 [**動作**] 窗格中，按一下 [**篩選目前的記錄**]。</span><span class="sxs-lookup"><span data-stu-id="436f8-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="436f8-114">從 [**事件來源**] 清單中，按一下 [ **LS 使用者複製**]。</span><span class="sxs-lookup"><span data-stu-id="436f8-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="436f8-115">在\*\* \<所有事件識別碼\> **中輸入**30024\*\* ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="436f8-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="436f8-116">在 [篩選的事件] 清單中的 [一般] 索引標籤上，尋找 **[** 使用者複製已成功完成] 的專案。</span><span class="sxs-lookup"><span data-stu-id="436f8-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

