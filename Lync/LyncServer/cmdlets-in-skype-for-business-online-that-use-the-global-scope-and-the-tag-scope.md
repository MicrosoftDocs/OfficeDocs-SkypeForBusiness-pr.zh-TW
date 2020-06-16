---
title: 使用全域範圍及標記範圍的商務用 Skype Online 中的 Cmdlet
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
ms.openlocfilehash: c8063334f2cea6fcca768754197bacbd30869461
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755073"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="39122-102">使用全域範圍及標記範圍的商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="39122-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="39122-103">在商務用 Skype Online 中，原則可以設定為*全域範圍*或*標記範圍*（或個別*使用者範圍*）。</span><span class="sxs-lookup"><span data-stu-id="39122-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="39122-104">使用**Cs** Cmdlet 時，您不需要指定範圍或身分識別。</span><span class="sxs-lookup"><span data-stu-id="39122-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="39122-105">如果您呼叫其中一個不含任何參數的 Cmdlet，將會傳回所有相關的專案。</span><span class="sxs-lookup"><span data-stu-id="39122-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="39122-106">例如，下列命令會傳回所有外部存取原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="39122-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="39122-107">如果您想要限制傳回的資料，您只需要包含 Identity 參數或 Filter 參數。</span><span class="sxs-lookup"><span data-stu-id="39122-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="39122-108">例如，若只要傳回全域原則，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="39122-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="39122-109">若要傳回身分識別為 "RedmondAccessPolicy" 的個別使用者原則，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="39122-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="39122-110">參照個別使用者原則時，標記<STRONG>首碼</STRONG>是選用的。</span><span class="sxs-lookup"><span data-stu-id="39122-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="39122-111">這種包含首碼的語法也是有效的：</span><span class="sxs-lookup"><span data-stu-id="39122-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="39122-112">Get-CsExternalAccessPolicy –身分識別 "tag： RedmondAccessPolicy"</span><span class="sxs-lookup"><span data-stu-id="39122-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="39122-113">若要傳回除全域原則以外的所有原則（也就是說，所有的個別使用者原則），請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="39122-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="39122-114">下列 Cmdlet 同時針對全域範圍和個別使用者（標記）範圍執行：</span><span class="sxs-lookup"><span data-stu-id="39122-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="39122-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="39122-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="39122-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="39122-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="39122-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="39122-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="39122-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="39122-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="39122-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="39122-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="39122-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="39122-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="39122-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="39122-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="39122-122">不論名稱為何，撥號對應表都是以功能為依據的原則。</span><span class="sxs-lookup"><span data-stu-id="39122-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="39122-123">使用<EM>撥號</EM>對應表代替（例如，撥號原則）以保留舊版 Lync Server 所使用的詞彙。</span><span class="sxs-lookup"><span data-stu-id="39122-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="39122-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="39122-124">See Also</span></span>


[<span data-ttu-id="39122-125">商務用 Skype Online 中的身分識別、範圍和承租人</span><span class="sxs-lookup"><span data-stu-id="39122-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="39122-126">[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="39122-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

