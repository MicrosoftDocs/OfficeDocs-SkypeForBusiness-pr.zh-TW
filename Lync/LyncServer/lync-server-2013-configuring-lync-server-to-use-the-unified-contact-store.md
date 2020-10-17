---
title: Lync Server 2013：設定 Lync Server 使用整合連絡人存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1f913b321d700337d1cb3649c2e1351971b6d7a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506250"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a><span data-ttu-id="09c31-102">設定 Microsoft Lync Server 2013 以使用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="09c31-102">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09c31-103">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="09c31-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="09c31-104">整合連絡人存放區可讓使用者維護單一連絡人清單，然後讓多個應用程式（包括 Microsoft Lync 2013、Microsoft Outlook 2013 及 Microsoft Outlook Web App 2013）都能使用這些連絡人。</span><span class="sxs-lookup"><span data-stu-id="09c31-104">The unified contact store enables users to maintain a single contacts list and then have those contacts available in multiple applications, including Microsoft Lync 2013, Microsoft Outlook 2013, and Microsoft Outlook Web App 2013.</span></span> <span data-ttu-id="09c31-105">當您為使用者啟用整合連絡人存放區時，使用者的連絡人不會儲存在 Microsoft Lync Server 2013，然後使用 SIP 通訊協定進行檢索。</span><span class="sxs-lookup"><span data-stu-id="09c31-105">When you enable the unified contact store for a user that user's contacts are not stored in Microsoft Lync Server 2013 and then retrieved using the SIP protocol.</span></span> <span data-ttu-id="09c31-106">相反地，他或她的連絡人會儲存在 Microsoft Exchange Server 2013 中，而且會透過 Exchange Web 服務進行檢索。</span><span class="sxs-lookup"><span data-stu-id="09c31-106">Instead, his or her contacts are stored in Microsoft Exchange Server 2013 and are retrieved by using Exchange Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09c31-107">從技術角度來看，連絡人資訊會儲存在使用者的 Exchange 2013 信箱中的一對資料夾中。</span><span class="sxs-lookup"><span data-stu-id="09c31-107">Technically, contact information is stored in a pair of folders found in the user's Exchange 2013 mailbox.</span></span> <span data-ttu-id="09c31-108">連絡人本身會儲存在名為 Lync 連絡人的資料夾中，使用者對使用者來說是可見的;連絡人的中繼資料儲存在使用者無法看見的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="09c31-108">The contacts themselves are stored in a folder named Lync Contacts which is visible to end users; metadata about the contacts are stored in a subfolder that is not visible to end users.</span></span>



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a><span data-ttu-id="09c31-109">針對使用者啟用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="09c31-109">Enabling the Unified Contact Store for a User</span></span>

<span data-ttu-id="09c31-110">如果您已在 Lync Server 2013 和 Exchange 2013 之間設定伺服器對伺服器驗證，則也會啟用整合連絡人存放區的使用;不需要其他伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="09c31-110">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you have also enabled the use of the unified contact store; no additional server configuration is required.</span></span> <span data-ttu-id="09c31-111">不過，要將使用者的連絡人移動至整合連絡人存放區，則需設定其他使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="09c31-111">However, additional user account configuration is required in order to move a user's contacts into the unified contact store.</span></span> <span data-ttu-id="09c31-112">根據預設，使用者連絡人會保留在 Lync Server，而非整合連絡人存放區中。</span><span class="sxs-lookup"><span data-stu-id="09c31-112">By default, user contacts are kept in Lync Server and not in the unified contact store.</span></span>

<span data-ttu-id="09c31-113">使用 Lync Server 使用者服務原則來管理對整合連絡人存放區的存取。</span><span class="sxs-lookup"><span data-stu-id="09c31-113">Access to the unified contact store is managed by using Lync Server user services policies.</span></span> <span data-ttu-id="09c31-114">使用者伺服器原則僅有單一屬性 (UcsAllowed)；此屬性用於決定使用者的連絡人所儲存的位置。</span><span class="sxs-lookup"><span data-stu-id="09c31-114">User server policies have only a single property (UcsAllowed); this property is used to determine the location where a user's contacts are stored.</span></span> <span data-ttu-id="09c31-115">如果使用者是由使用者服務原則所管理，且 UcsAllowed 已設定為 True ($True) 則使用者的連絡人會儲存在統一連絡人存放區中。</span><span class="sxs-lookup"><span data-stu-id="09c31-115">If a user is managed by a user services policy where UcsAllowed has been set to True ($True) then the user's contacts will be stored in the unified contact store.</span></span> <span data-ttu-id="09c31-116">如果使用者是由使用者服務原則所管理，且 UcsAllowed 已設定為 False ($False) 則會將其連絡人儲存在 Lync Server 中。</span><span class="sxs-lookup"><span data-stu-id="09c31-116">If the user is managed by a user services policy where UcsAllowed has been set to False ($False) then his or her contacts will be stored in Lync Server.</span></span>

