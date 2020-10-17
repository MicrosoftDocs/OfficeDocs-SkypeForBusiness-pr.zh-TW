---
title: Lync Server 2013：退回遷移的使用者
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
ms.openlocfilehash: deda1ec30ef5267acd8b3826b77077e7902d98e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511260"
---
# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="e7551-102">在 Lync Server 2013 中復原已遷移的使用者</span><span class="sxs-lookup"><span data-stu-id="e7551-102">Roll back migrated users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7551-103">_**主題上次修改日期：** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="e7551-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="e7551-104">如果您需要回復「整合連絡人存放區」功能，請僅在將使用者移回 Exchange 2010 或 Lync Server 2010 時，才復原連絡人。</span><span class="sxs-lookup"><span data-stu-id="e7551-104">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="e7551-105">若要回退，請停用使用者的原則，然後執行 **Invoke-CsUcsRollback** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e7551-105">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="e7551-106">只執行 **Invoke-CsUcsRollback** 僅能確保永久復原，因為若未停用原則，將會再次啟動整合連絡人存放區遷移。</span><span class="sxs-lookup"><span data-stu-id="e7551-106">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="e7551-107">例如，如果使用者因為 Exchange 2013 復原回 Exchange 2010，而且使用者的信箱移至 exchange 2013，只要在使用者服務原則中仍為使用者啟用整合連絡人存放區，就會在復原後的七天內重新開始整合的連絡人存放區遷移。</span><span class="sxs-lookup"><span data-stu-id="e7551-107">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7551-108">在下列情況下， <STRONG>Move-CsUser</STRONG> Cmdlet 會自動將使用者的連絡人存放區從 Exchange 2013 回復至 Lync Server 2013：</span><span class="sxs-lookup"><span data-stu-id="e7551-108">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e7551-109">當使用者從 Lync Server 2013 移至 Lync Server 2010 時。</span><span class="sxs-lookup"><span data-stu-id="e7551-109">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7551-110">當使用者遷移跨單位部署時，例如，當使用者從 Lync Online 移至 Lync Server 2013 內部部署時，或相反。</span><span class="sxs-lookup"><span data-stu-id="e7551-110">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7551-111">從備份資料庫匯入整合連絡人存放區資料可能會導致整合連絡人存放區資料和使用者資料在匯出與匯入間的統一連絡人存放區模式變更時損毀。</span><span class="sxs-lookup"><span data-stu-id="e7551-111">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import.</span></span> <span data-ttu-id="e7551-112">例如：</span><span class="sxs-lookup"><span data-stu-id="e7551-112">For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e7551-113">如果您在將使用者的連絡人遷移至 Exchange 2013 之前匯出連絡人清單，然後在遷移後，匯入相同的資料，整合的連絡人存放區資料和連絡人清單會損毀。</span><span class="sxs-lookup"><span data-stu-id="e7551-113">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7551-114">如果您在將使用者遷移至 Exchange 2013 之後匯出 userdata，請復原遷移，然後在遷移之後從某些原因匯入資料，整合的連絡人存放區資料和連絡人清單會損毀。</span><span class="sxs-lookup"><span data-stu-id="e7551-114">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7551-115">將 Exchange 信箱從 Exchange 2013 移至 Exchange 2010 之前，Exchange 管理員必須先確定 Lync server 系統管理員已先將 Lync Server 使用者連絡人從 Exchange 2013 復原至 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="e7551-115">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="e7551-116">若要將整合連絡人存放區連絡人回復至 Lync Server，請參閱本節稍後的程式「將整合的連絡人存放區連絡人從 Exchange 2013 復原至 Lync Server 2013」。</span><span class="sxs-lookup"><span data-stu-id="e7551-116">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="e7551-117">下列程式說明如何退回使用者連絡人。</span><span class="sxs-lookup"><span data-stu-id="e7551-117">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="e7551-118">如果您使用 **Move-CsUser** 指令移動 lync server 2013 和 lync server 2010 之間的使用者，則可以略過這些步驟，因為 **Move-CsUser** Cmdlet 會在將使用者從 Lync Server 2013 移至 lync server 2010 時，自動將 unifed 連絡人存放區回退。</span><span class="sxs-lookup"><span data-stu-id="e7551-118">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="e7551-119">**Move-CsUser** 不會停用整合連絡人存放區原則，所以如果使用者移回 Lync Server 2013，就會重複遷移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="e7551-119">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="e7551-120">從 Lync Server 2013 退回使用者連絡人至 Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e7551-120">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="e7551-121">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e7551-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7551-122">停用整合連絡人存放區，讓使用者復原，這樣就不會在復原後 remigrated。</span><span class="sxs-lookup"><span data-stu-id="e7551-122">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="e7551-123">只有在您想要確保使用者今後不會 remigrate 的情況下，才執行此步驟。 ) 若要停用個別使用者的整合連絡人存放區，請在命令列中輸入： (</span><span class="sxs-lookup"><span data-stu-id="e7551-123">(Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="e7551-124">例如：</span><span class="sxs-lookup"><span data-stu-id="e7551-124">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="e7551-125">將使用者從 Lync Server 2013 移至 Lync Server 2010 之前，請回復 Lync Server 上指定使用者的好友清單。</span><span class="sxs-lookup"><span data-stu-id="e7551-125">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7551-126">如果省略此步驟，好友清單將會遺失。</span><span class="sxs-lookup"><span data-stu-id="e7551-126">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="e7551-127">退回指定的使用者。</span><span class="sxs-lookup"><span data-stu-id="e7551-127">Roll back the specified users.</span></span> <span data-ttu-id="e7551-128">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="e7551-128">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="e7551-129">例如：</span><span class="sxs-lookup"><span data-stu-id="e7551-129">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7551-130">建議您不要使用– Force 選項強制復原。</span><span class="sxs-lookup"><span data-stu-id="e7551-130">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="e7551-131">如果您使用此選項，使用者的連絡人將會遺失。</span><span class="sxs-lookup"><span data-stu-id="e7551-131">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="e7551-132">若要將整合連絡人存放區連絡人從 Exchange 2013 復原至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7551-132">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="e7551-133">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e7551-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7551-134">停用整合連絡人存放區，讓使用者復原，這樣就不會在復原後 remigrated。</span><span class="sxs-lookup"><span data-stu-id="e7551-134">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="e7551-135">若要停用個別使用者的整合連絡人存放區，請在命令列輸入：</span><span class="sxs-lookup"><span data-stu-id="e7551-135">To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="e7551-136">例如：</span><span class="sxs-lookup"><span data-stu-id="e7551-136">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="e7551-137">退回指定的使用者。</span><span class="sxs-lookup"><span data-stu-id="e7551-137">Roll back the specified users.</span></span> <span data-ttu-id="e7551-138">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="e7551-138">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="e7551-139">例如：</span><span class="sxs-lookup"><span data-stu-id="e7551-139">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7551-140">您必須先回復 Lync Server 使用者，然後移動 Exchange 2013 信箱。</span><span class="sxs-lookup"><span data-stu-id="e7551-140">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="e7551-141">在 Lync Server 復原完成之前，Exchange 系統管理員會封鎖回退 Exchange。</span><span class="sxs-lookup"><span data-stu-id="e7551-141">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="e7551-142">建議您不要使用– Force 選項強制復原。</span><span class="sxs-lookup"><span data-stu-id="e7551-142">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="e7551-143">如果您使用此選項，使用者的連絡人將會遺失。</span><span class="sxs-lookup"><span data-stu-id="e7551-143">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="e7551-144">在您將使用者復原至 Lync Server 之後，Exchange 管理員可以將 exchange 的使用者從 Exchange 2013 復原為 Exchange 2010。</span><span class="sxs-lookup"><span data-stu-id="e7551-144">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

