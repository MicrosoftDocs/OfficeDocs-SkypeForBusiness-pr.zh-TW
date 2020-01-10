---
title: '在商務用 Skype Server 中部署整合連絡人存放區 '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 摘要：在商務用 Skype Server 中啟用整合連絡人存放區。
ms.openlocfilehash: 6cadba38f40a8ff12501e0fe73f4243dc96a5831
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003063"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="9ac88-103">在商務用 Skype Server 中部署整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="9ac88-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="9ac88-104">**摘要：** 在商務用 Skype Server 中啟用整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="9ac88-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="9ac88-105">在商務用 Skype 伺服器中啟用整合連絡人存放區，不需要任何拓撲設定。</span><span class="sxs-lookup"><span data-stu-id="9ac88-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="9ac88-106">若要為使用者啟用整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="9ac88-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="9ac88-107">已啟用整合連絡人存放區原則（預設為啟用）。</span><span class="sxs-lookup"><span data-stu-id="9ac88-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="9ac88-108">使用者至少使用商務用 Skype 登入一次。</span><span class="sxs-lookup"><span data-stu-id="9ac88-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="9ac88-109">在使用者的連絡人已完成遷移之後，當使用者使用商務用 Skype 登入時，該使用者可以從商務用 skype、Outlook 2013 或 Outlook Web Access 存取及管理其商務用 skype 連絡人。</span><span class="sxs-lookup"><span data-stu-id="9ac88-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="9ac88-110">使用者不需要登入商務用 Skype，就可以從 Outlook 或 Outlook Web Access 管理他們的連絡人。</span><span class="sxs-lookup"><span data-stu-id="9ac88-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9ac88-111">如果使用者在遷移之後從商務用 Skype 登入，就可以使用連絡人和群組，但使用者無法管理（也就是新增、刪除、移動、標記、將或修改）這些連絡人。</span><span class="sxs-lookup"><span data-stu-id="9ac88-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="9ac88-112">為使用者啟用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="9ac88-112">Enable users for unified contact store</span></span>