<span data-ttu-id="09c31-117">當您安裝 Lync Server 2013 時，會同時安裝單一使用者服務原則 (在全域範圍內設定) 。</span><span class="sxs-lookup"><span data-stu-id="09c31-117">When you install Lync Server 2013 a single user services policy (configured at the global scope) is installed as well.</span></span> <span data-ttu-id="09c31-118">這個原則中的 UcsAllowed 值設定為 True，這表示，預設會將使用者連絡人儲存在「整合連絡人存放區」中， (假設已部署並設定) 。</span><span class="sxs-lookup"><span data-stu-id="09c31-118">The UcsAllowed value in this policy is set to True, meaning that, by default, user contacts will be stored in the unified contact store (assuming this has been deployed and configured).</span></span> <span data-ttu-id="09c31-119">如果您想要將所有使用者連絡人遷移至整合連絡人存放區，您不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="09c31-119">If you want to migrate all of your user contacts to the unified contact store you do not have to do anything at all.</span></span>

<span data-ttu-id="09c31-120">如果您不想將所有連絡人遷移至整合連絡人存放區，您可以將全域原則中的 UcsAllowed 屬性設定為 False，以停用所有使用者的整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="09c31-120">If you would prefer not to migrate all your contacts to the unified contact store you can disable the unified contact store for all users by setting the UcsAllowed property in the global policy to False:</span></span>

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

<span data-ttu-id="09c31-121">停用全域原則中的整合連絡人存放區後，您就可以建立個別使用者原則，以啟用整合連絡人存放區的使用;這可讓您讓某些使用者將其連絡人保留在統一連絡人存放區中，而其他使用者仍可繼續在 Lync Server 中保留其連絡人。</span><span class="sxs-lookup"><span data-stu-id="09c31-121">After you have disabled the unified contact store in the global policy you can then create a per-user policy that enables the use of the unified contact store; this allows you to have some users keep their contacts in the unified contact store while other users continue to keep their contacts in Lync Server.</span></span> <span data-ttu-id="09c31-122">您可以使用類似以下的命令來建立個別使用者的使用者服務原則：</span><span class="sxs-lookup"><span data-stu-id="09c31-122">You can create a per-user user services policy by using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

<span data-ttu-id="09c31-p107">在您建立新原則之後，接著您必須將該原則指派給應擁有整合連絡人存放區存取權的任何使用者。您可使用類似以下的命令，將個別使用者原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="09c31-p107">After you have created the new policy you must then assign that policy to any user who should have access to the unified contact store. Per-user policies can be assigned to users by using commands similar to this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

<span data-ttu-id="09c31-125">在指派原則給 Lync Server 之後，就會開始將使用者的連絡人遷移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="09c31-125">After the policy has been assigned Lync Server will begin to migrate the user's contacts to the unified contact store.</span></span> <span data-ttu-id="09c31-126">遷移完成後，使用者將會在 Exchange 中儲存其連絡人，而不是 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="09c31-126">After migration is complete, the user will then have his or her contacts stored in Exchange rather than Lync Server.</span></span> <span data-ttu-id="09c31-127">若使用者在遷移完成時登入 Lync 2013，將會出現一個訊息方塊，而要求他或她會登入 Lync，然後重新登入，以完成此程式。</span><span class="sxs-lookup"><span data-stu-id="09c31-127">If the user happens to be logged on to Lync 2013 at the time migration completes, a message box will appear and he or she will be asked to log off of Lync and then log back on in order to finalize the process.</span></span> <span data-ttu-id="09c31-128">尚未被指派此個別使用者原則的使用者，將不會將其連絡人遷移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="09c31-128">Users who have not been assigned this per-user policy will not have their contacts migrated to the unified contact store.</span></span> <span data-ttu-id="09c31-129">這是因為這些使用者是由全域原則所管理，且已在全域原則中停用統一連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="09c31-129">That’s because those users are being managed by the global policy, and use of the unified contact store has been disabled in the global policy.</span></span>

<span data-ttu-id="09c31-130">您可以從 Lync Server 管理命令介面中執行 [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) Cmdlet，以確認使用者的連絡人是否已順利遷移至整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="09c31-130">You can verify that a user's contacts have successfully been migrated to the unified contact store by running the [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet from within the Lync Server Management Shell:</span></span>

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="09c31-131">如果 Test-CsUnifiedContactStore 成功，就代表使用者 sip:kenmyer@litwareinc.com 的連絡人已經移轉至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="09c31-131">If Test-CsUnifiedContactStore succeeds that means that the contacts for the user sip:kenmyer@litwareinc.com have been migrated to the unified contact store.</span></span>

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a><span data-ttu-id="09c31-132">復原連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="09c31-132">Rolling Back the Unified Contact Store</span></span>

