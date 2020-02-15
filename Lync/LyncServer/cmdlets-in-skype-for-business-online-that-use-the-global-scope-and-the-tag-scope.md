---
title: Skype 商務 Online 中使用全域範圍和標籤範圍的指令程式
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
ms.openlocfilehash: 998201bf7772003c83ae27d56b3a238f9f0ca055
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001148"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="ba0f5-102">Skype 商務 Online 中使用全域範圍和標籤範圍的指令程式</span><span class="sxs-lookup"><span data-stu-id="ba0f5-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="ba0f5-103">Skype for Business Online，在*全域範圍*任一或*標記範圍*（或*個別使用者範圍*） 可以設定原則。</span><span class="sxs-lookup"><span data-stu-id="ba0f5-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="ba0f5-104">使用**Get-Cs** cmdlet 時，您不必指定範圍或身分識別。</span><span class="sxs-lookup"><span data-stu-id="ba0f5-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="ba0f5-105">如果您呼叫下列其中一個這些 cmdlet 不含任何參數，則會傳回所有相關的項目。</span><span class="sxs-lookup"><span data-stu-id="ba0f5-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="ba0f5-106">例如，此命令會傳回您所有外部存取原則的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="ba0f5-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="ba0f5-107">您必須包含只使用 Identity 參數或 Filter 參數，如果您想要限制傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="ba0f5-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="ba0f5-108">例如，若要傳回全域原則，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="ba0f5-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="ba0f5-109">若要傳回 identity 為"redmondaccesspolicy 指派 「 每一使用者原則，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="ba0f5-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="ba0f5-110">參照的每一使用者原則時, 是選用的標記<STRONG>前置詞</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="ba0f5-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="ba0f5-111">此語法，其中包含前置詞，也是有效的：</span><span class="sxs-lookup"><span data-stu-id="ba0f5-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="ba0f5-112">Get-csexternalaccesspolicy – Identity"tag: redmondaccesspolicy 指派 」</span><span class="sxs-lookup"><span data-stu-id="ba0f5-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="ba0f5-113">若要傳回的全域原則 （也就是所有個別使用者原則） 以外的所有原則，請使用此命令：</span><span class="sxs-lookup"><span data-stu-id="ba0f5-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="ba0f5-114">針對全域範圍和每個使用者 （標記） 範圍操作的下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ba0f5-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="ba0f5-115">[Get-csclientpolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ba0f5-115">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ba0f5-116">[Get-csconferencingpolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ba0f5-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ba0f5-117">[Get-csdialplan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ba0f5-117">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ba0f5-118">[Get-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ba0f5-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ba0f5-119">[Get-cshostedvoicemailpolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ba0f5-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ba0f5-120">[Get-cspresencepolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ba0f5-120">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="ba0f5-121">[Get-csvoicepolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ba0f5-121">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="ba0f5-122">儘管名稱為，撥號對應表是，具有相同的作用來說，原則。</span><span class="sxs-lookup"><span data-stu-id="ba0f5-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="ba0f5-123"><EM>撥號對應表</EM>的字詞會使用而不是，例如撥號原則，才能保留與舊版的 Lync Server 搭配使用的術語。</span><span class="sxs-lookup"><span data-stu-id="ba0f5-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="ba0f5-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ba0f5-124">See Also</span></span>


[<span data-ttu-id="ba0f5-125">身分識別、 範圍與 skype for Business Online 租用戶</span><span class="sxs-lookup"><span data-stu-id="ba0f5-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="ba0f5-126">[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="ba0f5-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

