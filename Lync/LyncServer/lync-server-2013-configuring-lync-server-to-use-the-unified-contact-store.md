---
title: Lync Server 2013：將 Lync Server 設定為使用整合連絡人存放區
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
ms.openlocfilehash: 794d14172c5932436d46fbeb66ea1da4dd7a5e44
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a><span data-ttu-id="f7705-102">將 Microsoft Lync Server 2013 設定為使用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="f7705-102">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7705-103">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="f7705-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="f7705-104">「整合連絡人存放區」可讓使用者維護單一連絡人清單，然後讓這些連絡人在多個應用程式中使用，包括 Microsoft Lync 2013、Microsoft Outlook 2013 及 Microsoft Outlook Web App 2013。</span><span class="sxs-lookup"><span data-stu-id="f7705-104">The unified contact store enables users to maintain a single contacts list and then have those contacts available in multiple applications, including Microsoft Lync 2013, Microsoft Outlook 2013, and Microsoft Outlook Web App 2013.</span></span> <span data-ttu-id="f7705-105">當您為使用者啟用 [整合連絡人存放區] 時，使用者的連絡人不會儲存在 Microsoft Lync Server 2013，然後使用 SIP 通訊協定進行檢索。</span><span class="sxs-lookup"><span data-stu-id="f7705-105">When you enable the unified contact store for a user that user's contacts are not stored in Microsoft Lync Server 2013 and then retrieved using the SIP protocol.</span></span> <span data-ttu-id="f7705-106">相反地，他/她的連絡人會儲存在 Microsoft Exchange Server 2013 中，並會使用 Exchange Web 服務進行檢索。</span><span class="sxs-lookup"><span data-stu-id="f7705-106">Instead, his or her contacts are stored in Microsoft Exchange Server 2013 and are retrieved by using Exchange Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7705-107">從技術角度來看，連絡人資訊是儲存在使用者的 Exchange 2013 信箱中的一組資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f7705-107">Technically, contact information is stored in a pair of folders found in the user's Exchange 2013 mailbox.</span></span> <span data-ttu-id="f7705-108">連絡人本身會儲存在名為「Lync 連絡人」的資料夾中，使用者對使用者可見;連絡人的中繼資料儲存在使用者無法看見的子資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f7705-108">The contacts themselves are stored in a folder named Lync Contacts which is visible to end users; metadata about the contacts are stored in a subfolder that is not visible to end users.</span></span>



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a><span data-ttu-id="f7705-109">為使用者啟用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="f7705-109">Enabling the Unified Contact Store for a User</span></span>

<span data-ttu-id="f7705-110">如果您已在 Lync Server 2013 與 Exchange 2013 之間設定伺服器對伺服器驗證，則表示您也已啟用整合連絡人存放區的使用;不需要額外的伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="f7705-110">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you have also enabled the use of the unified contact store; no additional server configuration is required.</span></span> <span data-ttu-id="f7705-111">不過，您需要額外的使用者帳戶設定，才能將使用者的連絡人移至 [整合連絡人] 存放區。</span><span class="sxs-lookup"><span data-stu-id="f7705-111">However, additional user account configuration is required in order to move a user's contacts into the unified contact store.</span></span> <span data-ttu-id="f7705-112">根據預設，使用者連絡人會保留在 Lync Server，而不是在整合連絡人存放區中。</span><span class="sxs-lookup"><span data-stu-id="f7705-112">By default, user contacts are kept in Lync Server and not in the unified contact store.</span></span>

