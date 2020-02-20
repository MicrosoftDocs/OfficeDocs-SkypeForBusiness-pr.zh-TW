---
title: Lync Server 2013： 復原已移轉的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbc2c46b462ec50c1f5796a9a6a03cd39f7b44dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="e7f14-102">回復移轉 Lync Server 2013 中的使用者</span><span class="sxs-lookup"><span data-stu-id="e7f14-102">Roll back migrated users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7f14-103">_**主題上次修改日期：** 2012年-10-07_</span><span class="sxs-lookup"><span data-stu-id="e7f14-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="e7f14-104">如果您需要回復整合的連絡人存放區功能，，回復連絡人，只有當您將使用者移回至 Exchange 2010 或 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="e7f14-104">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="e7f14-105">若要回復，停用使用者的原則，然後執行 [ **Invoke-csucsrollback** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e7f14-105">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="e7f14-106">只執行**Invoke-csucsrollback**單獨不足以確保永久回復，因為如果原則未停用整合連絡人存放區移轉也會重新啟動。</span><span class="sxs-lookup"><span data-stu-id="e7f14-106">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="e7f14-107">例如，如果使用者復原，因為 Exchange 2013 會回復至 Exchange 2010 和使用者的信箱然後移至 Exchange 2013，整合連絡人存放區移轉將會被起始再次七天之後復原，只要整合的連絡人存放區仍維持啟用的使用者服務原則中的使用者。</span><span class="sxs-lookup"><span data-stu-id="e7f14-107">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7f14-108"><STRONG>Move-csuser</STRONG> cmdlet 會自動回復使用者的連絡人存放區從 Exchange 2013 到 Lync Server 2013 在下列情況：</span><span class="sxs-lookup"><span data-stu-id="e7f14-108">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e7f14-109">當使用者從 Lync Server 2013 移至 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="e7f14-109">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7f14-110">當使用者是跨部署移轉，例如當使用者從移 Lync Online 至 Lync Server 2013 內部部署，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="e7f14-110">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7f14-111">從備份資料庫匯入整合連絡人存放區資料可能會導致整合連絡人存放區資料和損毀如果整合連絡人存放區模式變更之間匯出及匯入的使用者資料。</span><span class="sxs-lookup"><span data-stu-id="e7f14-111">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import.</span></span> <span data-ttu-id="e7f14-112">例如：</span><span class="sxs-lookup"><span data-stu-id="e7f14-112">For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e7f14-113">如果您匯出連絡人清單，才能在使用者的連絡人移轉至 Exchange 2013，然後，在移轉後匯入相同的資料，但是整合連絡人存放區資料和連絡人清單就會損毀。</span><span class="sxs-lookup"><span data-stu-id="e7f14-113">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7f14-114">如果您將使用者移轉至 Exchange 2013 之後，您可以匯出 userdata，回復移轉，然後從將資料匯入移轉後因任何原因，整合的連絡人存放區資料和連絡人清單就會損毀。</span><span class="sxs-lookup"><span data-stu-id="e7f14-114">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7f14-115">您將 Exchange 信箱從 Exchange 2013 移至 Exchange 2010 之前，Exchange 系統管理員必須確定，Lync Server 系統管理員已先回復 Lync Server 使用者連絡人從 Exchange 2013 到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="e7f14-115">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="e7f14-116">若要將回復到 Lync Server 整合連絡人存放區連絡人，請參閱本節稍後的 < 對復原整合連絡人存放區連絡人從 Exchange 2013 to Lync Server 2013 中，「 程序。</span><span class="sxs-lookup"><span data-stu-id="e7f14-116">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="e7f14-117">下列程序說明如何回復使用者的連絡人。</span><span class="sxs-lookup"><span data-stu-id="e7f14-117">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="e7f14-118">如果您使用**Move-csuser** cmdlet 來 Lync Server 2013 和 Lync Server 2010 之間移動使用者時，因為**Move-csuser** cmdlet 會自動回復 unifed 連絡人存放區時它將使用者從 Lync Server 2013 移至 Lync Server 2010 可以略過這些步驟。</span><span class="sxs-lookup"><span data-stu-id="e7f14-118">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="e7f14-119">**Move-csuser**不讓移轉至整合連絡人存放區會循環，如果使用者移回至 Lync Server 2013 停用整合連絡人存放區原則。</span><span class="sxs-lookup"><span data-stu-id="e7f14-119">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="e7f14-120">將回復使用者連絡人從 Lync Server 2013 到 Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e7f14-120">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="e7f14-121">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="e7f14-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7f14-122">停用回以便不被 remigrated rollback 之後復原使用者的整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="e7f14-122">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="e7f14-123">（執行這個步驟只有當您想要確保使用者將不會在未來的遷移時）。若要停用整合連絡人存放區針對個別使用者，請在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="e7f14-123">(Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="e7f14-124">例如：</span><span class="sxs-lookup"><span data-stu-id="e7f14-124">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="e7f14-125">之前先從 Lync Server 2013 的使用者移至 Lync Server 2010 中，將回復朋友清單中所指定使用者的 Lync 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="e7f14-125">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7f14-126">如果省略這個步驟，將會遺失朋友清單。</span><span class="sxs-lookup"><span data-stu-id="e7f14-126">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="e7f14-127">回復為指定的使用者。</span><span class="sxs-lookup"><span data-stu-id="e7f14-127">Roll back the specified users.</span></span> <span data-ttu-id="e7f14-128">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="e7f14-128">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="e7f14-129">例如：</span><span class="sxs-lookup"><span data-stu-id="e7f14-129">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7f14-130">我們不建議使用-Force 參數來強制執行復原。</span><span class="sxs-lookup"><span data-stu-id="e7f14-130">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="e7f14-131">如果您使用此選項，將會遺失使用者的連絡人。</span><span class="sxs-lookup"><span data-stu-id="e7f14-131">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="e7f14-132">將回復整合連絡人存放區連絡人從 Exchange 2013 到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7f14-132">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="e7f14-133">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="e7f14-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7f14-134">停用回以便不被 remigrated rollback 之後復原使用者的整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="e7f14-134">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="e7f14-135">若要停用整合連絡人存放區針對個別使用者，請在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="e7f14-135">To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="e7f14-136">例如：</span><span class="sxs-lookup"><span data-stu-id="e7f14-136">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="e7f14-137">回復為指定的使用者。</span><span class="sxs-lookup"><span data-stu-id="e7f14-137">Roll back the specified users.</span></span> <span data-ttu-id="e7f14-138">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="e7f14-138">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="e7f14-139">例如：</span><span class="sxs-lookup"><span data-stu-id="e7f14-139">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7f14-140">您必須先將回復 Lync Server 使用者]，然後再移 Exchange 2013 信箱。</span><span class="sxs-lookup"><span data-stu-id="e7f14-140">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="e7f14-141">Exchange 系統管理員會封鎖復原 Exchange，直到 Lync Server 復原已完成。</span><span class="sxs-lookup"><span data-stu-id="e7f14-141">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="e7f14-142">我們不建議使用-Force 參數來強制執行復原。</span><span class="sxs-lookup"><span data-stu-id="e7f14-142">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="e7f14-143">如果您使用此選項，將會遺失使用者的連絡人。</span><span class="sxs-lookup"><span data-stu-id="e7f14-143">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="e7f14-144">您將回復使用者到 Lync Server 之後，Exchange 系統管理員可以將回復 Exchange 使用者從 Exchange 2013 到 Exchange 2010。</span><span class="sxs-lookup"><span data-stu-id="e7f14-144">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

