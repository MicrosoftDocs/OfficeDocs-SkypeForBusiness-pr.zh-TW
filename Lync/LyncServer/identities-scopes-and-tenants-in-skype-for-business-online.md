---
title: 身分識別、 範圍與 skype for Business Online 租用戶
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dd2008984707f1f8e76b7e61074d5303c0d0819
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="dd162-102">身分識別、 範圍與 skype for Business Online 租用戶</span><span class="sxs-lookup"><span data-stu-id="dd162-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd162-103">_**主題上次修改日期：** 2015年-03-09_</span><span class="sxs-lookup"><span data-stu-id="dd162-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="dd162-104">許多用來管理商務用 Skype 的 Windows PowerShell cmdlet 需要非常特定的對想要管理的項目。</span><span class="sxs-lookup"><span data-stu-id="dd162-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="dd162-105">例如，當您執行[設定 CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)指令程式，您必須指定想要管理的使用者。</span><span class="sxs-lookup"><span data-stu-id="dd162-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="dd162-106">這是合理。</span><span class="sxs-lookup"><span data-stu-id="dd162-106">This makes sense.</span></span> <span data-ttu-id="dd162-107">除非您特別告知指令程式來管理使用者帳戶，**設定 CsUserAcp**指令程式都有任何想法應該可以修改哪些使用者的音訊會議資訊。</span><span class="sxs-lookup"><span data-stu-id="dd162-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="dd162-108">基於這個理由，每次您執行**設定 CsUserAcp** cmdlet 時，您將需要加入 Identity 參數，後面接著要修改的使用者帳戶的身分識別：</span><span class="sxs-lookup"><span data-stu-id="dd162-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="dd162-109">如果字詞一律參照的使用者帳戶的身分識別*身分識別*，就很少造成混淆。</span><span class="sxs-lookup"><span data-stu-id="dd162-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="dd162-110">當您正在處理與人員 （使用者、 連絡人、 等等） 時，身分識別參照個別的使用者本身。</span><span class="sxs-lookup"><span data-stu-id="dd162-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="dd162-111">不過，使用者帳戶以外的項目也有身分識別。</span><span class="sxs-lookup"><span data-stu-id="dd162-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="dd162-112">當您在處理與 Skype for Business Online service 的元件-原則、 組態設定，等等 — 身分識別 」 是指稍有不同的字詞。</span><span class="sxs-lookup"><span data-stu-id="dd162-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="dd162-113">例如，假設此命令：</span><span class="sxs-lookup"><span data-stu-id="dd162-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="dd162-114">在此情況下，Identity 為"global 」 指的是範圍的會議組態設定。</span><span class="sxs-lookup"><span data-stu-id="dd162-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="dd162-115">*範圍*是和所用的商務用 Skype （Lync Server） 的字詞來指定鄰的管理。</span><span class="sxs-lookup"><span data-stu-id="dd162-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="dd162-116">根據預設，原則與設定一律會擁有全域範圍。</span><span class="sxs-lookup"><span data-stu-id="dd162-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="dd162-117">當您第一次設定您 Skype for Business Online 帳戶必須，根據預設，全域原則及設定一群 — 全域會議組態設定、 全域外部存取原則、 全域撥號對應表，依此類推。</span><span class="sxs-lookup"><span data-stu-id="dd162-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="dd162-118">為了協助確保之所有使用者和所有元件會永遠，以某種方式，受管理的 Microsoft Lync Server 2010 中引進下列全域原則與設定。</span><span class="sxs-lookup"><span data-stu-id="dd162-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="dd162-119">這是不一定為 true，Microsoft Office Communicator 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="dd162-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="dd162-120">根據您，如何存取系統，您無法可能最後的主要是未受管理的狀態 （通常是因為群組原則無法套用至您的使用者帳戶）。</span><span class="sxs-lookup"><span data-stu-id="dd162-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="dd162-121">相反地，在 Lync Server 和商務用 Skype，則是 nothing 屬於左未受管理。</span><span class="sxs-lookup"><span data-stu-id="dd162-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="dd162-122">這是因為任何動作，您就不用全域原則與設定將一律會強制執行。</span><span class="sxs-lookup"><span data-stu-id="dd162-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="dd162-123">我們由 「 就不需任何其他項目 」 代表什麼意義？</span><span class="sxs-lookup"><span data-stu-id="dd162-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="dd162-124">Skype 商務 Online，若是沒錯，可以建立原則*標記的範圍*，或管理的圓球。</span><span class="sxs-lookup"><span data-stu-id="dd162-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="dd162-125">在標記範圍 （也就是*個別使用者範圍*） 中建立的原則優先於全域範圍建立原則。</span><span class="sxs-lookup"><span data-stu-id="dd162-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="dd162-126">換句話說，每一使用者原則將會一律優先於全域原則。</span><span class="sxs-lookup"><span data-stu-id="dd162-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="dd162-127">例如，您可能有兩個外部使用者存取原則。</span><span class="sxs-lookup"><span data-stu-id="dd162-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="dd162-128">全域原則會禁止使用者擁有公用立即訊息 (IM) 提供者，例如 Windows Live 帳戶的人通訊。</span><span class="sxs-lookup"><span data-stu-id="dd162-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="dd162-129">個別使用者原則，AllowPublicIMCommunication，可讓與公用 IM 提供者的通訊。</span><span class="sxs-lookup"><span data-stu-id="dd162-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="dd162-130">您可能也有兩位使用者： Ken Myer 與 Pilar Ackerman。</span><span class="sxs-lookup"><span data-stu-id="dd162-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="dd162-131">Ken Myer 已被指派個別使用者原則。</span><span class="sxs-lookup"><span data-stu-id="dd162-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="dd162-132">為 pilar Ackerman 尚未被指派每位使用者的原則;也就是說，她管理由全域外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="dd162-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="dd162-133">下表顯示哪些使用者 （如果有的話） 可以與彼此公用 IM 提供者：</span><span class="sxs-lookup"><span data-stu-id="dd162-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd162-134">原則設定</span><span class="sxs-lookup"><span data-stu-id="dd162-134">Policy Settings</span></span></th>
<th><span data-ttu-id="dd162-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="dd162-135">Ken Myer</span></span></th>
<th><span data-ttu-id="dd162-136">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="dd162-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd162-137">公用 IM 提供者的全域原則設定</span><span class="sxs-lookup"><span data-stu-id="dd162-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="dd162-138">否</span><span class="sxs-lookup"><span data-stu-id="dd162-138">No</span></span></p></td>
<td><p><span data-ttu-id="dd162-139">否</span><span class="sxs-lookup"><span data-stu-id="dd162-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd162-140">公用 IM 提供者的每一使用者原則設定</span><span class="sxs-lookup"><span data-stu-id="dd162-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="dd162-141">是</span><span class="sxs-lookup"><span data-stu-id="dd162-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd162-142">否</span><span class="sxs-lookup"><span data-stu-id="dd162-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd162-143">使用者可以與彼此公用 IM 提供者</span><span class="sxs-lookup"><span data-stu-id="dd162-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="dd162-144">是</span><span class="sxs-lookup"><span data-stu-id="dd162-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="dd162-145">否</span><span class="sxs-lookup"><span data-stu-id="dd162-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dd162-146">如您所見，Ken Myer 會允許與公用 IM 提供者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="dd162-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="dd162-147">這是因為中指派給他的每一使用者原則的設定會覆寫全域原則設定。</span><span class="sxs-lookup"><span data-stu-id="dd162-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="dd162-148">為 pilar Ackerman 無法與公用 IM 提供者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="dd162-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="dd162-149">這是因為她會受全域原則，並全域原則禁止這類通訊。</span><span class="sxs-lookup"><span data-stu-id="dd162-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="dd162-150">由 Office 365 支援人員，必須為您建立個別使用者原則。</span><span class="sxs-lookup"><span data-stu-id="dd162-150">Per-user policies must be created for you by Office 365 Support.</span></span> <span data-ttu-id="dd162-151">建立原則之後，您可以再指派這些使用者使用適當的**授與 Cs**指令程式 (例如， [Grant-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy))。</span><span class="sxs-lookup"><span data-stu-id="dd162-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="dd162-152">每一使用者原則很容易識別因為原則 Identity 一律為開頭標記**前置詞**。</span><span class="sxs-lookup"><span data-stu-id="dd162-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="dd162-153">例如：</span><span class="sxs-lookup"><span data-stu-id="dd162-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="dd162-154">回到開發早期 Lync Server 2010 的標記<STRONG>前置詞</STRONG>日期。</span><span class="sxs-lookup"><span data-stu-id="dd162-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="dd162-155">這些天內個別使用者原則已稱為<EM>標籤原則</EM>，並已識別的標記<STRONG>前置詞</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="dd162-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="dd162-156">這些原則現在更精確地稱為<EM>個別使用者原則</EM>，而且標籤範圍更精確地稱為<EM>每個使用者範圍</EM>。</span><span class="sxs-lookup"><span data-stu-id="dd162-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="dd162-157">不過，基於技術考量，已永遠不會變更標記<STRONG>前置詞</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="dd162-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="dd162-158">使用 Skype for Business Online 和 Windows PowerShell 時使用的另一個重要字詞是*租用戶*。</span><span class="sxs-lookup"><span data-stu-id="dd162-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="dd162-159">當您設定 「 Skype for Business Online 帳戶時，指派新部署的租用戶識別碼號碼，也就是類似這樣的全域唯一識別碼 (GUID):</span><span class="sxs-lookup"><span data-stu-id="dd162-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="dd162-160">Skype 商務 Online 指令程式的幾個要求您輸入的租用戶識別碼，每當您執行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dd162-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="dd162-161">您必須輸入的租用戶識別碼，即使您已登入，並只能有一個租用戶。</span><span class="sxs-lookup"><span data-stu-id="dd162-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="dd162-162">幸好，您不需要記下租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="dd162-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="dd162-163">您可以隨時擷取租用戶識別碼，藉由執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="dd162-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="dd162-164">當然，了解等全域範圍和個別使用者範圍 （或標籤範圍） 之間的差異是只一半。</span><span class="sxs-lookup"><span data-stu-id="dd162-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="dd162-165">務必要知道當 （或即使） 您可以使用這些範圍。</span><span class="sxs-lookup"><span data-stu-id="dd162-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="dd162-166">相同是身分識別和 tenant 參數，則為 true。</span><span class="sxs-lookup"><span data-stu-id="dd162-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="dd162-167">下列主題說明不同的 Skype for Business Online 指令程式如何使用身分識別、 範圍和 tenant 參數：</span><span class="sxs-lookup"><span data-stu-id="dd162-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="dd162-168">Skype 商務 Online 中使用全域範圍的指令程式</span><span class="sxs-lookup"><span data-stu-id="dd162-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="dd162-169">Skype 商務 Online 中使用全域範圍和標籤範圍的指令程式</span><span class="sxs-lookup"><span data-stu-id="dd162-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="dd162-170">Skype 商務 Online 中使用的使用者身分識別的指令程式</span><span class="sxs-lookup"><span data-stu-id="dd162-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="dd162-171">Skype 商務 Online 中使用的使用者身分識別和標籤範圍的指令程式</span><span class="sxs-lookup"><span data-stu-id="dd162-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="dd162-172">Skype 商務 Online 中使用 Tenant 參數的指令程式</span><span class="sxs-lookup"><span data-stu-id="dd162-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="dd162-173">Skype 商務 Online 中使用的會議提供者身分識別的指令程式</span><span class="sxs-lookup"><span data-stu-id="dd162-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="dd162-174">Skype 商務 Online 中不需要使用某個範圍或身分識別的指令程式</span><span class="sxs-lookup"><span data-stu-id="dd162-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

