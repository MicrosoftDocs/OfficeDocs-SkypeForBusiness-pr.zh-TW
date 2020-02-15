---
title: Skype 商務 Online 中使用全域範圍的指令程式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: f4a894c4a9c6e2913abb003c49094bc6d6868483
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001248"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="7d286-102">Skype 商務 Online 中使用全域範圍的指令程式</span><span class="sxs-lookup"><span data-stu-id="7d286-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="7d286-103">有多個的 Skype for Business Online 設定只會在*全域範圍*。</span><span class="sxs-lookup"><span data-stu-id="7d286-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="7d286-104">這表示套用至指派給該租用戶的所有使用者設定的單一集合。</span><span class="sxs-lookup"><span data-stu-id="7d286-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="7d286-105">（每個租用戶都有通用設定其專屬唯一集合）。當您使用全域範圍僅限於的指令程式時，Identity 參數是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="7d286-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="7d286-106">例如，若要擷取會議組態設定，您可以使用此命令：</span><span class="sxs-lookup"><span data-stu-id="7d286-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="7d286-107">或者，您可以省略 Identity 參數，並改為使用這個簡單的命令：</span><span class="sxs-lookup"><span data-stu-id="7d286-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="7d286-108">因為只有一個全域的會議組態設定集合，兩個命令會傳回完全相同的資訊。</span><span class="sxs-lookup"><span data-stu-id="7d286-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="7d286-109">使用下列其中一個**設定 Cs**指令程式時，也可以省略 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="7d286-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="7d286-110">這兩個命令是相同的：</span><span class="sxs-lookup"><span data-stu-id="7d286-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="7d286-111">兩個命令皆相同，因為根據預設，Windows PowerShell 將會修改全域集合如果您未包含 Identity 參數。</span><span class="sxs-lookup"><span data-stu-id="7d286-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="7d286-112">下列指令程式作業只會在全域範圍：</span><span class="sxs-lookup"><span data-stu-id="7d286-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="7d286-113">[Get-csimfilterconfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7d286-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7d286-114">[Get-csmeetingconfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7d286-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7d286-115">[Get-csprivacyconfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7d286-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7d286-116">[取得 CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7d286-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7d286-117">[取得 CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7d286-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7d286-118">[取得 CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7d286-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7d286-119">[取得 CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7d286-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7d286-120">[移除 CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7d286-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7d286-121">[Set-csmeetingconfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7d286-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="7d286-122">[Set-csprivacyconfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7d286-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="7d286-123">請注意，**移除 CsVoicePolicy**指令程式的異常的某個項目。</span><span class="sxs-lookup"><span data-stu-id="7d286-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="7d286-124">首先，此 cmdlet 會要求您加入 Identity 參數：</span><span class="sxs-lookup"><span data-stu-id="7d286-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="7d286-125">其次，**移除 CsVoicePolicy**指令程式不會實際刪除全域語音原則;Skype 商務 Online 不允許您刪除全域原則或設定值。</span><span class="sxs-lookup"><span data-stu-id="7d286-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="7d286-126">此 cmdlet 的作用為何是可讓您的全域語音原則中的所有屬性重都設為其預設值。</span><span class="sxs-lookup"><span data-stu-id="7d286-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="7d286-127">例如，根據預設，AllowCallForwarding 屬性設為 False。</span><span class="sxs-lookup"><span data-stu-id="7d286-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="7d286-128">不過，AllowCallForwarding 可能已修改，值立即設定為 True。</span><span class="sxs-lookup"><span data-stu-id="7d286-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="7d286-129">當您執行**移除 CsVoicePolicy**指令程式時，AllowCallForwarding 屬性就會還原成其預設值： False。</span><span class="sxs-lookup"><span data-stu-id="7d286-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="7d286-130">下表摘要說明此案例：</span><span class="sxs-lookup"><span data-stu-id="7d286-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d286-131">AllowCallForwarding 值</span><span class="sxs-lookup"><span data-stu-id="7d286-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="7d286-132">案例</span><span class="sxs-lookup"><span data-stu-id="7d286-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d286-133">False</span><span class="sxs-lookup"><span data-stu-id="7d286-133">False</span></span></p></td>
<td><p><span data-ttu-id="7d286-134">預設值</span><span class="sxs-lookup"><span data-stu-id="7d286-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d286-135">True</span><span class="sxs-lookup"><span data-stu-id="7d286-135">True</span></span></p></td>
<td><p><span data-ttu-id="7d286-136">之後已修改全域原則</span><span class="sxs-lookup"><span data-stu-id="7d286-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d286-137">False</span><span class="sxs-lookup"><span data-stu-id="7d286-137">False</span></span></p></td>
<td><p><span data-ttu-id="7d286-138">已<strong>移除 CsVoicePolicy</strong>之後執行指令程式</span><span class="sxs-lookup"><span data-stu-id="7d286-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="7d286-139">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7d286-139">See Also</span></span>


[<span data-ttu-id="7d286-140">身分識別、 範圍與 skype for Business Online 租用戶</span><span class="sxs-lookup"><span data-stu-id="7d286-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="7d286-141">[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="7d286-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

