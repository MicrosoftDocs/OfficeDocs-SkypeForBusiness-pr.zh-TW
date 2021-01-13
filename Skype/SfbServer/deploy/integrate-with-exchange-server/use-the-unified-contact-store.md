---
title: 設定商務用 Skype 伺服器以使用整合連絡人存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 摘要：設定 Exchange Server 和商務用 Skype 伺服器的整合連絡人存放區。
ms.openlocfilehash: 4b96a0c4f3294146c987794ffce083c46d94bb48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833863"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a><span data-ttu-id="74f08-103">設定商務用 Skype 伺服器以使用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="74f08-103">Configure Skype for Business Server to use the unified contact store</span></span>
 
<span data-ttu-id="74f08-104">**摘要：** 設定 Exchange Server 2016 或 Exchange Server 2013 和商務用 Skype Server 的整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="74f08-104">**Summary:** Configure the unified contacts store for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="74f08-105">使用整合連絡人存放區時，使用者會維護單一連絡人清單，然後讓多個應用程式（包括商務用 Skype、Microsoft Outlook 2013 和 Microsoft Outlook Web App 2013）都能使用這些連絡人。</span><span class="sxs-lookup"><span data-stu-id="74f08-105">Using the unified contact store, users maintain a single contacts list and then have those contacts available in multiple applications, including Skype for Business, Microsoft Outlook 2013, and Microsoft Outlook Web App 2013.</span></span> <span data-ttu-id="74f08-106">當您為使用者啟用整合連絡人存放區時，該使用者的連絡人不會儲存在商務用 Skype 伺服器中，也可以視需要而取回。</span><span class="sxs-lookup"><span data-stu-id="74f08-106">When you enable the unified contact store for a user, that user's contacts are not stored in Skype for Business Server and retrieved as needed.</span></span> <span data-ttu-id="74f08-107">相反地，他或她的連絡人會儲存在 Exchange Server 2016 或 Exchange Server 2013 中，並使用 Exchange Web 服務進行檢索。</span><span class="sxs-lookup"><span data-stu-id="74f08-107">Instead, his or her contacts are stored in Exchange Server 2016 or Exchange Server 2013 and are retrieved by using Exchange Web Services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74f08-108">從技術角度來看，連絡人資訊會儲存在使用者的 Exchange 信箱中找到的資料夾組中。</span><span class="sxs-lookup"><span data-stu-id="74f08-108">Technically, contact information is stored in a pair of folders found in the user's Exchange mailbox.</span></span> <span data-ttu-id="74f08-109">連絡人本身會儲存在名為商務用 Skype 連絡人的資料夾中，供使用者看到;連絡人的中繼資料儲存在使用者無法看見的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="74f08-109">The contacts themselves are stored in a folder named Skype for Business Contacts which is visible to end users; metadata about the contacts are stored in a subfolder that is not visible to end users.</span></span> 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a><span data-ttu-id="74f08-110">針對使用者啟用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="74f08-110">Enabling the Unified Contact Store for a User</span></span>

<span data-ttu-id="74f08-111">如果已設定商務用 Skype Server 與 Exchange Server 之間的伺服器對伺服器驗證，則表示您也已啟用整合連絡人存放區;不需要其他伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="74f08-111">If server-to-server authentication between Skype for Business Server and Exchange Server is already configured, then you have also enabled the unified contact store; no additional server configuration is required.</span></span> <span data-ttu-id="74f08-112">不過，要將使用者的連絡人移動至整合連絡人存放區，則需設定其他使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="74f08-112">However, additional user account configuration is required in order to move a user's contacts into the unified contact store.</span></span> <span data-ttu-id="74f08-113">根據預設，使用者連絡人會保留在商務用 Skype Server 中，而非整合連絡人存放區中。</span><span class="sxs-lookup"><span data-stu-id="74f08-113">By default, user contacts are kept in Skype for Business Server and not in the unified contact store.</span></span>
  
