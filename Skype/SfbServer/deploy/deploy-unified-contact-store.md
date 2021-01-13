---
title: '在商務用 Skype Server 中部署整合連絡人存放區 '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 摘要：在商務用 Skype Server 中啟用整合連絡人存放區。
ms.openlocfilehash: 7bf4dcb884dc9fecee15209f5acb563fce9efd43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812553"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="d900d-103">在商務用 Skype Server 中部署整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="d900d-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="d900d-104">**摘要：** 在商務用 Skype Server 中啟用整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="d900d-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="d900d-105">在商務用 Skype Server 中啟用整合連絡人存放區，不需要任何拓撲設定。</span><span class="sxs-lookup"><span data-stu-id="d900d-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="d900d-106">若要為使用者啟用整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="d900d-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="d900d-107">啟用整合連絡人存放區原則 (預設為啟用)。</span><span class="sxs-lookup"><span data-stu-id="d900d-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="d900d-108">使用者以商務用 Skype 登入至少一次。</span><span class="sxs-lookup"><span data-stu-id="d900d-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="d900d-109">在使用者的連絡人已遷移之後，當使用者使用商務用 Skype 登入時，使用者就可以從商務用 skype、Outlook 2013 或 Outlook Web Access 存取及管理商務用 skype 連絡人。</span><span class="sxs-lookup"><span data-stu-id="d900d-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="d900d-110">使用者不必登入商務用 Skype 以從 Outlook 或 Outlook Web Access 管理其連絡人。</span><span class="sxs-lookup"><span data-stu-id="d900d-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d900d-111">如果使用者在遷移之後從商務用 Skype 登入，則連絡人和群組可供使用且是最新的，但是使用者無法管理 (，例如新增、刪除、移動、標記、untag 或修改) 那些連絡人。</span><span class="sxs-lookup"><span data-stu-id="d900d-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="d900d-112">為使用者啟用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="d900d-112">Enable users for unified contact store</span></span>