<span data-ttu-id="f7705-113">使用 Lync Server 使用者服務原則管理對整合連絡人存放區的存取權。</span><span class="sxs-lookup"><span data-stu-id="f7705-113">Access to the unified contact store is managed by using Lync Server user services policies.</span></span> <span data-ttu-id="f7705-114">使用者伺服器原則只有單一屬性（UcsAllowed）;這個屬性是用來判斷使用者連絡人的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="f7705-114">User server policies have only a single property (UcsAllowed); this property is used to determine the location where a user's contacts are stored.</span></span> <span data-ttu-id="f7705-115">如果使用者是由使用者服務原則所管理，而 UcsAllowed 已設定為 True （$True），則使用者的連絡人會儲存在整合連絡人存放區中。</span><span class="sxs-lookup"><span data-stu-id="f7705-115">If a user is managed by a user services policy where UcsAllowed has been set to True ($True) then the user's contacts will be stored in the unified contact store.</span></span> <span data-ttu-id="f7705-116">如果使用者是由使用者服務原則所管理，而 UcsAllowed 已設定為 False （$False），則他/她的連絡人將會儲存在 Lync Server 中。</span><span class="sxs-lookup"><span data-stu-id="f7705-116">If the user is managed by a user services policy where UcsAllowed has been set to False ($False) then his or her contacts will be stored in Lync Server.</span></span>

<span data-ttu-id="f7705-117">當您安裝 Lync Server 2013 時，會同時安裝單一使用者服務原則（在全域範圍中設定）。</span><span class="sxs-lookup"><span data-stu-id="f7705-117">When you install Lync Server 2013 a single user services policy (configured at the global scope) is installed as well.</span></span> <span data-ttu-id="f7705-118">此原則中的 UcsAllowed 值會設定為 True，這表示預設會將使用者連絡人儲存在整合連絡人存放區中（假設已部署並設定）。</span><span class="sxs-lookup"><span data-stu-id="f7705-118">The UcsAllowed value in this policy is set to True, meaning that, by default, user contacts will be stored in the unified contact store (assuming this has been deployed and configured).</span></span> <span data-ttu-id="f7705-119">如果您想要將所有使用者連絡人遷移至 [整合連絡人] 商店，您不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="f7705-119">If you want to migrate all of your user contacts to the unified contact store you do not have to do anything at all.</span></span>

<span data-ttu-id="f7705-120">如果您不想將所有連絡人移至 [整合連絡人] 商店，您可以將 [全域原則] 中的 [UcsAllowed] 屬性設為 False，以停用所有使用者的整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="f7705-120">If you would prefer not to migrate all your contacts to the unified contact store you can disable the unified contact store for all users by setting the UcsAllowed property in the global policy to False:</span></span>

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

<span data-ttu-id="f7705-121">在全域原則中停用整合連絡人存放區之後，您就可以建立可讓您使用整合連絡人存放區的每個使用者原則;這可讓您讓一些使用者將他們的連絡人保留在 [整合連絡人] 存放區中，而其他使用者則能繼續在 Lync Server 中保留他們的連絡人。</span><span class="sxs-lookup"><span data-stu-id="f7705-121">After you have disabled the unified contact store in the global policy you can then create a per-user policy that enables the use of the unified contact store; this allows you to have some users keep their contacts in the unified contact store while other users continue to keep their contacts in Lync Server.</span></span> <span data-ttu-id="f7705-122">您可以使用類似以下的命令來建立每使用者使用者服務原則：</span><span class="sxs-lookup"><span data-stu-id="f7705-122">You can create a per-user user services policy by using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

<span data-ttu-id="f7705-123">在您建立新原則之後，您必須將該原則指派給應該有權存取整合連絡人存放區的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="f7705-123">After you have created the new policy you must then assign that policy to any user who should have access to the unified contact store.</span></span> <span data-ttu-id="f7705-124">您可以使用類似以下的命令，將每個使用者的原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="f7705-124">Per-user policies can be assigned to users by using commands similar to this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

