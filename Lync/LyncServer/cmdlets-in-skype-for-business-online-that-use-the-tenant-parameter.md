---
title: Skype 商務 Online 中使用 Tenant 參數的指令程式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 121133ce163b73bd0ddf49faa1db03ae352056d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42000928"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="40ce7-102">Skype 商務 Online 中使用 Tenant 參數的指令程式</span><span class="sxs-lookup"><span data-stu-id="40ce7-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="40ce7-103">時修改您的公用提供者的設定，您一律需要提供的租用戶身分識別，;即使您只需要單一租用戶，這是，則為 true。</span><span class="sxs-lookup"><span data-stu-id="40ce7-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="40ce7-104">例如，此命令會設定 Windows Live 做為您的使用者可以與彼此只將公用提供者：</span><span class="sxs-lookup"><span data-stu-id="40ce7-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="40ce7-105">幸好，您不需要輸入租用戶識別碼 (例如，bf19b7db-6960-41e5-a139-2aa373474354) 每次您執行下列其中一個這些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="40ce7-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="40ce7-106">相反地，您可以擷取租用戶識別碼執行[Get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet，將租用戶識別碼儲存在變數中，當您呼叫下列其中一個其他指令程式，然後使用該變數。</span><span class="sxs-lookup"><span data-stu-id="40ce7-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="40ce7-107">例如：</span><span class="sxs-lookup"><span data-stu-id="40ce7-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="40ce7-108">或者，您可以在單一命令來擷取租用戶識別碼，並再將輸入所得數值與設定 CsTenantPublicProvider 指令程式：</span><span class="sxs-lookup"><span data-stu-id="40ce7-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="40ce7-109">您不需要呼叫**Get-cstenant**指令程式時指定的租用戶識別碼。</span><span class="sxs-lookup"><span data-stu-id="40ce7-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="40ce7-110">此命令會傳回您的租用戶的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="40ce7-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="40ce7-111">下列指令程式接受的租用戶身分識別。</span><span class="sxs-lookup"><span data-stu-id="40ce7-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="40ce7-112">不過，在這些情況下，參數是選擇性的而不需輸入呼叫指令程式時。</span><span class="sxs-lookup"><span data-stu-id="40ce7-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="40ce7-113">相反地，Windows PowerShell 將有效地為您根據 Skype for Business Online 目前正連線至的租用戶輸入租用戶識別碼：</span><span class="sxs-lookup"><span data-stu-id="40ce7-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="40ce7-114">[Get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="40ce7-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="40ce7-115">[設定 CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="40ce7-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="40ce7-116">[設定 CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="40ce7-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="40ce7-117">[取得 CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="40ce7-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="40ce7-118">[取得 CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="40ce7-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="40ce7-119">[取得 CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="40ce7-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="40ce7-120">例如，可以呼叫的**Get-CsTenantFederationConfiguration** cmdlet，使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="40ce7-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="40ce7-121">雖然並非必要，您可以在呼叫 Get CsTenantFederationConfiguration 時包含 Tenant 參數：</span><span class="sxs-lookup"><span data-stu-id="40ce7-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="40ce7-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="40ce7-122">See Also</span></span>


[<span data-ttu-id="40ce7-123">身分識別、 範圍與 skype for Business Online 租用戶</span><span class="sxs-lookup"><span data-stu-id="40ce7-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="40ce7-124">[Skype 商務 Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="40ce7-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