<span data-ttu-id="74f08-114">使用商務用 Skype Server 使用者服務原則來管理對整合連絡人存放區的存取。</span><span class="sxs-lookup"><span data-stu-id="74f08-114">Access to the unified contact store is managed by using Skype for Business Server user services policies.</span></span> <span data-ttu-id="74f08-115">使用者伺服器原則僅有單一屬性 (UcsAllowed)；此屬性用於決定使用者的連絡人所儲存的位置。</span><span class="sxs-lookup"><span data-stu-id="74f08-115">User server policies have only a single property (UcsAllowed); this property is used to determine the location where a user's contacts are stored.</span></span> <span data-ttu-id="74f08-116">如果使用者是由使用者服務原則所管理，且 UcsAllowed 已設定為 True ($True) 則使用者的連絡人會儲存在統一連絡人存放區中。</span><span class="sxs-lookup"><span data-stu-id="74f08-116">If a user is managed by a user services policy where UcsAllowed has been set to True ($True) then the user's contacts will be stored in the unified contact store.</span></span> <span data-ttu-id="74f08-117">如果使用者是由使用者服務原則所管理，且 UcsAllowed 已設定為 False ($False) 則該使用者的連絡人會儲存在商務用 Skype Server 中。</span><span class="sxs-lookup"><span data-stu-id="74f08-117">If the user is managed by a user services policy where UcsAllowed has been set to False ($False) then his or her contacts will be stored in Skype for Business Server.</span></span>
  
<span data-ttu-id="74f08-118">當您安裝商務用 Skype Server 時，會同時安裝單一使用者服務原則 (在全域範圍) 設定。</span><span class="sxs-lookup"><span data-stu-id="74f08-118">When you install Skype for Business Server, a single user services policy (configured at the global scope) is installed as well.</span></span> <span data-ttu-id="74f08-119">這個原則中的 UcsAllowed 值設定為 True，這表示，預設會將使用者連絡人儲存在「整合連絡人存放區」中， (假設已部署並設定) 。</span><span class="sxs-lookup"><span data-stu-id="74f08-119">The UcsAllowed value in this policy is set to True, meaning that, by default, user contacts will be stored in the unified contact store (assuming this has been deployed and configured).</span></span> <span data-ttu-id="74f08-120">如果您想要將所有使用者連絡人遷移至整合連絡人存放區，您不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="74f08-120">If you want to migrate all of your user contacts to the unified contact store you do not have to do anything at all.</span></span> 
  
<span data-ttu-id="74f08-121">如果您不想將所有連絡人遷移至整合連絡人存放區，您可以將全域原則中的 UcsAllowed 屬性設定為 False，以停用所有使用者的整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="74f08-121">If you would prefer not to migrate all your contacts to the unified contact store you can disable the unified contact store for all users by setting the UcsAllowed property in the global policy to False:</span></span>
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

<span data-ttu-id="74f08-122">停用全域原則中的整合連絡人存放區後，您就可以建立個別使用者原則，以啟用整合連絡人存放區的使用;這可讓您讓某些使用者將其連絡人保留在整合連絡人存放區中，而其他使用者仍可繼續在商務用 Skype Server 中保留其連絡人。</span><span class="sxs-lookup"><span data-stu-id="74f08-122">After you have disabled the unified contact store in the global policy you can then create a per-user policy that enables the use of the unified contact store; this allows you to have some users keep their contacts in the unified contact store while other users continue to keep their contacts in Skype for Business Server.</span></span> <span data-ttu-id="74f08-123">您可以使用類似以下的命令來建立個別使用者的使用者服務原則：</span><span class="sxs-lookup"><span data-stu-id="74f08-123">You can create a per-user user services policy by using a command similar to this:</span></span>
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

<span data-ttu-id="74f08-p107">在您建立新原則之後，接著您必須將該原則指派給應擁有整合連絡人存放區存取權的任何使用者。您可使用類似以下的命令，將個別使用者原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="74f08-p107">After you have created the new policy you must then assign that policy to any user who should have access to the unified contact store. Per-user policies can be assigned to users by using commands similar to this:</span></span>
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

