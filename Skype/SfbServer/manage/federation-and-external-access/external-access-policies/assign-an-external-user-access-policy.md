---
title: 指派外部使用者存取原則
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果使用者已啟用商務用 Skype Server 的功能，您可以在商務用 Skype Server 控制台中設定 SIP 同盟、遠端使用者存取及公用立即訊息（IM）連線，方法是將適當的原則套用至特定的使用者。
ms.openlocfilehash: b87eb377b23063dbcdfd9562a99533da230a8f30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818324"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="37f4e-103">將外部使用者存取原則指派給商務用 Skype 啟用的使用者</span><span class="sxs-lookup"><span data-stu-id="37f4e-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="37f4e-104">如果使用者已啟用商務用 Skype Server 的功能，您可以在商務用 Skype Server 控制台中設定 SIP 同盟、遠端使用者存取及公用立即訊息（IM）連線，方法是將適當的原則套用至特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="37f4e-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="37f4e-105">例如，如果您建立了支援遠端使用者存取的原則，您必須先將其套用至使用者，才能讓使用者從遠端位置連線到商務用 Skype Server，並從遠端位置與內部使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="37f4e-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="37f4e-106">若要支援外部使用者存取，您必須針對您要支援的每個外部使用者存取類型啟用支援，然後設定適當的原則和其他選項來控制其用途。</span><span class="sxs-lookup"><span data-stu-id="37f4e-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="37f4e-107">如需詳細資訊，請參閱[管理商務用 Skype Server 的同盟和外部存取](../managing-federation-and-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="37f4e-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="37f4e-108">使用本主題中的程式，將先前建立的外部使用者存取原則套用至一或多個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="37f4e-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="37f4e-109">將外部使用者原則套用到使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="37f4e-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="37f4e-110">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="37f4e-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="37f4e-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="37f4e-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="37f4e-112">在左導覽列中，按一下 [使用者]\*\*\*\*，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="37f4e-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="37f4e-113">在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]\*\*\*\* 及 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="37f4e-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="37f4e-114">在 [在**外部存取原則\*\*\*\*編輯商務用 Skype 伺服器使用者**] 底下，選取您要套用的使用者原則。</span><span class="sxs-lookup"><span data-stu-id="37f4e-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="37f4e-115">[ \*\* \<自動>\*\* 設定] 會套用 [預設伺服器] 或 [全域原則設定]。</span><span class="sxs-lookup"><span data-stu-id="37f4e-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="37f4e-116">使用 Windows PowerShell Cmdlet 指派每個使用者的外部存取原則</span><span class="sxs-lookup"><span data-stu-id="37f4e-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="37f4e-117">您可以使用 Windows PowerShell 和 Grant CsExternalAccessPolicy Cmdlet 來指派每個使用者的外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="37f4e-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="37f4e-118">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="37f4e-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="37f4e-119">將每個使用者的外部存取原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="37f4e-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="37f4e-120">這個命令會將每個使用者的外部存取原則 RedmondExternalAccessPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="37f4e-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="37f4e-121">將每個使用者的外部存取原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="37f4e-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="37f4e-122">這個命令會將每個使用者的外部存取原則 USAExternalAccessPolicy 指派給在 Active Directory 中的美國組織單位中擁有帳戶的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="37f4e-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="37f4e-123">如需此命令中使用的 OU 參數的詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) Cmdlet 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="37f4e-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="37f4e-124">若要取消指派每個使用者的外部存取原則</span><span class="sxs-lookup"><span data-stu-id="37f4e-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="37f4e-125">這個命令會會先前指派給 Ken Myer 的任何每使用者外部存取原則。</span><span class="sxs-lookup"><span data-stu-id="37f4e-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="37f4e-126">未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。</span><span class="sxs-lookup"><span data-stu-id="37f4e-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="37f4e-127">網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="37f4e-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="37f4e-128">如需詳細資訊，請參閱[Grant CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="37f4e-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


