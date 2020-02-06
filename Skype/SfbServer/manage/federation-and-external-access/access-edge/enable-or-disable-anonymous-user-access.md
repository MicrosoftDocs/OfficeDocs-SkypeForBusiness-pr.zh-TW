---
title: 啟用或停用匿名使用者存取
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
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
description: ''
ms.openlocfilehash: 40b365f25abccc05a5eb5156e1c7d79106a7537c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818404"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="765f4-102">在商務用 Skype Server 中啟用或停用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="765f4-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="765f4-103">匿名使用者是在組織的 Active Directory 網域服務或受支援的聯盟網域中沒有使用者帳戶的使用者，但在內部部署會議中可以受邀參與遠端參與。</span><span class="sxs-lookup"><span data-stu-id="765f4-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="765f4-104">透過允許匿名參與會議，您可以啟用匿名使用者（也就是僅透過會議或會議金鑰驗證身分識別的使用者）加入會議。</span><span class="sxs-lookup"><span data-stu-id="765f4-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="765f4-105">允許匿名參與需要為您的組織啟用。</span><span class="sxs-lookup"><span data-stu-id="765f4-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="765f4-106">如果您稍後想要暫時或永久避免匿名使用者的存取權，您可以針對您的組織停用它。</span><span class="sxs-lookup"><span data-stu-id="765f4-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="765f4-107">您可以使用本節中的程式來啟用或停用您組織的匿名使用者存取權。</span><span class="sxs-lookup"><span data-stu-id="765f4-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="765f4-108">透過針對您的組織啟用匿名使用者存取，您只會指定執行存取邊緣服務的伺服器支援由匿名使用者進行存取。</span><span class="sxs-lookup"><span data-stu-id="765f4-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="765f4-109">匿名使用者無法參與貴組織中的任何會議，除非您也設定了至少一個會議原則，並將它套用至一或多個使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="765f4-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="765f4-110">只有指派會議原則且設定為支援匿名使用者的使用者，才能邀請匿名使用者加入會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="765f4-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="765f4-111">如需設定會議原則以支援邀請匿名使用者的詳細資料，請參閱[管理會議原則](../../conferencing/conferencing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="765f4-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="765f4-112">若要啟用或停用您組織的匿名使用者存取權</span><span class="sxs-lookup"><span data-stu-id="765f4-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="765f4-113">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="765f4-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="765f4-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="765f4-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="765f4-115">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。</span><span class="sxs-lookup"><span data-stu-id="765f4-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="765f4-116">在 [**存取邊緣**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="765f4-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="765f4-117">在 [**編輯存取邊緣**設定] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="765f4-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="765f4-118">若要為您的組織啟用匿名使用者存取，請選取 [**啟用與匿名使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="765f4-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="765f4-119">若要停用您組織的匿名使用者存取，請清除 [**啟用與匿名使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="765f4-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="765f4-120">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="765f4-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="765f4-121">使用 Windows PowerShell Cmdlet 來啟用或停用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="765f4-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="765f4-122">您可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** Cmdlet 來管理匿名使用者存取。</span><span class="sxs-lookup"><span data-stu-id="765f4-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="765f4-123">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="765f4-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="765f4-124">啟用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="765f4-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="765f4-125">若要啟用匿名使用者存取，請將**AllowAnonymousUsers**屬性的值設定為 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="765f4-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="765f4-126">若要停用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="765f4-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="765f4-127">若要停用匿名使用者存取，請將**AllowAnonymousUsers**屬性的值設定為 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="765f4-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="765f4-128">請參閱</span><span class="sxs-lookup"><span data-stu-id="765f4-128">See Also</span></span>

[<span data-ttu-id="765f4-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="765f4-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