<span data-ttu-id="74f08-126">指派原則之後，商務用 Skype 伺服器就會開始將使用者的連絡人遷移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="74f08-126">After the policy has been assigned, Skype for Business Server will begin to migrate the user's contacts to the unified contact store.</span></span> <span data-ttu-id="74f08-127">遷移完成後，使用者將會在 Exchange 中儲存其連絡人，而不是商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="74f08-127">After migration is complete, the user will then have his or her contacts stored in Exchange rather than Skype for Business Server.</span></span> <span data-ttu-id="74f08-128">若使用者在遷移完成時登入 Lync 2013，將會出現一個訊息方塊，而要求他或她會登入商務用 Skype，然後重新登入，以完成此程式。</span><span class="sxs-lookup"><span data-stu-id="74f08-128">If the user happens to be logged on to Lync 2013 at the time migration completes, a message box will appear and he or she will be asked to log off of Skype for Business and then log back on in order to finalize the process.</span></span> <span data-ttu-id="74f08-129">尚未被指派此個別使用者原則的使用者，將不會將其連絡人遷移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="74f08-129">Users who have not been assigned this per-user policy will not have their contacts migrated to the unified contact store.</span></span> <span data-ttu-id="74f08-130">這是因為這些使用者是由全域原則所管理，且已在全域原則中停用統一連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="74f08-130">That's because those users are being managed by the global policy, and use of the unified contact store has been disabled in the global policy.</span></span>
  
<span data-ttu-id="74f08-131">您可以從商務用 Skype Server 管理命令介面中執行 [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) Cmdlet，以確認使用者的連絡人是否已順利遷移至整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="74f08-131">You can verify that a user's contacts have successfully been migrated to the unified contact store by running the [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) cmdlet from within the Skype for Business Server Management Shell:</span></span>
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="74f08-132">如果 Test-CsUnifiedContactStore 會成功，表示使用者 sip 的連絡人： kenmyer@ litwareinc 已 <span></span> <span></span> 遷移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="74f08-132">If Test-CsUnifiedContactStore succeeds that means that the contacts for the user sip:kenmyer@<span></span>litwareinc<span></span>.com have been migrated to the unified contact store.</span></span>
  
## <a name="rolling-back-the-unified-contact-store"></a><span data-ttu-id="74f08-133">復原連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="74f08-133">Rolling Back the Unified Contact Store</span></span>

<span data-ttu-id="74f08-134">如果您需要從統一連絡人存放區中移除使用者的連絡人 (例如，如果使用者需要在 Microsoft Lync Server 2010 上 rehomed，而且無法再使用整合連絡人存放區) 必須執行兩項操作。</span><span class="sxs-lookup"><span data-stu-id="74f08-134">If you need to remove a user's contacts from the unified contact store (for example, if the user needs to be rehomed on Microsoft Lync Server 2010 and thus can no longer use the unified contact store) you must do two things.</span></span> <span data-ttu-id="74f08-135">首先，您必須將新的使用者服務原則指派給使用者，而不是使用統一連絡人存放區中儲存連絡人的原則。</span><span class="sxs-lookup"><span data-stu-id="74f08-135">First, you must assign the user a new user services policy, one that prohibits storing contacts in the unified contact store.</span></span> <span data-ttu-id="74f08-136"> (也就是 UcsAllowed 屬性已設定為 $False 的原則。 ) 如果您不具備這類原則，您可以使用類似下列的命令建立一個原則：</span><span class="sxs-lookup"><span data-stu-id="74f08-136">(That is, a policy where the UcsAllowed property has been set to $False.) If you do not have such a policy you can create one using a command similar to this:</span></span>
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

<span data-ttu-id="74f08-137">然後您可使用如下命令來指派這個新的個別使用者原則 (NoUnifiedContactStore)：</span><span class="sxs-lookup"><span data-stu-id="74f08-137">You can then assign this new per-user policy (NoUnifiedContactStore) by using a command like this:</span></span>
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

<span data-ttu-id="74f08-138">上述命令會將新原則指派給使用者 Ken Myer，同時也會防止 Ken 的連絡人移轉至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="74f08-138">The preceding command assigns the new policy to the user Ken Myer, and also prevents Ken's contacts from being migrated to the unified contact store.</span></span>
  
