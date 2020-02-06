---
title: 啟用或停用遠端使用者存取
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: 如果您為遠端使用者啟用遠端使用者存取，支援的遠端使用者透過網際網路連線，而且不需要使用 VPN 連線，就能使用商務用 Skype 伺服器與內部使用者共同作業。
ms.openlocfilehash: b562dbe7a849ca4266a45303008ff9081903658d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818374"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="3092f-103">在商務用 Skype Server 中啟用或停用遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="3092f-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="3092f-104">遠端使用者是組織內擁有持久 Active Directory 身分識別的使用者。</span><span class="sxs-lookup"><span data-stu-id="3092f-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="3092f-105">當遠端使用者未連線到貴組織的網路時，您可以使用虛擬私人網路（VPN），從您的網路外部登入商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3092f-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="3092f-106">遠端使用者包括在家中或在路上以及其他遠端工作人員（例如受信任的供應商，即已獲授與企業認證的人員）工作的員工。</span><span class="sxs-lookup"><span data-stu-id="3092f-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="3092f-107">如果您為遠端使用者啟用遠端使用者存取，支援的遠端使用者透過網際網路連線，而且不需要使用 VPN 連線，就能使用商務用 Skype 伺服器與內部使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="3092f-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="3092f-108">若要支援遠端使用者存取，您必須啟用遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="3092f-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="3092f-109">當您啟用遠端使用者存取時，就會為您的整個組織啟用此許可權。</span><span class="sxs-lookup"><span data-stu-id="3092f-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="3092f-110">如果您稍後想要暫時或永久避免遠端使用者存取，您可以針對您的組織停用它。</span><span class="sxs-lookup"><span data-stu-id="3092f-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="3092f-111">使用本節中的程式來啟用或停用貴組織的遠端使用者存取權。</span><span class="sxs-lookup"><span data-stu-id="3092f-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="3092f-112">啟用遠端使用者存取只會指定執行 Access Edge 服務的伺服器支援與遠端使用者的通訊，但遠端使用者無法參與立即訊息（IM）或組織中的會議，除非您在此設定至少一個管理遠端使用者存取使用的原則。</span><span class="sxs-lookup"><span data-stu-id="3092f-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="3092f-113">在一個策略層級套用的商務用 Skype 伺服器原則設定，可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="3092f-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="3092f-114">商務用 Skype Server 原則優先順序為：使用者原則（最具影響力）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。</span><span class="sxs-lookup"><span data-stu-id="3092f-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="3092f-115">這表示原則設定越接近策略設定的物件，就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="3092f-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="3092f-116">如需有關設定遠端使用者存取的原則的詳細資訊，請參閱[在商務用 Skype Server 中設定控制遠端使用者存取權的原則](../external-access-policies/configure-policies-to-control-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="3092f-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="3092f-117">若要啟用或停用貴組織的遠端使用者存取權</span><span class="sxs-lookup"><span data-stu-id="3092f-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="3092f-118">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3092f-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3092f-119">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="3092f-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3092f-120">在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [**存取邊緣**設定]。</span><span class="sxs-lookup"><span data-stu-id="3092f-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="3092f-121">在 [**存取邊緣**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="3092f-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3092f-122">在 [**編輯存取邊緣**設定] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="3092f-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="3092f-123">若要為您的組織啟用遠端使用者存取，請選取 [**啟用遠端使用者存取權**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3092f-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="3092f-124">若要停用您組織的遠端使用者存取權，請清除 [**啟用遠端使用者存取權**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3092f-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="3092f-125">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3092f-125">Click **Commit**.</span></span>

<span data-ttu-id="3092f-126">若要讓遠端使用者登入執行商務用 Skype Server 的伺服器，您也必須至少設定一個外部存取原則來支援遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="3092f-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="3092f-127">如需詳細資訊，請參閱[在商務用 Skype Server 中設定控制遠端使用者存取權的原則](../external-access-policies/configure-policies-to-control-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="3092f-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3092f-128">使用 Windows PowerShell Cmdlet 來啟用或停用遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="3092f-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="3092f-129">您可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 來管理遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="3092f-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="3092f-130">這個 Cmdlet 可以從商務用 Skype Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行。</span><span class="sxs-lookup"><span data-stu-id="3092f-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="3092f-131">啟用遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="3092f-131">To enable remote user access</span></span>

  - <span data-ttu-id="3092f-132">若要啟用遠端使用者存取，請將**AllowOutsideUsers**屬性的值設定為 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="3092f-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="3092f-133">若要停用遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="3092f-133">To disable remote user access</span></span>

  - <span data-ttu-id="3092f-134">若要停用遠端使用者存取，請將**AllowOutsideUsers**屬性的值設定為 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="3092f-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


