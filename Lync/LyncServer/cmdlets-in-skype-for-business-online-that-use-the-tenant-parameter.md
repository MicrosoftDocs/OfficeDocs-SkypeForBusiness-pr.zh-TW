---
title: 使用承租人參數的商務用 Skype Online 中的 Cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 352a33fcff5db306b62535c28fb4a2b2dd766bea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755039"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="75732-102">使用承租人參數的商務用 Skype Online 中的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="75732-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="75732-103">修改您的公用提供者設定時，您必須提供承租人身分識別;即使您只有一個承租人，也是如此。</span><span class="sxs-lookup"><span data-stu-id="75732-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="75732-104">例如，此命令會將 Windows Live 設定為您的使用者可與之通訊的唯一公開提供者：</span><span class="sxs-lookup"><span data-stu-id="75732-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="75732-105">幸運的是，每當您執行其中一個 Cmdlet 時，您不需要輸入承租人識別碼（例如，bf19b7db-6960-41e5-a139-2aa373474354）。</span><span class="sxs-lookup"><span data-stu-id="75732-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="75732-106">相反地，您可以執行[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) Cmdlet，將租使用者識別碼儲存在變數中，然後在呼叫另一個 Cmdlet 時使用該變數，以取得租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="75732-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="75732-107">例如：</span><span class="sxs-lookup"><span data-stu-id="75732-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="75732-108">或者，您可以在單一命令中執行這項作業，方法是檢索租使用者識別碼，然後將此值管線傳送至 CsTenantPublicProvider Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="75732-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="75732-109">呼叫**Get-CsTenant** Cmdlet 時，不需要指定租使用者識別碼。</span><span class="sxs-lookup"><span data-stu-id="75732-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="75732-110">此命令會傳回您租使用者的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="75732-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="75732-111">下列 Cmdlet 會接受租使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="75732-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="75732-112">不過，在這種情況下，此參數是選用的，而且不需要在呼叫 Cmdlet 時輸入。</span><span class="sxs-lookup"><span data-stu-id="75732-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="75732-113">相反地，Windows PowerShell 會根據您目前連線的商務用 Skype Online 租使用者，為您輸入承租人身分識別：</span><span class="sxs-lookup"><span data-stu-id="75732-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="75732-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="75732-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="75732-115">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="75732-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="75732-116">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="75732-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="75732-117">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="75732-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="75732-118">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="75732-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="75732-119">[CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="75732-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="75732-120">例如，您可以使用下列命令呼叫**CsTenantFederationConfiguration** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="75732-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="75732-121">您可以在呼叫 CsTenantFederationConfiguration 時包含租使用者參數，但這不是必要的：</span><span class="sxs-lookup"><span data-stu-id="75732-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="75732-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="75732-122">See Also</span></span>


[<span data-ttu-id="75732-123">商務用 Skype Online 中的身分識別、範圍和承租人</span><span class="sxs-lookup"><span data-stu-id="75732-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="75732-124">[商務用 Skype Online Cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="75732-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