<span data-ttu-id="d900d-113">當您部署商務用 Skype Server 和發行拓撲時，預設會為所有使用者啟用整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="d900d-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="d900d-114">在您部署商務用 Skype Server 之後，您不需要執行任何其他動作即可啟用整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="d900d-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="d900d-115">不過，您可以使用 **Set-CsUserServicesPolicy** Cmdlet 自訂哪些連絡人有整合連絡人存放區可用。</span><span class="sxs-lookup"><span data-stu-id="d900d-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="d900d-116">您可以全域、依網站、依承租人或依個人或個人群組啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="d900d-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="d900d-117">啟用整合連絡人存放區的使用者</span><span class="sxs-lookup"><span data-stu-id="d900d-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="d900d-118">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="d900d-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d900d-119">執行下列任一項作業：</span><span class="sxs-lookup"><span data-stu-id="d900d-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="d900d-120">若要為所有商務用 Skype Server 使用者全域性啟用整合連絡人存放區，請在 Windows PowerShell 命令列介面上進行下列指令程式：</span><span class="sxs-lookup"><span data-stu-id="d900d-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="d900d-121">若要為特定網站上的使用者啟用整合連絡人存放區，請在提示中輸入：</span><span class="sxs-lookup"><span data-stu-id="d900d-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="d900d-122">例如：</span><span class="sxs-lookup"><span data-stu-id="d900d-122">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="d900d-123">若要依租使用者啟用整合連絡人存放區，請在提示中輸入：</span><span class="sxs-lookup"><span data-stu-id="d900d-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="d900d-124">例如：</span><span class="sxs-lookup"><span data-stu-id="d900d-124">For example:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="d900d-125">若要為特定使用者啟用整合連絡人存放區，請在提示中輸入：</span><span class="sxs-lookup"><span data-stu-id="d900d-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="d900d-126">您也可以使用使用者別名或 SIP URI，而不使用使用者顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="d900d-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="d900d-127">例如：</span><span class="sxs-lookup"><span data-stu-id="d900d-127">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="d900d-128">在上一個範例中，第一個命令建立名稱為「UCS 已啟用使用者」 的新個別使用者原則，而且將 UcsAllowed 旗標設定為 True。</span><span class="sxs-lookup"><span data-stu-id="d900d-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="d900d-129">第二個指令將該原則指派給顯示名稱為 Ken Myer 的使用者，這表示目前已針對 Ken Myer 啟用整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="d900d-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="d900d-130">將使用者遷移至整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="d900d-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="d900d-131">當使用者執行下列動作時，使用者的連絡人會自動遷移至 Exchange 2013 伺服器：</span><span class="sxs-lookup"><span data-stu-id="d900d-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="d900d-132">已指派了 UcsAllowed 設為 True 的使用者服務原則。</span><span class="sxs-lookup"><span data-stu-id="d900d-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="d900d-133">已布建與 Exchange 2013 信箱，且至少已登入至信箱一次。</span><span class="sxs-lookup"><span data-stu-id="d900d-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="d900d-134">使用商務用 Skype 豐富型用戶端登入。</span><span class="sxs-lookup"><span data-stu-id="d900d-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="d900d-135">如果使用者登入 Lync 或舊版用戶端，或使用者未連線至 Exchange 2013 伺服器，則會忽略使用者服務原則，而且使用者的連絡人仍會保留在商務用 Skype Server 中。</span><span class="sxs-lookup"><span data-stu-id="d900d-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="d900d-136">您可使用下列方法之一，來判斷使用者的連絡人是否已移轉：</span><span class="sxs-lookup"><span data-stu-id="d900d-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="d900d-137">檢查用戶端電腦上的下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="d900d-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="d900d-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL \> \UCS</span><span class="sxs-lookup"><span data-stu-id="d900d-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="d900d-139">如果使用者的連絡人儲存在 Exchange 2013 中，則此機碼會包含值為2165的 InUCSMode。</span><span class="sxs-lookup"><span data-stu-id="d900d-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="d900d-140">執行 **Test-CsUnifiedContactStore** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d900d-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="d900d-141">在商務用 Skype Server 管理命令介面命令列上輸入：</span><span class="sxs-lookup"><span data-stu-id="d900d-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="d900d-142">若 **Test-CsUnifiedContactStore** 成功，使用者的連絡人就已移轉至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="d900d-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="d900d-143">回退遷移的使用者</span><span class="sxs-lookup"><span data-stu-id="d900d-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="d900d-144">如果您需要回復「整合連絡人存放區」功能，請僅在將使用者移回 Exchange 2010 或 Lync Server 2010 時，才復原連絡人。</span><span class="sxs-lookup"><span data-stu-id="d900d-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="d900d-145">若要回退，請停用使用者的原則，然後執行 **Invoke-CsUcsRollback** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d900d-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="d900d-146">只執行 **Invoke-CsUcsRollback** 僅能確保永久復原，因為若未停用原則，將會再次啟動整合連絡人存放區遷移。</span><span class="sxs-lookup"><span data-stu-id="d900d-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="d900d-147">例如，如果使用者因為 Exchange 2013 復原回 Exchange 2010，而且使用者的信箱移至 exchange 2013，只要在使用者服務原則中仍為使用者啟用整合連絡人存放區，就會在復原後的七天內重新開始整合的連絡人存放區遷移。</span><span class="sxs-lookup"><span data-stu-id="d900d-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="d900d-148">在下列情況下， **Move-CsUser** Cmdlet 會自動將使用者的連絡人存放區從 Exchange 2013 退回商務用 Skype Server：</span><span class="sxs-lookup"><span data-stu-id="d900d-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="d900d-149">當使用者從商務用 Skype Server 移至 Microsoft Lync Server 2013 或 Lync Server 2010 時。</span><span class="sxs-lookup"><span data-stu-id="d900d-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="d900d-150">當使用者遷移跨單位部署時，例如，當使用者從商務用 Skype Online 移至內部部署的商務用 Skype Server 時，或相反。</span><span class="sxs-lookup"><span data-stu-id="d900d-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="d900d-151">從備份資料庫匯入整合連絡人存放區資料可能會導致整合連絡人存放區資料和使用者資料在匯出與匯入間的統一連絡人存放區模式變更時損毀。</span><span class="sxs-lookup"><span data-stu-id="d900d-151">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import.</span></span> <span data-ttu-id="d900d-152">例如：</span><span class="sxs-lookup"><span data-stu-id="d900d-152">For example:</span></span>
  
- <span data-ttu-id="d900d-153">如果您在將使用者的連絡人遷移至 Exchange 2013 之前匯出連絡人清單，然後在遷移後，匯入相同的資料，整合的連絡人存放區資料和連絡人清單會損毀。</span><span class="sxs-lookup"><span data-stu-id="d900d-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="d900d-154">如果您在將使用者遷移至 Exchange 2013 之後匯出使用者資料，請復原遷移，然後在遷移之後從某些原因匯入資料，整合的連絡人存放區資料和連絡人清單會損毀。</span><span class="sxs-lookup"><span data-stu-id="d900d-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d900d-155">將 Exchange 信箱從 Exchange 2013 移至 Exchange 2010 之前，Exchange 系統管理員必須確定商務用 skype 伺服器管理員已第一次將商務用 Skype Server 使用者連絡人從 Exchange 2013 移回商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="d900d-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="d900d-156">若要將整合連絡人存放區連絡人回復至商務用 Skype Server，請參閱本節稍後的程式「將 Exchange 2013 的整合連絡人存放區連絡人復原到商務用 Skype Server」。</span><span class="sxs-lookup"><span data-stu-id="d900d-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="d900d-157">**如何退回使用者連絡人：** 如果您使用 **Move-CsUser** 指令程式在商務用 skype server 2015 和 Lync server 2010 之間移動使用者，則可以略過這些步驟，因為 **Move-CsUser** 指令程式會在將使用者從商務用 Skype Server 2015 移至 Lync server 2010 時，自動回復已整合的連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="d900d-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="d900d-158">**Move-CsUser** 不會停用整合連絡人存放區原則，所以如果使用者移回商務用 Skype Server 2015，便會重複遷移至整合的連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="d900d-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