> [!NOTE]
> <span data-ttu-id="74f08-139">在某些情況下，您只要取消指派使用者目前的使用者服務原則，就能達到相同的網路效果。</span><span class="sxs-lookup"><span data-stu-id="74f08-139">In some cases you can achieve the same net effect by simply un-assigning the user's current user services policy.</span></span> <span data-ttu-id="74f08-140">例如，假設 Ken Myer 擁有個別使用者的使用者服務原則，該原則可啟用整合連絡人存放區，但是您的全域原則禁止整合連絡人存放區的使用。</span><span class="sxs-lookup"><span data-stu-id="74f08-140">For example, suppose Ken Myer has a per-user user services policy the enables the unified contact store, but your global policy prohibits the use of the unified contact store.</span></span> <span data-ttu-id="74f08-141">在此情況下，您可以取消指派 Ken 的每個使用者服務原則。</span><span class="sxs-lookup"><span data-stu-id="74f08-141">In that case, you could un-assign Ken's per-user services policy.</span></span> <span data-ttu-id="74f08-142">當您那樣做時，Ken 會自動受全域原則管理，因此不再有整合連絡人存放區的存取權。</span><span class="sxs-lookup"><span data-stu-id="74f08-142">When you do that, Ken will automatically be managed by the global policy, and thus will no longer have access to the unified contact store.</span></span> <span data-ttu-id="74f08-143">若要取消指派先前指派的個別使用者原則，請使用之前所顯示的相同命令，但這次將 PolicyName 參數設定為 null 值： Grant-CsUserServicesPolicy-Identity "Ken Myer"-PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="74f08-143">To un-assign a previously-assigned per-user policy, use the same command as shown before, but this time set the PolicyName parameter to a null value: Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName $Null</span></span> 
  
<span data-ttu-id="74f08-144">在處理整合連絡人存放區時，須牢記「防止 Ken 的連絡人移轉至整合連絡人存放區」這個術語。</span><span class="sxs-lookup"><span data-stu-id="74f08-144">The terminology "prevents Ken's contacts from being migrated to the unified contact store" is important to keep in mind when working with the unified contact store.</span></span> <span data-ttu-id="74f08-145">單單將新的使用者服務原則指派給 Ken 並不會將其連絡人從整合連絡人存放區移出。</span><span class="sxs-lookup"><span data-stu-id="74f08-145">Simply assigning Ken a new user services policy will not move his contacts out of the unified contact store.</span></span> <span data-ttu-id="74f08-146">當使用者登入商務用 Skype 伺服器時，系統會檢查使用者的使用者服務原則，以查看其連絡人是否應該保留在統一連絡人存放區中。</span><span class="sxs-lookup"><span data-stu-id="74f08-146">When a user logs on to Skype for Business Server, the system checks the user's user services policy to see whether his or her contacts should be kept in the unified contact store.</span></span> <span data-ttu-id="74f08-147">如果結果為肯定 (也就是說，如果 UcsAllowed 屬性設為 $True)，那些連絡人就會移轉至整合連絡人存放區 (假設那些連絡人尚未存放在整合連絡人存放區)。</span><span class="sxs-lookup"><span data-stu-id="74f08-147">If the answer is yes (that is, if the UcsAllowed property is set to $True) then those contacts will be migrated to the unified contact store (assuming that those contacts are not already in the unified contact store).</span></span> <span data-ttu-id="74f08-148">如果答案是 [否]，則商務用 Skype 伺服器只會略過使用者的連絡人，然後移至下一個工作。</span><span class="sxs-lookup"><span data-stu-id="74f08-148">If the answer is no, then Skype for Business Server simply ignores the user's contacts and moves on to its next task.</span></span> <span data-ttu-id="74f08-149">這表示商務用 Skype 伺服器不會自動將使用者的連絡人從統一連絡人存放區移出，不論 UcsAllowed 屬性的值為何。</span><span class="sxs-lookup"><span data-stu-id="74f08-149">That means that Skype for Business Server will not automatically move a user's contacts from out of the unified contact store, regardless of the value of the UcsAllowed property.</span></span>
  
