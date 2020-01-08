---
title: 商務用 Skype Online 中的身分識別、範圍和租使用者
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a759c53b717cbaf1ecdb747d5cb01e94b305f52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="739ae-102">商務用 Skype Online 中的身分識別、範圍和租使用者</span><span class="sxs-lookup"><span data-stu-id="739ae-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="739ae-103">_**主題上次修改日期：** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="739ae-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="739ae-104">許多用來管理商務用 Skype Online 的 Windows PowerShell Cmdlet，都需要您特別注意您嘗試管理的專案。</span><span class="sxs-lookup"><span data-stu-id="739ae-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="739ae-105">例如，當您執行[CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) Cmdlet 時，您必須指出您嘗試管理的使用者。</span><span class="sxs-lookup"><span data-stu-id="739ae-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="739ae-106">這麼做很有意義。</span><span class="sxs-lookup"><span data-stu-id="739ae-106">This makes sense.</span></span> <span data-ttu-id="739ae-107">除非您特別告訴 Cmdlet 要管理哪個使用者帳戶，否則**CsUserAcp** Cmdlet 不會知道應該修改哪一個使用者的音訊會議資訊。</span><span class="sxs-lookup"><span data-stu-id="739ae-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="739ae-108">基於這個原因，每當您執行**CsUserAcp** Cmdlet 時，您都會需要加入身分識別參數，後面接著要修改的使用者帳戶身分識別：</span><span class="sxs-lookup"><span data-stu-id="739ae-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="739ae-109">如果「期限」總是參照使用者帳戶的*身分識別，* 就不會有混淆的原因。</span><span class="sxs-lookup"><span data-stu-id="739ae-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="739ae-110">當您處理人員時（使用者、連絡人等等），身分識別會參照個別使用者本身。</span><span class="sxs-lookup"><span data-stu-id="739ae-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="739ae-111">不過，使用者帳戶以外的專案也會有身分識別。</span><span class="sxs-lookup"><span data-stu-id="739ae-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="739ae-112">當您處理商務用 Skype Online 服務的元件時（[原則]、[設定] 設定等），這項身分識別代表的意義稍有不同。</span><span class="sxs-lookup"><span data-stu-id="739ae-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="739ae-113">例如，請考慮下列命令：</span><span class="sxs-lookup"><span data-stu-id="739ae-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="739ae-114">在此情況下，身分識別 "global" 代表會議設定的範圍。</span><span class="sxs-lookup"><span data-stu-id="739ae-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="739ae-115">[*範圍*] 是在商務用 Skype Online （以及 Lync Server）中用來指定球體管理的詞彙。</span><span class="sxs-lookup"><span data-stu-id="739ae-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="739ae-116">根據預設，原則和設定總是擁有全域範圍。</span><span class="sxs-lookup"><span data-stu-id="739ae-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="739ae-117">當您第一次設定商務用 Skype Online 帳戶時，會根據預設，擁有全域原則與設定的集合： [全域會議設定]、[全域外部存取原則]、[全域撥號方案] 等等。</span><span class="sxs-lookup"><span data-stu-id="739ae-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="739ae-118">在 Microsoft Lync Server 2010 中引進了這些全域原則和設定，以協助確保所有使用者和所有元件都能以某種方式管理。</span><span class="sxs-lookup"><span data-stu-id="739ae-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="739ae-119">在 Microsoft Office Communicator 2007 R2 中，這不一定是正確的。</span><span class="sxs-lookup"><span data-stu-id="739ae-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="739ae-120">視您存取系統的方式而定，您可能會在基本不受管理的狀態（通常是因為群組原則無法套用到您的使用者帳戶）中結束。</span><span class="sxs-lookup"><span data-stu-id="739ae-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="739ae-121">相反地，在 Lync Server 和商務用 Skype Online 中，系統不會有任何未受管理的功能。</span><span class="sxs-lookup"><span data-stu-id="739ae-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="739ae-122">這是因為無論其他內容為何，全域原則和設定都將會強制執行。</span><span class="sxs-lookup"><span data-stu-id="739ae-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="739ae-123">我們的意思是 "代替其他內容？</span><span class="sxs-lookup"><span data-stu-id="739ae-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="739ae-124">在商務用 Skype Online 的情況下，您可以在 [標籤*範圍*] 或 [管理] 球形建立原則。</span><span class="sxs-lookup"><span data-stu-id="739ae-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="739ae-125">在標籤範圍建立的原則（也稱為 *[每使用者範圍*]）優先于在全域範圍中建立的原則。</span><span class="sxs-lookup"><span data-stu-id="739ae-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="739ae-126">換句話說，每個使用者的原則將永遠優先于全域原則。</span><span class="sxs-lookup"><span data-stu-id="739ae-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="739ae-127">例如，您可能會有兩個外部使用者存取原則。</span><span class="sxs-lookup"><span data-stu-id="739ae-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="739ae-128">全域原則禁止使用者與在公用立即訊息（IM）提供者（例如 Windows Live）上擁有帳戶的人員進行通訊。</span><span class="sxs-lookup"><span data-stu-id="739ae-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="739ae-129">AllowPublicIMCommunication 的每個使用者原則都允許與公用 IM 提供者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="739ae-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="739ae-130">您也可能有兩個使用者： Ken Myer 及 Pilar 方。</span><span class="sxs-lookup"><span data-stu-id="739ae-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="739ae-131">Ken Myer 已指派給每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="739ae-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="739ae-132">Pilar 方尚未指派給每個使用者的原則;也就是說，她是由全域外部存取原則所管理。</span><span class="sxs-lookup"><span data-stu-id="739ae-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="739ae-133">下表顯示哪個使用者（如果有的話）可以與公用 IM 提供者通訊：</span><span class="sxs-lookup"><span data-stu-id="739ae-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="739ae-134">原則設定</span><span class="sxs-lookup"><span data-stu-id="739ae-134">Policy Settings</span></span></th>
<th><span data-ttu-id="739ae-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="739ae-135">Ken Myer</span></span></th>
<th><span data-ttu-id="739ae-136">Pilar 方</span><span class="sxs-lookup"><span data-stu-id="739ae-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="739ae-137">公用 IM 提供者的全域原則設定</span><span class="sxs-lookup"><span data-stu-id="739ae-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="739ae-138">否</span><span class="sxs-lookup"><span data-stu-id="739ae-138">No</span></span></p></td>
<td><p><span data-ttu-id="739ae-139">否</span><span class="sxs-lookup"><span data-stu-id="739ae-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="739ae-140">公用 IM 提供者的每使用者原則設定</span><span class="sxs-lookup"><span data-stu-id="739ae-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="739ae-141">是</span><span class="sxs-lookup"><span data-stu-id="739ae-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="739ae-142">否</span><span class="sxs-lookup"><span data-stu-id="739ae-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="739ae-143">使用者可以與公用 IM 提供者通訊</span><span class="sxs-lookup"><span data-stu-id="739ae-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="739ae-144">是</span><span class="sxs-lookup"><span data-stu-id="739ae-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="739ae-145">否</span><span class="sxs-lookup"><span data-stu-id="739ae-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="739ae-146">如您所見，您可以使用 Ken Myer 來與公用 IM 提供者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="739ae-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="739ae-147">這是因為指派給他的每個使用者原則中的設定會覆寫全域原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="739ae-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="739ae-148">Pilar 方無法與公用 IM 提供者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="739ae-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="739ae-149">這是因為她是由全域原則所管理，而且全域原則會禁止這類通訊。</span><span class="sxs-lookup"><span data-stu-id="739ae-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="739ae-150">必須由 Office 365 支援為您建立每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="739ae-150">Per-user policies must be created for you by Office 365 Support.</span></span> <span data-ttu-id="739ae-151">建立原則之後，您就可以使用適當的**授與 Cs** Cmdlet （例如，[授與 CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)）指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="739ae-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="739ae-152">每個使用者的原則都容易辨識，因為原則身分識別會以標籤**首碼**為開頭。</span><span class="sxs-lookup"><span data-stu-id="739ae-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="739ae-153">例如：</span><span class="sxs-lookup"><span data-stu-id="739ae-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="739ae-154">標記<STRONG>首碼</STRONG>日期回到 Lync Server 2010 的早期開發日。</span><span class="sxs-lookup"><span data-stu-id="739ae-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="739ae-155">在這些天數中，每個使用者的原則稱為<EM>標記原則</EM>，且是由標籤<STRONG>首碼</STRONG>所識別。</span><span class="sxs-lookup"><span data-stu-id="739ae-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="739ae-156">現在，這些原則會更精確地參照為<EM>每個使用者的原則</EM>，而標記範圍則更準確地稱為 [<EM>每使用者] 範圍</EM>。</span><span class="sxs-lookup"><span data-stu-id="739ae-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="739ae-157">不過，出於技術方面的原因，不會變更標記的<STRONG>首碼</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="739ae-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="739ae-158">使用商務用 Skype Online 和 Windows PowerShell*時所使用的另*一個重要詞彙。</span><span class="sxs-lookup"><span data-stu-id="739ae-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="739ae-159">當您設定商務用 Skype Online 帳戶時，系統會指派新部署的租使用者識別碼編號，這是類似以下的全域唯一識別碼（GUID）：</span><span class="sxs-lookup"><span data-stu-id="739ae-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="739ae-160">幾個商務用 Skype Online Cmdlet 需要您在執行 Cmdlet 時輸入租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="739ae-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="739ae-161">您必須輸入租使用者識別碼，即使您已登入，且只有一個租使用者。</span><span class="sxs-lookup"><span data-stu-id="739ae-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="739ae-162">幸運的是，您不需要記住租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="739ae-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="739ae-163">您可以執行下列 Windows PowerShell 命令，隨時取得您的租使用者識別碼：</span><span class="sxs-lookup"><span data-stu-id="739ae-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="739ae-164">當然，只要知道全域範圍與每個使用者範圍（或標籤範圍）之間的差異，就只需要一半的工作。</span><span class="sxs-lookup"><span data-stu-id="739ae-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="739ae-165">您也可以瞭解何時（或即使是您）使用這些範圍。</span><span class="sxs-lookup"><span data-stu-id="739ae-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="739ae-166">對於身分識別和租使用者參數，也是如此。</span><span class="sxs-lookup"><span data-stu-id="739ae-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="739ae-167">下列主題說明不同的商務用 Skype Online Cmdlet 如何使用身分識別、範圍和租使用者參數：</span><span class="sxs-lookup"><span data-stu-id="739ae-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="739ae-168">商務用 Skype Online 的 Cmdlet 只使用全域範圍</span><span class="sxs-lookup"><span data-stu-id="739ae-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="739ae-169">商務用 Skype Online 中使用全域範圍和標籤範圍的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="739ae-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="739ae-170">商務用 Skype Online 中使用使用者身分識別的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="739ae-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="739ae-171">商務用 Skype Online 中使用使用者身分識別和標籤範圍的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="739ae-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="739ae-172">商務用 Skype Online 中使用租使用者參數的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="739ae-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="739ae-173">商務用 Skype Online 中使用會議提供者身分識別的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="739ae-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="739ae-174">商務用 Skype Online 中不使用範圍或身分識別的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="739ae-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