<span data-ttu-id="f7705-125">策略指派 Lync Server 之後，就會開始將使用者的連絡人遷移至 [整合連絡人] 存放區。</span><span class="sxs-lookup"><span data-stu-id="f7705-125">After the policy has been assigned Lync Server will begin to migrate the user's contacts to the unified contact store.</span></span> <span data-ttu-id="f7705-126">完成遷移之後，使用者就會將自己的連絡人儲存在 Exchange 中，而不是 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="f7705-126">After migration is complete, the user will then have his or her contacts stored in Exchange rather than Lync Server.</span></span> <span data-ttu-id="f7705-127">如果在遷移完成時，使用者登入 Lync 2013，就會出現一則訊息，然後系統會要求他/她登出 Lync，然後重新登入以完成程式。</span><span class="sxs-lookup"><span data-stu-id="f7705-127">If the user happens to be logged on to Lync 2013 at the time migration completes, a message box will appear and he or she will be asked to log off of Lync and then log back on in order to finalize the process.</span></span> <span data-ttu-id="f7705-128">未獲指派此每個使用者原則的使用者，將不會將其連絡人遷移至 [整合連絡人] 存放區。</span><span class="sxs-lookup"><span data-stu-id="f7705-128">Users who have not been assigned this per-user policy will not have their contacts migrated to the unified contact store.</span></span> <span data-ttu-id="f7705-129">這是因為這些使用者是由全域原則所管理，而「整合連絡人存放區」已在全域原則中停用。</span><span class="sxs-lookup"><span data-stu-id="f7705-129">That’s because those users are being managed by the global policy, and use of the unified contact store has been disabled in the global policy.</span></span>

<span data-ttu-id="f7705-130">您可以從 Lync Server Management Shell 中執行[Test CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) Cmdlet，以驗證使用者的連絡人是否已順利遷移到整合連絡人存放區：</span><span class="sxs-lookup"><span data-stu-id="f7705-130">You can verify that a user's contacts have successfully been migrated to the unified contact store by running the [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet from within the Lync Server Management Shell:</span></span>

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f7705-131">如果 CsUnifiedContactStore 成功，則表示使用者 sip:kenmyer@litwareinc.com 的連絡人已遷移至整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="f7705-131">If Test-CsUnifiedContactStore succeeds that means that the contacts for the user sip:kenmyer@litwareinc.com have been migrated to the unified contact store.</span></span>

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a><span data-ttu-id="f7705-132">回退整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="f7705-132">Rolling Back the Unified Contact Store</span></span>

<span data-ttu-id="f7705-133">如果您需要從 [整合連絡人] 存放區中移除使用者的連絡人（例如，如果使用者需要在 Microsoft Lync Server 2010 上 rehomed，因此不能再使用 [整合連絡人] 存放區），您必須執行兩個動作。</span><span class="sxs-lookup"><span data-stu-id="f7705-133">If you need to remove a user's contacts from the unified contact store (for example, if the user needs to be rehomed on Microsoft Lync Server 2010 and thus can no longer use the unified contact store) you must do two things.</span></span> <span data-ttu-id="f7705-134">首先，您必須為使用者指派新的使用者服務原則，該原則禁止在整合連絡人存放區中儲存連絡人。</span><span class="sxs-lookup"><span data-stu-id="f7705-134">First, you must assign the user a new user services policy, one that prohibits storing contacts in the unified contact store.</span></span> <span data-ttu-id="f7705-135">（也就是 UcsAllowed 屬性已設為 $False 的原則）。如果您沒有這樣的原則，您可以使用類似以下的命令來建立一個原則：</span><span class="sxs-lookup"><span data-stu-id="f7705-135">(That is, a policy where the UcsAllowed property has been set to $False.) If you do not have such a policy you can create one using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

<span data-ttu-id="f7705-136">然後，您可以使用如下所示的命令來指派這個新的每個使用者原則（NoUnifiedContactStore）：</span><span class="sxs-lookup"><span data-stu-id="f7705-136">You can then assign this new per-user policy (NoUnifiedContactStore) by using a command like this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