<span data-ttu-id="9ac88-113">當您部署商務用 Skype 伺服器併發布拓撲時，預設會為所有使用者啟用「整合連絡人存放區」。</span><span class="sxs-lookup"><span data-stu-id="9ac88-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="9ac88-114">在您部署商務用 Skype Server 之後，您不需要採取任何其他動作即可啟用整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="9ac88-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="9ac88-115">不過，您可以使用**CsUserServicesPolicy** Cmdlet 來自訂哪些使用者可以使用 [整合的連絡人] 存放區。</span><span class="sxs-lookup"><span data-stu-id="9ac88-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="9ac88-116">您可以在全球、由網站、由租使用者，或由個人或個人群組來啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="9ac88-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="9ac88-117">若要讓使用者使用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="9ac88-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="9ac88-118">啟動商務用 Skype Server 管理命令介面：請依序按一下 [**開始**]、[**所有程式**]、[**商務用 skype**]，然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="9ac88-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="9ac88-119">請執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="9ac88-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="9ac88-120">若要針對所有商務用 Skype Server 使用者全域啟用整合式連絡人存放區，請在 Windows PowerShell 命令列介面上使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9ac88-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="9ac88-121">若要針對特定網站的使用者啟用整合連絡人存放區，請在出現提示時，輸入：</span><span class="sxs-lookup"><span data-stu-id="9ac88-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="9ac88-122">例如：</span><span class="sxs-lookup"><span data-stu-id="9ac88-122">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="9ac88-123">若要啟用租使用者的整合連絡人存放區，請在提示時輸入：</span><span class="sxs-lookup"><span data-stu-id="9ac88-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="9ac88-124">例如：</span><span class="sxs-lookup"><span data-stu-id="9ac88-124">For example:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="9ac88-125">若要針對特定使用者啟用整合連絡人存放區，請在提示時輸入：</span><span class="sxs-lookup"><span data-stu-id="9ac88-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="9ac88-126">您也可以使用使用者別名或 SIP URI，而不是使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="9ac88-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="9ac88-127">例如：</span><span class="sxs-lookup"><span data-stu-id="9ac88-127">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="9ac88-128">在前面的範例中，第一個命令會建立名為 [UCS] 的新使用者原則，並將 UcsAllowed 標誌設定為 True。</span><span class="sxs-lookup"><span data-stu-id="9ac88-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="9ac88-129">第二個命令會將原則指派給使用者，並使用顯示名稱 Ken Myer，這表示現在已為整合連絡人存放區啟用 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="9ac88-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="9ac88-130">將使用者移轉到整合的連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="9ac88-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="9ac88-131">當使用者在下列情況下，使用者的連絡人會自動轉移至 Exchange 2013 伺服器：</span><span class="sxs-lookup"><span data-stu-id="9ac88-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="9ac88-132">已指派 UcsAllowed 設定為 True 的使用者服務原則。</span><span class="sxs-lookup"><span data-stu-id="9ac88-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="9ac88-133">已使用 Exchange 2013 信箱進行預配，且至少已在信箱中登入一次。</span><span class="sxs-lookup"><span data-stu-id="9ac88-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="9ac88-134">使用商務用 Skype 胖用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="9ac88-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="9ac88-135">如果使用者使用 Lync 或較舊的用戶端登入，或者如果使用者未連線至 Exchange 2013 伺服器，則系統會忽略使用者服務原則，且使用者的連絡人會保留在商務用 Skype 伺服器中。</span><span class="sxs-lookup"><span data-stu-id="9ac88-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="9ac88-136">您可以使用下列其中一種方法來判斷使用者的連絡人是否已被遷移：</span><span class="sxs-lookup"><span data-stu-id="9ac88-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="9ac88-137">檢查用戶端電腦上的下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="9ac88-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="9ac88-138">HKEY_CURRENT_USER \Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span><span class="sxs-lookup"><span data-stu-id="9ac88-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="9ac88-139">如果使用者的連絡人儲存在 Exchange 2013 中，此索引鍵會包含值為2165的 InUCSMode 值。</span><span class="sxs-lookup"><span data-stu-id="9ac88-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="9ac88-140">執行**Test CsUnifiedContactStore** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9ac88-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="9ac88-141">在商務用 Skype Server Management Shell 命令列上，鍵入：</span><span class="sxs-lookup"><span data-stu-id="9ac88-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="9ac88-142">如果**CsUnifiedContactStore**成功，則使用者的連絡人已遷移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="9ac88-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="9ac88-143">回滾已遷移的使用者</span><span class="sxs-lookup"><span data-stu-id="9ac88-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="9ac88-144">如果您需要回滾 [整合連絡人存放區] 功能，請只有在您將使用者移回 Exchange 2010 或 Lync Server 2010 時，才能回滾連絡人。</span><span class="sxs-lookup"><span data-stu-id="9ac88-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="9ac88-145">若要回滾，請停用使用者的原則，然後執行**CsUcsRollback** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9ac88-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="9ac88-146">僅僅執行**Invoke CsUcsRollback**是無法確保永久復原，因為如果原則沒有停用，就會再次啟動整合式連絡人存放區遷移。</span><span class="sxs-lookup"><span data-stu-id="9ac88-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="9ac88-147">例如，如果使用者因為 Exchange 2013 已回滾至 Exchange 2010，且使用者的信箱移至 Exchange 2013，則在回滾之後的7天內就會再次開始進行整合連絡人商店遷移（只要整合連絡人存放區）在使用者服務原則中，仍已啟用使用者的。</span><span class="sxs-lookup"><span data-stu-id="9ac88-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="9ac88-148">在下列情況下， **move-csuser** Cmdlet 會將使用者的連絡人存放區從 Exchange 2013 自動回滾到商務用 Skype Server：</span><span class="sxs-lookup"><span data-stu-id="9ac88-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="9ac88-149">當使用者從商務用 Skype Server 移至 Microsoft Lync Server 2013 或 Lync Server 2010 時。</span><span class="sxs-lookup"><span data-stu-id="9ac88-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="9ac88-150">使用者被遷移時（例如，當使用者從商務用 Skype Online 移至內部部署的商務用 Skype Server），或相反的情況下。</span><span class="sxs-lookup"><span data-stu-id="9ac88-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="9ac88-151">從備份資料庫匯入整合連絡人存放區資料時，如果在匯出與匯入之間變更了整合連絡人存放區模式，就會導致整合連絡人存放區資料和使用者資料遭到損毀。</span><span class="sxs-lookup"><span data-stu-id="9ac88-151">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import.</span></span> <span data-ttu-id="9ac88-152">例如：</span><span class="sxs-lookup"><span data-stu-id="9ac88-152">For example:</span></span>
  
- <span data-ttu-id="9ac88-153">如果您先匯出連絡人清單，然後再將使用者的連絡人遷移至 Exchange 2013，然後在遷移之後，將相同的資料匯入，整合的連絡人商店資料和連絡人清單都會損毀。</span><span class="sxs-lookup"><span data-stu-id="9ac88-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="9ac88-154">如果您在將使用者遷移至 Exchange 2013 之後匯出使用者資料，請回滾遷移，然後，如果您在遷移之後從某種原因匯入資料，整合的連絡人商店資料和連絡人清單都會損毀。</span><span class="sxs-lookup"><span data-stu-id="9ac88-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="9ac88-155">在將 Exchange 信箱從 Exchange 2013 移至 Exchange 2010 之前，Exchange 管理員必須先將商務用 skype Server 系統管理員的 [商務2013用 skype 伺服器] 使用者連絡人回滾至 Skype for商務伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ac88-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="9ac88-156">若要將「整合連絡人存放區」連絡人回滾至商務用 Skype Server，請參閱本節稍後的程式「將整合的連絡人存放庫連絡人從 Exchange 2013 回滾到商務用 Skype Server」。</span><span class="sxs-lookup"><span data-stu-id="9ac88-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="9ac88-157">**如何退回使用者連絡人：** 如果您使用**move-csuser** Cmdlet 在商務用 skype server 2015 和 Lync server 2010 之間移動使用者，您可以略過這些步驟，因為**移動 move-csuser** Cmdlet 會在將使用者從商務用 Skype Server 2015 移至 Lync Server 2010 時，自動回滾整合的連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="9ac88-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="9ac88-158">**Move-csuser**不會停用整合式連絡人存放區原則，因此，如果使用者移回商務用 Skype Server 2015，就會重複遷移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="9ac88-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

