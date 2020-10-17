---
title: 使用全域範圍及標記範圍的商務用 Skype Online 中的 Cmdlet
description: 在商務用 Skype Online 中使用全域範圍及標記範圍的 Cmdlet。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba89ebe7322159027c5de765117afd366cb3dc23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545619"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="c88e3-103">使用全域範圍及標記範圍的商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c88e3-103">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="c88e3-104">在商務用 Skype Online 中，可設定 *全域範圍* 或標籤 *範圍* (或 *每位使用者範圍*) 的原則。</span><span class="sxs-lookup"><span data-stu-id="c88e3-104">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="c88e3-105">使用 **Cs** Cmdlet 時，您不需要指定範圍或身分識別。</span><span class="sxs-lookup"><span data-stu-id="c88e3-105">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="c88e3-106">如果您呼叫其中一個不含任何參數的 Cmdlet，將會傳回所有相關的專案。</span><span class="sxs-lookup"><span data-stu-id="c88e3-106">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="c88e3-107">例如，下列命令會傳回所有外部存取原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="c88e3-107">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="c88e3-108">如果您想要限制傳回的資料，您只需要包含 Identity 參數或 Filter 參數。</span><span class="sxs-lookup"><span data-stu-id="c88e3-108">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="c88e3-109">例如，若只要傳回全域原則，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="c88e3-109">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="c88e3-110">若要傳回身分識別為 "RedmondAccessPolicy" 的個別使用者原則，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="c88e3-110">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="c88e3-111">參照個別使用者原則時，標記 <STRONG>首碼</STRONG> 是選用的。</span><span class="sxs-lookup"><span data-stu-id="c88e3-111">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="c88e3-112">這種包含首碼的語法也是有效的：</span><span class="sxs-lookup"><span data-stu-id="c88e3-112">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="c88e3-113">Get-CsExternalAccessPolicy –身分識別 "tag： RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="c88e3-113">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="c88e3-114">若要傳回除全域原則以外的所有原則 (也就是說，所有的個別使用者原則) ，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="c88e3-114">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="c88e3-115">下列 Cmdlet 針對全域範圍和個別使用者 (標籤) 範圍執行：</span><span class="sxs-lookup"><span data-stu-id="c88e3-115">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="c88e3-116">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="c88e3-116">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="c88e3-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="c88e3-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="c88e3-118">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="c88e3-118">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="c88e3-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="c88e3-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="c88e3-120">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="c88e3-120">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="c88e3-121">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="c88e3-121">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="c88e3-122">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="c88e3-122">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="c88e3-123">不論名稱為何，撥號對應表都是以功能為依據的原則。</span><span class="sxs-lookup"><span data-stu-id="c88e3-123">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="c88e3-124">使用 <EM>撥號</EM> 對應表代替（例如，撥號原則）以保留舊版 Lync Server 所使用的詞彙。</span><span class="sxs-lookup"><span data-stu-id="c88e3-124">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="c88e3-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c88e3-125">See Also</span></span>


[<span data-ttu-id="c88e3-126">商務用 Skype Online 中的身分識別、範圍和承租人</span><span class="sxs-lookup"><span data-stu-id="c88e3-126">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="c88e3-127">[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="c88e3-127">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