<span data-ttu-id="09c31-133">如果您需要從統一連絡人存放區中移除使用者的連絡人 (例如，如果使用者需要在 Microsoft Lync Server 2010 上 rehomed，而且無法再使用整合連絡人存放區) 必須執行兩項操作。</span><span class="sxs-lookup"><span data-stu-id="09c31-133">If you need to remove a user's contacts from the unified contact store (for example, if the user needs to be rehomed on Microsoft Lync Server 2010 and thus can no longer use the unified contact store) you must do two things.</span></span> <span data-ttu-id="09c31-134">首先，您必須將新的使用者服務原則指派給使用者，而不是使用統一連絡人存放區中儲存連絡人的原則。</span><span class="sxs-lookup"><span data-stu-id="09c31-134">First, you must assign the user a new user services policy, one that prohibits storing contacts in the unified contact store.</span></span> <span data-ttu-id="09c31-135"> (也就是 UcsAllowed 屬性已設定為 $False 的原則。 ) 如果您不具備這類原則，您可以使用類似下列的命令建立一個原則：</span><span class="sxs-lookup"><span data-stu-id="09c31-135">(That is, a policy where the UcsAllowed property has been set to $False.) If you do not have such a policy you can create one using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

<span data-ttu-id="09c31-136">然後您可使用如下命令來指派這個新的個別使用者原則 (NoUnifiedContactStore)：</span><span class="sxs-lookup"><span data-stu-id="09c31-136">You can then assign this new per-user policy (NoUnifiedContactStore) by using a command like this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

<span data-ttu-id="09c31-137">上述命令會將新原則指派給使用者 Ken Myer，同時也會防止 Ken 的連絡人移轉至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="09c31-137">The preceding command assigns the new policy to the user Ken Myer, and also prevents Ken's contacts from being migrated to the unified contact store.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09c31-p110">在某些情況下，您可以單單解除指派使用者的目前使用者服務原則達到相同的整體效果。例如，假設 Ken Myer 擁有個別使用者的使用者服務原則，該原則可啟用整合連絡人存放區，但是您的全域原則禁止整合連絡人存放區的使用。在該情況下，您可以解除指派 Ken 的個別使用者服務原則。當您那樣做時，Ken 會自動受全域原則管理，因此不再有整合連絡人存放區的存取權。</span><span class="sxs-lookup"><span data-stu-id="09c31-p110">In some cases you can achieve the same net effect by simply unassigning the user's current user services policy. For example, suppose Ken Myer has a per-user user services policy the enables the unified contact store, but your global policy prohibits the use of the unified contact store. In that case, you could unassign Ken's per-user services policy. When you do that, Ken will automatically be managed by the global policy, and thus will no longer have access to the unified contact store.</span></span><BR><span data-ttu-id="09c31-142">若要解除指派先前所指派的個別使用者原則，請使用如前所示的相同命令，但這次需將 PolicyName 參數設為 Null 值：</span><span class="sxs-lookup"><span data-stu-id="09c31-142">To unassign a previously-assigned per-user policy, use the same command as shown before, but this time set the PolicyName parameter to a null value:</span></span><BR><span data-ttu-id="09c31-143">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="09c31-143">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



</div>

<span data-ttu-id="09c31-144">在處理整合連絡人存放區時，須牢記「防止 Ken 的連絡人移轉至整合連絡人存放區」這個術語。</span><span class="sxs-lookup"><span data-stu-id="09c31-144">The terminology "prevents Ken's contacts from being migrated to the unified contact store" is important to keep in mind when working with the unified contact store.</span></span> <span data-ttu-id="09c31-145">單單將新的使用者服務原則指派給 Ken 並不會將其連絡人從整合連絡人存放區移出。</span><span class="sxs-lookup"><span data-stu-id="09c31-145">Simply assigning Ken a new user services policy will not move his contacts out of the unified contact store.</span></span> <span data-ttu-id="09c31-146">當使用者登入 Lync Server 2013 時，系統會檢查使用者的使用者服務原則，以查看其連絡人是否應該保留在統一連絡人存放區中。</span><span class="sxs-lookup"><span data-stu-id="09c31-146">When a user logs on to Lync Server 2013, the system checks the user's user services policy to see whether his or her contacts should be kept in the unified contact store.</span></span> <span data-ttu-id="09c31-147">如果結果為肯定 (也就是說，如果 UcsAllowed 屬性設為 $True)，那些連絡人就會移轉至整合連絡人存放區 (假設那些連絡人尚未存放在整合連絡人存放區)。</span><span class="sxs-lookup"><span data-stu-id="09c31-147">If the answer is yes (that is, if the UcsAllowed property is set to $True) then those contacts will be migrated to the unified contact store (assuming that those contacts are not already in the unified contact store).</span></span> <span data-ttu-id="09c31-148">如果答案是 [否]，則 Lync Server 只會忽略使用者的連絡人，並移至下一個工作。</span><span class="sxs-lookup"><span data-stu-id="09c31-148">If the answer is no, then Lync Server simply ignores the user's contacts and moves on to its next task.</span></span> <span data-ttu-id="09c31-149">這表示，不論 UcsAllowed 屬性值為何，Lync Server 不會自動將使用者的連絡人從統一連絡人存放區移出。</span><span class="sxs-lookup"><span data-stu-id="09c31-149">That means that Lync Server will not automatically move a user's contacts from out of the unified contact store, regardless of the value of the UcsAllowed property.</span></span>

