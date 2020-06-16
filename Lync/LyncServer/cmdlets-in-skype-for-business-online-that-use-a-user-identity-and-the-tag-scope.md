---
title: 使用使用者身分識別及標記範圍的商務用 Skype Online 中的 Cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9adf86a6ec6d2bd859411005dcc67b0dcbe09c7f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755115"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="708d1-102">使用使用者身分識別及標記範圍的商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="708d1-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="708d1-103">**授與 Cs 指令程式**（用來指派原則給使用者）需要兩個識別碼：使用者身分識別（身分識別參數）和個別使用者原則的身分識別（PolicyName 參數）。</span><span class="sxs-lookup"><span data-stu-id="708d1-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="708d1-104">例如，若要將語音原則 RedmondVoicePolicy 指派給使用者 Ken Myer，您可以使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="708d1-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="708d1-105">將原則指派給使用者時，有兩個事項需要謹記。</span><span class="sxs-lookup"><span data-stu-id="708d1-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="708d1-106">首先，只能指派每個使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="708d1-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="708d1-107">您無法將全域原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="708d1-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="708d1-108">例如，此命令將會失敗：</span><span class="sxs-lookup"><span data-stu-id="708d1-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="708d1-109">因為不需要指派全域原則，所以此命令失敗。</span><span class="sxs-lookup"><span data-stu-id="708d1-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="708d1-110">如果您想要使用通用原則來管理使用者，請務必確定您沒有為使用者指派每個使用者原則。</span><span class="sxs-lookup"><span data-stu-id="708d1-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="708d1-111">若使用者未指派任何個別使用者原則，則會使用全域原則來管理使用者。</span><span class="sxs-lookup"><span data-stu-id="708d1-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="708d1-112">如果使用者先前已被指派個別使用者原則，而您想要取消指派該原則，而使用者卻是由全域原則所管理，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="708d1-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="708d1-113">在此情況下，您會先使用下列語法來 unassigns 個別使用者原則，方法是授與該使用者的 null 原則：</span><span class="sxs-lookup"><span data-stu-id="708d1-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="708d1-114">Grant-CsVoicePolicy –身分識別 "Ken Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="708d1-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="708d1-115">其次，請記住每一使用者原則都是在標籤範圍內建立的。</span><span class="sxs-lookup"><span data-stu-id="708d1-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="708d1-116">不過，您可以在指定原則名稱時省略標記**首碼**。</span><span class="sxs-lookup"><span data-stu-id="708d1-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="708d1-117">這兩個命令相同：</span><span class="sxs-lookup"><span data-stu-id="708d1-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="708d1-118">如果您想要傳回所有個別使用者原則的身分識別（或至少，所有指定類型的個別使用者原則，例如語音原則），請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="708d1-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="708d1-119">下列 Cmdlet 會同時使用使用者身分識別及標籤範圍：</span><span class="sxs-lookup"><span data-stu-id="708d1-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="708d1-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="708d1-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="708d1-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="708d1-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="708d1-122">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="708d1-122">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="708d1-123">[授與 Get-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="708d1-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="708d1-124">[授與 CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="708d1-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="708d1-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="708d1-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="708d1-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="708d1-126">See Also</span></span>


[<span data-ttu-id="708d1-127">商務用 Skype Online 中的身分識別、範圍和承租人</span><span class="sxs-lookup"><span data-stu-id="708d1-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="708d1-128">[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="708d1-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

