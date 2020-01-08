---
title: 商務用 Skype Online 中使用租使用者參數的 Cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd58e375bcacfcb18cbc21e6ac352b8d98b56661
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "40975942"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="60a4c-102">商務用 Skype Online 中使用租使用者參數的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="60a4c-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="60a4c-103">修改公用提供者設定時，您必須提供租使用者身分識別;即使您只有單一租使用者，也是如此。</span><span class="sxs-lookup"><span data-stu-id="60a4c-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="60a4c-104">例如，這個命令會將 Windows Live 設為您的使用者可與之通訊的唯一公用提供者：</span><span class="sxs-lookup"><span data-stu-id="60a4c-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="60a4c-105">幸運的是，您不需要在每次執行其中一個 Cmdlet 時輸入租使用者識別碼（例如，bf19b7db-6960-41e5-a139-2aa373474354）。</span><span class="sxs-lookup"><span data-stu-id="60a4c-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="60a4c-106">相反地，您可以執行[CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) Cmdlet、儲存變數中的租使用者識別碼，然後在您呼叫其中一個其他 Cmdlet 時使用該變數，以取得租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="60a4c-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="60a4c-107">例如：</span><span class="sxs-lookup"><span data-stu-id="60a4c-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="60a4c-108">或者，您也可以在單一命令中執行這項操作，方法是檢索租使用者識別碼，然後將該值 CsTenantPublicProvider Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="60a4c-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="60a4c-109">在呼叫**CsTenant** Cmdlet 時，您不需要指定租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="60a4c-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="60a4c-110">這個命令會傳回您租使用者的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="60a4c-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="60a4c-111">下列 Cmdlet 接受租使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="60a4c-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="60a4c-112">不過，在這些情況下，參數是選擇性的，而且不需要在呼叫 Cmdlet 時輸入。</span><span class="sxs-lookup"><span data-stu-id="60a4c-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="60a4c-113">相反地，Windows PowerShell 會根據您目前連線至的商務用 Skype Online 租使用者，有效地輸入您的租使用者身分識別：</span><span class="sxs-lookup"><span data-stu-id="60a4c-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="60a4c-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="60a4c-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="60a4c-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="60a4c-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="60a4c-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="60a4c-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="60a4c-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="60a4c-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="60a4c-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="60a4c-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="60a4c-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="60a4c-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="60a4c-120">例如，您可以使用此命令呼叫**CsTenantFederationConfiguration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="60a4c-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="60a4c-121">雖然不必要，但您可以在呼叫 CsTenantFederationConfiguration 時包含租使用者參數：</span><span class="sxs-lookup"><span data-stu-id="60a4c-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="60a4c-122">請參閱</span><span class="sxs-lookup"><span data-stu-id="60a4c-122">See Also</span></span>


[<span data-ttu-id="60a4c-123">商務用 Skype Online 中的身分識別、範圍和租使用者</span><span class="sxs-lookup"><span data-stu-id="60a4c-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="60a4c-124">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="60a4c-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