<span data-ttu-id="09c31-150">這也表示，在指派使用者新的使用者服務原則之後，您必須執行 [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) 指令程式，以便將使用者的連絡人移出 Exchange 2013 並回到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="09c31-150">That also means that, after assigning the user a new user services policy, you must then run the [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet in order to move the user's contacts out of Exchange 2013 and back to Lync Server 2013.</span></span> <span data-ttu-id="09c31-151">例如，在將新的使用者服務原則指派給 Ken Myer 之後，您就可以使用下列命令將其連絡人移出整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="09c31-151">For example, after assigning Ken Myer a new user services policy you can then move his contacts out of the unified contact store by using the following command:</span></span>

    Invoke-CsUcsRollback -Identity "Ken Myer"

<span data-ttu-id="09c31-152">果您變更使用者服務原則，但是未執行 Invoke-CsUcsRollback Cmdlet，Ken 的連絡人就不會從整合連絡人存放區移除。</span><span class="sxs-lookup"><span data-stu-id="09c31-152">If you change the user services policy but do not run the Invoke-CsUcsRollback cmdlet Ken's contacts will not be removed from the unified contact store.</span></span> <span data-ttu-id="09c31-153">如果您執行 Invoke-CsUcsRollback，但未變更 Ken Myer 的使用者服務原則，會有什麼結果呢？</span><span class="sxs-lookup"><span data-stu-id="09c31-153">What if you run Invoke-CsUcsRollback but do not change Ken Myer's user services policy?</span></span> <span data-ttu-id="09c31-154">在這種情況下，Ken 的連絡人會暫時從整合連絡人存放區中遭移除。</span><span class="sxs-lookup"><span data-stu-id="09c31-154">In that case, Ken's contacts will be temporarily removed from the unified contact store.</span></span> <span data-ttu-id="09c31-155">您務必牢記此移除作業為暫時性的。</span><span class="sxs-lookup"><span data-stu-id="09c31-155">The fact that this removal is temporary is important to keep in mind.</span></span> <span data-ttu-id="09c31-156">當 Ken 的連絡人從統一連絡人存放區中移除之後，Lync Server 2013 將會等候7天，然後查看已指派給 Ken 的使用者服務原則。</span><span class="sxs-lookup"><span data-stu-id="09c31-156">After Ken's contacts have been removed from the unified contact store, Lync Server 2013 will wait 7 days and then check to see which user services policy has been assigned to Ken.</span></span> <span data-ttu-id="09c31-157">如果指派給 Ken 的原則仍然可啟用整合來連絡人存放區，其連絡人就會自動移回連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="09c31-157">If Ken is still assigned a policy that enables the user of the unified contact store, then his contacts will automatically be moved back to into the contact store.</span></span> <span data-ttu-id="09c31-158">若要將連絡人從整合連絡人存放區永久移除，除了執行 Invoke-CsUcsRollback Cmdlet 之外，您還必須變更使用者服務原。</span><span class="sxs-lookup"><span data-stu-id="09c31-158">To permanently remove contacts from the unified contact store you must change the user services policy in addition to running the Invoke-CsUcsRollback cmdlet.</span></span>

<span data-ttu-id="09c31-159">由於大量可影響遷移的變數，因此很難估計帳戶完全遷移至整合連絡人存放區之前所需的時間。</span><span class="sxs-lookup"><span data-stu-id="09c31-159">Due to the large number of variables that can affect migration, it is difficult to estimate how long it will take before accounts are fully migrated to the unified contact store.</span></span> <span data-ttu-id="09c31-160">不過，作為一般規則，遷移不會立即生效：即使遷移少量的連絡人，移動作業完成後，可能需要10分鐘或更多時間。</span><span class="sxs-lookup"><span data-stu-id="09c31-160">As a general rule, however, migration does not take effect immediately: even when migrating a small number of contacts it might take 10 minutes or more before the move is complete.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