<span data-ttu-id="74f08-150">這也表示，在指派使用者新的使用者服務原則之後，您必須執行 [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) 指令程式，以便將使用者的連絡人移出 Exchange Server 並回到商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="74f08-150">That also means that, after assigning the user a new user services policy, you must then run the [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) cmdlet in order to move the user's contacts out of Exchange Server and back to Skype for Business Server.</span></span> <span data-ttu-id="74f08-151">例如，在將新的使用者服務原則指派給 Ken Myer 之後，您就可以使用下列命令將其連絡人移出整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="74f08-151">For example, after assigning Ken Myer a new user services policy you can then move his contacts out of the unified contact store by using the following command:</span></span>
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

<span data-ttu-id="74f08-152">果您變更使用者服務原則，但是未執行 Invoke-CsUcsRollback Cmdlet，Ken 的連絡人就不會從整合連絡人存放區移除。</span><span class="sxs-lookup"><span data-stu-id="74f08-152">If you change the user services policy but do not run the Invoke-CsUcsRollback cmdlet Ken's contacts will not be removed from the unified contact store.</span></span> <span data-ttu-id="74f08-153">如果您執行 Invoke-CsUcsRollback，但未變更 Ken Myer 的使用者服務原則，會有什麼結果呢？</span><span class="sxs-lookup"><span data-stu-id="74f08-153">What if you run Invoke-CsUcsRollback but do not change Ken Myer's user services policy?</span></span> <span data-ttu-id="74f08-154">在這種情況下，Ken 的連絡人會暫時從整合連絡人存放區中遭移除。</span><span class="sxs-lookup"><span data-stu-id="74f08-154">In that case, Ken's contacts will be temporarily removed from the unified contact store.</span></span> <span data-ttu-id="74f08-155">您務必牢記此移除作業為暫時性的。</span><span class="sxs-lookup"><span data-stu-id="74f08-155">The fact that this removal is temporary is important to keep in mind.</span></span> <span data-ttu-id="74f08-156">當 Ken 的連絡人從整合連絡人存放區中移除之後，商務用 Skype 伺服器會等候7天，然後查看已指派給 Ken 的使用者服務原則。</span><span class="sxs-lookup"><span data-stu-id="74f08-156">After Ken's contacts have been removed from the unified contact store, Skype for Business Server will wait 7 days and then check to see which user services policy has been assigned to Ken.</span></span> <span data-ttu-id="74f08-157">如果指派給 Ken 的原則仍然可啟用整合來連絡人存放區，其連絡人就會自動移回連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="74f08-157">If Ken is still assigned a policy that enables the user of the unified contact store, then his contacts will automatically be moved back to into the contact store.</span></span> <span data-ttu-id="74f08-158">若要將連絡人從整合連絡人存放區永久移除，除了執行 Invoke-CsUcsRollback Cmdlet 之外，您還必須變更使用者服務原。</span><span class="sxs-lookup"><span data-stu-id="74f08-158">To permanently remove contacts from the unified contact store you must change the user services policy in addition to running the Invoke-CsUcsRollback cmdlet.</span></span>
  
<span data-ttu-id="74f08-159">由於大量可影響遷移的變數，因此很難估計帳戶完全遷移至整合連絡人存放區之前所需的時間。</span><span class="sxs-lookup"><span data-stu-id="74f08-159">Due to the large number of variables that can affect migration, it is difficult to estimate how long it will take before accounts are fully migrated to the unified contact store.</span></span> <span data-ttu-id="74f08-160">不過，作為一般規則，遷移不會立即生效：即使遷移少量的連絡人，移動作業完成後，可能需要10分鐘或更多時間。</span><span class="sxs-lookup"><span data-stu-id="74f08-160">As a general rule, however, migration does not take effect immediately: even when migrating a small number of contacts it might take 10 minutes or more before the move is complete.</span></span>
  

