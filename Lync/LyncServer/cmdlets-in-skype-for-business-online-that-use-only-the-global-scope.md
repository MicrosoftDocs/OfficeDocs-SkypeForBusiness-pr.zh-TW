---
title: 僅使用全域範圍之商務用 Skype Online 中的 Cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b97f3c8d9ca7dda0b96db211192350184cbf27b1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755095"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="58490-102">僅使用全域範圍之商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="58490-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="58490-103">您可以在*全域範圍內*使用許多商務用 Skype Online 設定。</span><span class="sxs-lookup"><span data-stu-id="58490-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="58490-104">這表示有單一的設定集合，套用至指派給該租使用者的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="58490-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="58490-105">（每個租使用者都有自己的唯一全域設定集合。）當您使用限制為全域範圍的指令程式時，Identity 參數是選用的。</span><span class="sxs-lookup"><span data-stu-id="58490-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="58490-106">例如，若要檢索會議設定設定，您可以使用此命令：</span><span class="sxs-lookup"><span data-stu-id="58490-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="58490-107">或者，您可以省略 Identity 參數，而改為使用這個較簡單的命令：</span><span class="sxs-lookup"><span data-stu-id="58490-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="58490-108">因為只有一個全域集合的會議設定，所以這兩個命令會傳回完全相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="58490-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="58490-109">使用其中一個 a **Cs** Cmdlet 時，也可以省略 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="58490-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="58490-110">這兩個命令相同：</span><span class="sxs-lookup"><span data-stu-id="58490-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="58490-111">這兩個命令是相同的，因為根據預設，Windows PowerShell 會在未包含 Identity 參數時修改全域集合。</span><span class="sxs-lookup"><span data-stu-id="58490-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="58490-112">下列 Cmdlet 只會在全域範圍內運作：</span><span class="sxs-lookup"><span data-stu-id="58490-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="58490-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58490-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="58490-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58490-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="58490-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58490-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="58490-116">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58490-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="58490-117">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58490-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="58490-118">[CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58490-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="58490-119">[CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58490-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="58490-120">[Remove-Set-csvoicepolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58490-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="58490-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58490-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="58490-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58490-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="58490-123">請注意， **set-csvoicepolicy** Cmdlet 是一個反常情況。</span><span class="sxs-lookup"><span data-stu-id="58490-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="58490-124">首先，此 Cmdlet 必須包含 Identity 參數：</span><span class="sxs-lookup"><span data-stu-id="58490-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="58490-125">其次， **set-csvoicepolicy 指令程式**實際上不會刪除通用語音原則;商務用 Skype Online 不允許您刪除全域原則或設定設定。</span><span class="sxs-lookup"><span data-stu-id="58490-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="58490-126">Cmdlet 的作用是讓您將全域語音原則中的所有屬性重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="58490-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="58490-127">例如，根據預設，AllowCallForwarding 屬性會設定為 False。</span><span class="sxs-lookup"><span data-stu-id="58490-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="58490-128">不過，AllowCallForwarding 可能已修改，但現在值設定為 True。</span><span class="sxs-lookup"><span data-stu-id="58490-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="58490-129">當您執行**set-csvoicepolicy** Cmdlet 時，AllowCallForwarding 屬性會回復成其預設值： False。</span><span class="sxs-lookup"><span data-stu-id="58490-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="58490-130">下表摘要說明此案例：</span><span class="sxs-lookup"><span data-stu-id="58490-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58490-131">AllowCallForwarding 值</span><span class="sxs-lookup"><span data-stu-id="58490-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="58490-132">案例</span><span class="sxs-lookup"><span data-stu-id="58490-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58490-133">False</span><span class="sxs-lookup"><span data-stu-id="58490-133">False</span></span></p></td>
<td><p><span data-ttu-id="58490-134">預設值</span><span class="sxs-lookup"><span data-stu-id="58490-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58490-135">True</span><span class="sxs-lookup"><span data-stu-id="58490-135">True</span></span></p></td>
<td><p><span data-ttu-id="58490-136">在修改全域原則之後</span><span class="sxs-lookup"><span data-stu-id="58490-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58490-137">False</span><span class="sxs-lookup"><span data-stu-id="58490-137">False</span></span></p></td>
<td><p><span data-ttu-id="58490-138"><strong>Set-csvoicepolicy</strong> Cmdlet 已執行之後</span><span class="sxs-lookup"><span data-stu-id="58490-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="58490-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="58490-139">See Also</span></span>


[<span data-ttu-id="58490-140">商務用 Skype Online 中的身分識別、範圍和承租人</span><span class="sxs-lookup"><span data-stu-id="58490-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="58490-141">[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="58490-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

