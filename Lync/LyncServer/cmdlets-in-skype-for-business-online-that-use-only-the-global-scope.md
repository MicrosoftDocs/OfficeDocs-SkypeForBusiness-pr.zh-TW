---
title: 商務用 Skype Online 的 Cmdlet 只使用全域範圍
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210e9116152ebe071ec81d2e0d48ff31b7c20a60
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "40975501"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="01c38-102">商務用 Skype Online 的 Cmdlet 只使用全域範圍</span><span class="sxs-lookup"><span data-stu-id="01c38-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="01c38-103">許多商務用 Skype Online 設定僅適用于*全域範圍*。</span><span class="sxs-lookup"><span data-stu-id="01c38-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="01c38-104">這表示有一個設定集合，這些設定會套用至指派給該租使用者的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="01c38-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="01c38-105">（每個租使用者都有自己獨特的全域設定集合）。當您使用限制在全域範圍的 Cmdlet 時，身分識別參數是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="01c38-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="01c38-106">例如，若要檢索會議設定，您可以使用此命令：</span><span class="sxs-lookup"><span data-stu-id="01c38-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="01c38-107">或者，您可以省略身分識別參數並改用這個更簡單的命令：</span><span class="sxs-lookup"><span data-stu-id="01c38-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="01c38-108">因為只有一個全域集合的會議設定，所以這兩個命令會傳回完全相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="01c38-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="01c38-109">使用其中一個**設定的 Cs** Cmdlet 時，也可以省略身分識別參數。</span><span class="sxs-lookup"><span data-stu-id="01c38-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="01c38-110">這兩個命令完全相同：</span><span class="sxs-lookup"><span data-stu-id="01c38-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="01c38-111">這兩個命令完全相同，因為如果您不包含身分識別參數，Windows PowerShell 就會修改全域集合。</span><span class="sxs-lookup"><span data-stu-id="01c38-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="01c38-112">下列 Cmdlet 只會在全域範圍中運作：</span><span class="sxs-lookup"><span data-stu-id="01c38-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="01c38-113">[CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01c38-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01c38-114">[CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01c38-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01c38-115">[CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01c38-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01c38-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01c38-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01c38-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01c38-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01c38-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01c38-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01c38-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01c38-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01c38-120">[移除-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01c38-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01c38-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01c38-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="01c38-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01c38-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="01c38-123">請注意， **CsVoicePolicy** Cmdlet 是一些異常的情況。</span><span class="sxs-lookup"><span data-stu-id="01c38-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="01c38-124">首先，這個 Cmdlet 需要您加入身分識別參數：</span><span class="sxs-lookup"><span data-stu-id="01c38-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="01c38-125">其次， **CsVoicePolicy** Cmdlet 不會實際刪除全域語音原則;商務用 Skype Online 不允許您刪除全域原則或配置設定。</span><span class="sxs-lookup"><span data-stu-id="01c38-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="01c38-126">Cmdlet 的用途是讓您將全域語音原則中的所有屬性重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="01c38-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="01c38-127">例如，根據預設，AllowCallForwarding 屬性會設定為 False。</span><span class="sxs-lookup"><span data-stu-id="01c38-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="01c38-128">不過，AllowCallForwarding 可能已修改，且值現在已設定為 True。</span><span class="sxs-lookup"><span data-stu-id="01c38-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="01c38-129">當您執行**CsVoicePolicy** Cmdlet 時，AllowCallForwarding 屬性會還原為預設值： False。</span><span class="sxs-lookup"><span data-stu-id="01c38-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="01c38-130">下表摘要說明這個案例：</span><span class="sxs-lookup"><span data-stu-id="01c38-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01c38-131">AllowCallForwarding 值</span><span class="sxs-lookup"><span data-stu-id="01c38-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="01c38-132">例子</span><span class="sxs-lookup"><span data-stu-id="01c38-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01c38-133">虛假</span><span class="sxs-lookup"><span data-stu-id="01c38-133">False</span></span></p></td>
<td><p><span data-ttu-id="01c38-134">預設值</span><span class="sxs-lookup"><span data-stu-id="01c38-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01c38-135">滿足</span><span class="sxs-lookup"><span data-stu-id="01c38-135">True</span></span></p></td>
<td><p><span data-ttu-id="01c38-136">在修改全域原則之後</span><span class="sxs-lookup"><span data-stu-id="01c38-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01c38-137">虛假</span><span class="sxs-lookup"><span data-stu-id="01c38-137">False</span></span></p></td>
<td><p><span data-ttu-id="01c38-138"><strong>CsVoicePolicy</strong> Cmdlet 執行之後</span><span class="sxs-lookup"><span data-stu-id="01c38-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="01c38-139">請參閱</span><span class="sxs-lookup"><span data-stu-id="01c38-139">See Also</span></span>


[<span data-ttu-id="01c38-140">商務用 Skype Online 中的身分識別、範圍和租使用者</span><span class="sxs-lookup"><span data-stu-id="01c38-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="01c38-141">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="01c38-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