<span data-ttu-id="f7705-137">上述命令會將新的原則指派給使用者 Ken Myer，同時也會防止 Ken 的連絡人遷移到整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="f7705-137">The preceding command assigns the new policy to the user Ken Myer, and also prevents Ken's contacts from being migrated to the unified contact store.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7705-138">在某些情況下，您只要取消指派使用者目前的使用者服務原則，就能達到相同的網路效果。</span><span class="sxs-lookup"><span data-stu-id="f7705-138">In some cases you can achieve the same net effect by simply unassigning the user's current user services policy.</span></span> <span data-ttu-id="f7705-139">例如，假設 Ken Myer 的每個使用者服務原則都是啟用整合連絡人存放區，但是您的全域原則禁止使用整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="f7705-139">For example, suppose Ken Myer has a per-user user services policy the enables the unified contact store, but your global policy prohibits the use of the unified contact store.</span></span> <span data-ttu-id="f7705-140">在這種情況下，您可以取消指派 Ken 的每個使用者服務原則。</span><span class="sxs-lookup"><span data-stu-id="f7705-140">In that case, you could unassign Ken's per-user services policy.</span></span> <span data-ttu-id="f7705-141">當您執行此動作時，系統會自動由全域原則管理，因此將不再擁有對整合連絡人存放區的存取權。</span><span class="sxs-lookup"><span data-stu-id="f7705-141">When you do that, Ken will automatically be managed by the global policy, and thus will no longer have access to the unified contact store.</span></span><BR><span data-ttu-id="f7705-142">若要取消指派先前指派的每個使用者原則，請使用相同的命令（如上所示），但這次將 PolicyName 參數設定為 null 值：</span><span class="sxs-lookup"><span data-stu-id="f7705-142">To unassign a previously-assigned per-user policy, use the same command as shown before, but this time set the PolicyName parameter to a null value:</span></span><BR><span data-ttu-id="f7705-143">授與 CsUserServicesPolicy –身分識別「Ken Myer」– PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="f7705-143">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



</div>

<span data-ttu-id="f7705-144">在使用 [整合連絡人存放區] 時，請務必記住「防止 Ken 連絡人遷移到整合連絡人存放區」這一術語。</span><span class="sxs-lookup"><span data-stu-id="f7705-144">The terminology "prevents Ken's contacts from being migrated to the unified contact store" is important to keep in mind when working with the unified contact store.</span></span> <span data-ttu-id="f7705-145">只要將 Ken 指派給新的使用者服務原則，就不會將自己的連絡人移出 [整合連絡人] 存放區。</span><span class="sxs-lookup"><span data-stu-id="f7705-145">Simply assigning Ken a new user services policy will not move his contacts out of the unified contact store.</span></span> <span data-ttu-id="f7705-146">當使用者登入 Lync Server 2013 時，系統會檢查使用者的使用者服務原則，以查看他/她的連絡人是否應該保留在整合連絡人存放區中。</span><span class="sxs-lookup"><span data-stu-id="f7705-146">When a user logs on to Lync Server 2013, the system checks the user's user services policy to see whether his or her contacts should be kept in the unified contact store.</span></span> <span data-ttu-id="f7705-147">如果答案是 [是] （也就是 UcsAllowed 屬性設為 [$True]），這些連絡人將會遷移至 [整合連絡人] 存放區（假設這些連絡人不在 [整合連絡人] 存放區中）。</span><span class="sxs-lookup"><span data-stu-id="f7705-147">If the answer is yes (that is, if the UcsAllowed property is set to $True) then those contacts will be migrated to the unified contact store (assuming that those contacts are not already in the unified contact store).</span></span> <span data-ttu-id="f7705-148">如果答案為 [否]，則 Lync Server 只會忽略使用者的連絡人，然後移至它的下一個工作。</span><span class="sxs-lookup"><span data-stu-id="f7705-148">If the answer is no, then Lync Server simply ignores the user's contacts and moves on to its next task.</span></span> <span data-ttu-id="f7705-149">這表示不論 UcsAllowed 屬性的值為何，Lync Server 不會自動將使用者的連絡人從整合的連絡人存放區移出。</span><span class="sxs-lookup"><span data-stu-id="f7705-149">That means that Lync Server will not automatically move a user's contacts from out of the unified contact store, regardless of the value of the UcsAllowed property.</span></span>

