---
title: 確認已完成使用者複製
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51ff7889b97a58298256cc1a1de3a5d4f901608
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518000"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="1ea86-102">確認已完成使用者複製</span><span class="sxs-lookup"><span data-stu-id="1ea86-102">Verify user replication has completed</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ea86-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1ea86-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1ea86-104">在執行 **Move-CsLegacyUser** Cmdlet 時，您可能會因 Active Directory 網域服務 (AD DS) 和 Lync Server 2013 資料庫之間的使用者資訊而失敗，因為初始複寫不完整，所以您可能會遇到失敗。</span><span class="sxs-lookup"><span data-stu-id="1ea86-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="1ea86-105">成功完成 Lync Server 2013 User 複寫器服務的初始同步處理所需的時間，取決於主控 Lync Server 2013 集區之 Active Directory 樹系中主控的網域控制站數目。</span><span class="sxs-lookup"><span data-stu-id="1ea86-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="1ea86-106">當您第一次啟動 Lync Server 2013 前端伺服器時，就會發生 Lync Server 2013 使用者複寫器服務初始同步處理常式。</span><span class="sxs-lookup"><span data-stu-id="1ea86-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="1ea86-107">完成後，則是根據使用者複寫器間隔來進行同步化。</span><span class="sxs-lookup"><span data-stu-id="1ea86-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="1ea86-108">在執行 **Move-CsLegacyUser** Cmdlet 之前，請完成下列步驟來確認已完成使用者複寫。</span><span class="sxs-lookup"><span data-stu-id="1ea86-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="1ea86-109">確認使用者複寫已完成</span><span class="sxs-lookup"><span data-stu-id="1ea86-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="1ea86-110">在 Lync Server 2013 前端伺服器上，按一下 [ **開始** ] 功能表，然後按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="1ea86-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="1ea86-111">輸入 **eventvwr.exe**，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ea86-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="1ea86-112">在事件檢視器中，按一下 [應用程式及服務記錄檔]\*\*\*\* 予以展開，然後選取 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="1ea86-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="1ea86-113">在 [動作]\*\*\*\* 窗格中，按一下 [篩選目前的記錄]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ea86-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="1ea86-114">在 [事件來源]\*\*\*\* 清單中，按一下 [LS 使用者複寫器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ea86-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="1ea86-115">在 **\<All Event IDs\>** [輸入 **30024** ] 中，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1ea86-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="1ea86-116">在篩選後事件清單的 [一般]\*\*\*\* 索引標籤上，尋找有無任何項目指出使用者複寫成功的項目。</span><span class="sxs-lookup"><span data-stu-id="1ea86-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

