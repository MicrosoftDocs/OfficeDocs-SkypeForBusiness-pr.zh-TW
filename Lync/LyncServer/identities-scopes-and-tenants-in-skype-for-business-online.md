---
title: 商務用 Skype Online 中的身分識別、範圍和承租人
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3e5217c4214e6e86ca4c1dff62410c247cf7f8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="b7cf9-102">商務用 Skype Online 中的身分識別、範圍和承租人</span><span class="sxs-lookup"><span data-stu-id="b7cf9-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7cf9-103">_**主題上次修改日期：** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="b7cf9-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="b7cf9-104">許多用來管理商務用 Skype Online 的 Windows PowerShell Cmdlet，都需要您特別注意嘗試管理的專案。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="b7cf9-105">例如，當您執行 CsUserAcp 指令[程式](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)時，您必須指出嘗試管理的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="b7cf9-106">這會有意義。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-106">This makes sense.</span></span> <span data-ttu-id="b7cf9-107">除非您明確告訴 Cmdlet 要管理哪個使用者帳戶，否則**CsUserAcp 指令程式**不會知道應修改哪一個使用者的音訊會議資訊。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="b7cf9-108">基於這個理由，每次執行 CsUserAcp 指令**程式**時，您必須加入 identity 參數，後面接著要修改的使用者帳戶身分識別：</span><span class="sxs-lookup"><span data-stu-id="b7cf9-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="b7cf9-109">如果字詞*識別碼*永遠稱為使用者帳戶的身分識別，將不會造成混淆的原因很小。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="b7cf9-110">當您處理人員時（使用者、連絡人等等），身分識別會參照個別的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="b7cf9-111">不過，使用者帳戶以外的專案也具有身分識別。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="b7cf9-112">當您處理商務用 Skype Online 服務的元件時（原則、設定設定等等），「字詞身分識別」表示有些略有不同。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="b7cf9-113">例如，請考慮下列命令：</span><span class="sxs-lookup"><span data-stu-id="b7cf9-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="b7cf9-114">在此情況下，身分識別 "global" 是指會議配置設定的範圍。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="b7cf9-115">*範圍*是用於商務用 Skype Online （在 Lync Server 中，也就是 Lync Server）中的字詞，用來指定的管理。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="b7cf9-116">原則和設定預設會永遠具有全域範圍。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="b7cf9-117">當您第一次設定商務用 Skype Online 帳戶時，預設會有一個全域原則和設定的集合，全域會議設定、全域外部存取原則、全域撥號對應表等的集合。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="b7cf9-118">這些全域原則和設定會在 Microsoft Lync Server 2010 中引進，以協助確保所有使用者和所有元件都一定會受到管理。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="b7cf9-119">在 Microsoft Office Communicator 2007 R2 中，這不一定是 true。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="b7cf9-120">視您存取系統的方式而定，您可能會有很大的非管理狀態（通常是因為群組原則無法套用至您的使用者帳戶）。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="b7cf9-121">相反地，在 Lync Server 和商務用 Skype Online 中，永遠不會留下任何專案。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="b7cf9-122">這是因為絕對會強制執行全域原則及設定，而不是任何其他專案。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="b7cf9-123">「代替其他任何人」是什麼意思？</span><span class="sxs-lookup"><span data-stu-id="b7cf9-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="b7cf9-124">好的情況是，在商務用 Skype Online 中，您可以在*標記範圍*或管理的球體建立原則。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="b7cf9-125">在標記範圍建立的原則（也稱為個別*使用者範圍*）優先于在全域範圍內建立的原則。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="b7cf9-126">換句話說，每一使用者原則永遠優先于全域原則。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="b7cf9-127">例如，您可能有兩個外部使用者存取原則。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="b7cf9-128">全域原則禁止使用者與在公用立即訊息（IM）提供者（例如 Windows Live）上帳戶的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="b7cf9-129">每一使用者原則 AllowPublicIMCommunication，允許與公用 IM 提供者通訊。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="b7cf9-130">您也可能會有兩位使用者： Ken Myer 和 Pilar Ackerman。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="b7cf9-131">Ken Myer 已被指派每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="b7cf9-132">尚未將每一使用者原則指派給 Pilar Ackerman;也就是說，她是由全域外部存取原則所管理。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="b7cf9-133">下表顯示可與公用 IM 提供者通訊的使用者（如果有的話）：</span><span class="sxs-lookup"><span data-stu-id="b7cf9-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7cf9-134">原則設定</span><span class="sxs-lookup"><span data-stu-id="b7cf9-134">Policy Settings</span></span></th>
<th><span data-ttu-id="b7cf9-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="b7cf9-135">Ken Myer</span></span></th>
<th><span data-ttu-id="b7cf9-136">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="b7cf9-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7cf9-137">公用 IM 提供者的全域原則設定</span><span class="sxs-lookup"><span data-stu-id="b7cf9-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="b7cf9-138">否</span><span class="sxs-lookup"><span data-stu-id="b7cf9-138">No</span></span></p></td>
<td><p><span data-ttu-id="b7cf9-139">否</span><span class="sxs-lookup"><span data-stu-id="b7cf9-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7cf9-140">公用 IM 提供者的每一使用者原則設定</span><span class="sxs-lookup"><span data-stu-id="b7cf9-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="b7cf9-141">是</span><span class="sxs-lookup"><span data-stu-id="b7cf9-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="b7cf9-142">否</span><span class="sxs-lookup"><span data-stu-id="b7cf9-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7cf9-143">使用者可以與公用 IM 提供者通訊</span><span class="sxs-lookup"><span data-stu-id="b7cf9-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="b7cf9-144">是</span><span class="sxs-lookup"><span data-stu-id="b7cf9-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="b7cf9-145">否</span><span class="sxs-lookup"><span data-stu-id="b7cf9-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b7cf9-146">如您所見，允許 Ken Myer 與公用 IM 提供者通訊。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="b7cf9-147">這是因為指派給他的個別使用者原則中的設定會覆寫全域原則中的設定。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="b7cf9-148">Pilar Ackerman 無法與公用 IM 提供者通訊。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="b7cf9-149">這是因為她是由全域原則所管理，而全域原則則禁止這類通訊。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="b7cf9-150">每個使用者的原則都必須為您建立 Microsoft 支援服務。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-150">Per-user policies must be created for you by Microsoft Support.</span></span> <span data-ttu-id="b7cf9-151">建立原則之後，您可以使用適當的**授與 Cs** Cmdlet 將它們指派給使用者（例如，[授與 get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)）。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="b7cf9-152">因為原則識別永遠以標記**前置**詞開頭，所以個別使用者原則很容易識別。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="b7cf9-153">例如：</span><span class="sxs-lookup"><span data-stu-id="b7cf9-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="b7cf9-154">標記<STRONG>首碼</STRONG>日期回到 Lync Server 2010 的早期開發天。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="b7cf9-155">在這天內，每個使用者的原則稱為<EM>標記原則</EM>，並由標記<STRONG>前置</STRONG>詞識別。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="b7cf9-156">這些原則現在會以<EM>每個使用者的原則</EM>更準確地稱為，標籤範圍會更準確地稱為個別<EM>使用者範圍</EM>。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="b7cf9-157">不過，由於技術原因，標記<STRONG>首碼</STRONG>永遠不會變更。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="b7cf9-158">使用商務用 Skype Online 和 Windows PowerShell 的另一個關鍵術語是*租*使用者。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="b7cf9-159">當您設定商務用 Skype Online 帳戶時，您的新部署會指派租使用者識別碼（GUID），這是類似以下的全域唯一識別碼（GUID）：</span><span class="sxs-lookup"><span data-stu-id="b7cf9-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="b7cf9-160">在您每次執行 Cmdlet 時，有些商務用 Skype Online Cmdlet 會要求您輸入租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="b7cf9-161">您必須輸入租使用者識別碼，即使您已登入，而且只有一個承租人。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="b7cf9-162">幸運的是，您不需要記住租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="b7cf9-163">您可以隨時執行下列 Windows PowerShell 命令，來取得租使用者識別碼：</span><span class="sxs-lookup"><span data-stu-id="b7cf9-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="b7cf9-164">當然，知道全域範圍和個別使用者範圍（或標記範圍）之間的差異，只是部分工作。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="b7cf9-165">請務必知道何時（或甚至是）您可以使用這些範圍。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="b7cf9-166">識別碼和租使用者參數也是如此。</span><span class="sxs-lookup"><span data-stu-id="b7cf9-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="b7cf9-167">下列主題說明不同的商務用 Skype Online Cmdlet 如何使用 identity、範圍及承租人參數：</span><span class="sxs-lookup"><span data-stu-id="b7cf9-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="b7cf9-168">僅使用全域範圍之商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b7cf9-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="b7cf9-169">使用全域範圍及標記範圍的商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b7cf9-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="b7cf9-170">使用使用者身分識別的商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b7cf9-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="b7cf9-171">使用使用者身分識別及標記範圍的商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b7cf9-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="b7cf9-172">使用承租人參數的商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b7cf9-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="b7cf9-173">使用會議提供者身分識別的商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b7cf9-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="b7cf9-174">在商務用 Skype Online 中不使用範圍或身分識別的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b7cf9-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

