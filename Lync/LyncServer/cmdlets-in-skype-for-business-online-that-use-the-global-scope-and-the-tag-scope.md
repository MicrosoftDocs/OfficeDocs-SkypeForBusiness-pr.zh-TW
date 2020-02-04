---
title: 商務用 Skype Online 中使用全域範圍和標籤範圍的 Cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 04eb5f71a0092452eb8b24fa9acf53d46fb3bcd5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728093"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="783e4-102">商務用 Skype Online 中使用全域範圍和標籤範圍的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="783e4-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="783e4-103">在商務用 Skype Online 中，原則可以在*全域範圍*或標籤*範圍*（或*針對每個使用者的範圍*）進行設定。</span><span class="sxs-lookup"><span data-stu-id="783e4-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="783e4-104">使用**取得 Cs** Cmdlet 時，您不需要指定範圍或身分識別。</span><span class="sxs-lookup"><span data-stu-id="783e4-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="783e4-105">如果您呼叫其中一個不含任何參數的 Cmdlet，則會傳回所有相關專案。</span><span class="sxs-lookup"><span data-stu-id="783e4-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="783e4-106">例如，這個命令會傳回所有外部存取原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="783e4-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="783e4-107">如果您想要限制傳回的資料，必須只包含身分識別參數或 Filter 參數。</span><span class="sxs-lookup"><span data-stu-id="783e4-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="783e4-108">例如，若要只傳回全域原則，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="783e4-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="783e4-109">若要傳回具有 [RedmondAccessPolicy] 身分識別的每個使用者原則，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="783e4-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="783e4-110">參照每個使用者的原則時，標記<STRONG>首碼</STRONG>是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="783e4-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="783e4-111">此語法（包含首碼）也有效：</span><span class="sxs-lookup"><span data-stu-id="783e4-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="783e4-112">CsExternalAccessPolicy –身分識別 "tag： RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="783e4-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="783e4-113">若要傳回除全域原則以外的所有原則（也就是每個使用者的原則），請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="783e4-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="783e4-114">下列 Cmdlet 會針對全域範圍和每個使用者（tag）範圍執行：</span><span class="sxs-lookup"><span data-stu-id="783e4-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="783e4-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="783e4-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="783e4-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="783e4-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="783e4-117">[CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="783e4-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="783e4-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="783e4-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="783e4-119">[CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="783e4-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="783e4-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="783e4-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="783e4-121">[CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="783e4-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="783e4-122">雖然名稱和撥號方案是，但在功能上說，原則。</span><span class="sxs-lookup"><span data-stu-id="783e4-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="783e4-123">使用「<EM>撥號」方案</EM>（例如撥號原則）來保留舊版 Lync Server 所使用的詞彙。</span><span class="sxs-lookup"><span data-stu-id="783e4-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="783e4-124">請參閱</span><span class="sxs-lookup"><span data-stu-id="783e4-124">See Also</span></span>


[<span data-ttu-id="783e4-125">商務用 Skype Online 中的身分識別、範圍和租使用者</span><span class="sxs-lookup"><span data-stu-id="783e4-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="783e4-126">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="783e4-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

