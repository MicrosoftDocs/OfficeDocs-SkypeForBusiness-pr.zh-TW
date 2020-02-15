---
title: Skype 商務 Online 中使用的使用者身分識別和標籤範圍的指令程式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: a5319d527c859d239cd58eb5561d82a0b47a322e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42001438"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="5fe47-102">Skype 商務 Online 中使用的使用者身分識別和標籤範圍的指令程式</span><span class="sxs-lookup"><span data-stu-id="5fe47-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="5fe47-103">**授與 Cs** cmdlet （用來將原則指派給使用者） 需要兩個識別碼： 使用者身分識別 （Identity 參數） 與個別使用者原則 （PolicyName 參數） 的身分識別。</span><span class="sxs-lookup"><span data-stu-id="5fe47-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="5fe47-104">例如，若要將語音原則 RedmondVoicePolicy，指派給使用者 Ken Myer，您會使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="5fe47-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="5fe47-105">有兩個時將原則指派給使用者，請記住的事項。</span><span class="sxs-lookup"><span data-stu-id="5fe47-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="5fe47-106">首先，只有每位使用者可以將原則指派。</span><span class="sxs-lookup"><span data-stu-id="5fe47-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="5fe47-107">您無法將全域原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="5fe47-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="5fe47-108">例如，此命令將會失敗：</span><span class="sxs-lookup"><span data-stu-id="5fe47-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="5fe47-109">此命令失敗，因為不需要指派全域原則。</span><span class="sxs-lookup"><span data-stu-id="5fe47-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="5fe47-110">如果您想要使用的全域原則來管理使用者，只要務必，您沒有指派該使用者的個別使用者原則。</span><span class="sxs-lookup"><span data-stu-id="5fe47-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="5fe47-111">如果沒有個別使用者原則已指派給使用者，使用者將會自動管理所使用的全域原則。</span><span class="sxs-lookup"><span data-stu-id="5fe47-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="5fe47-112">如果使用者先前已指派個別使用者原則，以及您想要取消指派該原則，並將改為由全域原則的使用者？</span><span class="sxs-lookup"><span data-stu-id="5fe47-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="5fe47-113">在此情況下，您將先使用下列語法，unassigns 個別使用者原則所授與該使用者的 null 原則：</span><span class="sxs-lookup"><span data-stu-id="5fe47-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="5fe47-114">Grant-csvoicepolicy – Identity"Ken Myer"– PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="5fe47-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="5fe47-115">其次，請記住，在標記的範圍內建立個別使用者原則。</span><span class="sxs-lookup"><span data-stu-id="5fe47-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="5fe47-116">不過，您可以省略標記**前置詞**時指定原則名稱。</span><span class="sxs-lookup"><span data-stu-id="5fe47-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="5fe47-117">這兩個命令是相同的：</span><span class="sxs-lookup"><span data-stu-id="5fe47-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="5fe47-118">如果您想要傳回所有您個別使用者原則的身分識別 （或所有的個別使用者原則的最少，指定類型，例如語音原則），使用類似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="5fe47-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="5fe47-119">下列指令程式將使用這兩個使用者的身分識別和標籤範圍：</span><span class="sxs-lookup"><span data-stu-id="5fe47-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="5fe47-120">[Grant-csclientpolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5fe47-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5fe47-121">[Grant-csconferencingpolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5fe47-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5fe47-122">[Grant-csdialplan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5fe47-122">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5fe47-123">[Grant-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5fe47-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5fe47-124">[授與 CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5fe47-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5fe47-125">[Grant-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5fe47-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="5fe47-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5fe47-126">See Also</span></span>


[<span data-ttu-id="5fe47-127">身分識別、 範圍與 skype for Business Online 租用戶</span><span class="sxs-lookup"><span data-stu-id="5fe47-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="5fe47-128">[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5fe47-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