<span data-ttu-id="f7705-150">這也表示將使用者指派給新的使用者服務原則之後，您必須執行[CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) Cmdlet，以便將使用者的連絡人移出 Exchange 2013，然後返回 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f7705-150">That also means that, after assigning the user a new user services policy, you must then run the [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet in order to move the user's contacts out of Exchange 2013 and back to Lync Server 2013.</span></span> <span data-ttu-id="f7705-151">例如，將 Ken Myer 指派給新的使用者服務原則之後，您就可以使用下列命令，將其連絡人移出 [整合連絡人] 存放區：</span><span class="sxs-lookup"><span data-stu-id="f7705-151">For example, after assigning Ken Myer a new user services policy you can then move his contacts out of the unified contact store by using the following command:</span></span>

    Invoke-CsUcsRollback -Identity "Ken Myer"

<span data-ttu-id="f7705-152">如果您變更使用者服務原則，但不執行 CsUcsRollback Cmdlet Ken 的連絡人，則不會從整合連絡人存放區中移除。</span><span class="sxs-lookup"><span data-stu-id="f7705-152">If you change the user services policy but do not run the Invoke-CsUcsRollback cmdlet Ken's contacts will not be removed from the unified contact store.</span></span> <span data-ttu-id="f7705-153">如果您執行的是 Invoke CsUcsRollback，但不會變更 Ken Myer 的使用者服務原則，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="f7705-153">What if you run Invoke-CsUcsRollback but do not change Ken Myer's user services policy?</span></span> <span data-ttu-id="f7705-154">在這種情況下，Ken 連絡人將會暫時從整合連絡人存放區中移除。</span><span class="sxs-lookup"><span data-stu-id="f7705-154">In that case, Ken's contacts will be temporarily removed from the unified contact store.</span></span> <span data-ttu-id="f7705-155">這個移除是臨時性的，這項功能很重要，請務必記住這一點。</span><span class="sxs-lookup"><span data-stu-id="f7705-155">The fact that this removal is temporary is important to keep in mind.</span></span> <span data-ttu-id="f7705-156">從 [整合連絡人] 存放區移除 Ken 連絡人後，Lync Server 2013 將等待7天，然後檢查已指派給 Ken 的使用者服務原則。</span><span class="sxs-lookup"><span data-stu-id="f7705-156">After Ken's contacts have been removed from the unified contact store, Lync Server 2013 will wait 7 days and then check to see which user services policy has been assigned to Ken.</span></span> <span data-ttu-id="f7705-157">如果 Ken 仍獲指派可讓整合連絡人存放區使用者使用的原則，則他的連絡人會自動移回連絡人存放區中。</span><span class="sxs-lookup"><span data-stu-id="f7705-157">If Ken is still assigned a policy that enables the user of the unified contact store, then his contacts will automatically be moved back to into the contact store.</span></span> <span data-ttu-id="f7705-158">若要從 [整合連絡人] 存放區永久移除連絡人，除了執行 CsUcsRollback Cmdlet 之外，您還必須變更使用者服務原則。</span><span class="sxs-lookup"><span data-stu-id="f7705-158">To permanently remove contacts from the unified contact store you must change the user services policy in addition to running the Invoke-CsUcsRollback cmdlet.</span></span>

<span data-ttu-id="f7705-159">由於有大量可影響遷移的變數，所以很難估計帳戶完全遷移到整合連絡人存放區之前所需的時間。</span><span class="sxs-lookup"><span data-stu-id="f7705-159">Due to the large number of variables that can affect migration, it is difficult to estimate how long it will take before accounts are fully migrated to the unified contact store.</span></span> <span data-ttu-id="f7705-160">但作為一般規則，遷移不會立即生效：即使遷移少量的連絡人，移動作業也可能需要10分鐘或更長的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="f7705-160">As a general rule, however, migration does not take effect immediately: even when migrating a small number of contacts it might take 10 minutes or more before the move is complete.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

