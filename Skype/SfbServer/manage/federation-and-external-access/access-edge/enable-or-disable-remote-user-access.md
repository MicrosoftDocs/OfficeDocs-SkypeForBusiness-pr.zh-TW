---
title: 啟用或停用遠端使用者存取
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果您為遠端使用者啟用遠端使用者存取，支援的遠端使用者透過網際網路連線，而且不需要使用 VPN 連線，即可使用商務用 Skype Server 與內部使用者共同作業。
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817393"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="f3c9c-103">在商務用 Skype Server 中啟用或停用遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="f3c9c-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="f3c9c-104">遠端使用者是組織中具有持久 Active Directory 身分識別的使用者。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="f3c9c-105">遠端使用者通常會在您的網路外登入商務用 Skype Server，只要使用虛擬私人網路 (VPN) 未連接到組織的網路。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="f3c9c-106">遠端使用者包括在家中或在旅途中運作的員工，以及其他遠端工作者（如受信任的供應商，其已獲授與企業認證）。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="f3c9c-107">如果您為遠端使用者啟用遠端使用者存取，支援的遠端使用者透過網際網路連線，而且不需要使用 VPN 連線，即可使用商務用 Skype Server 與內部使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="f3c9c-108">若要支援遠端使用者存取，您必須啟用遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="f3c9c-109">當您啟用遠端使用者存取時，您可以為整個組織啟用它。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="f3c9c-110">如果您稍後想要暫時或永久防止遠端使用者存取，您可以為組織停用它。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="f3c9c-111">使用本節中的程式來啟用或停用組織的遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="f3c9c-112">啟用遠端使用者存取只會指定執行 Access Edge service 的伺服器可支援與遠端使用者的通訊，但遠端使用者無法參與立即訊息 (IM) 或組織中的會議，除非您也設定至少一個原則來管理遠端使用者存取的使用。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="f3c9c-113">在一個原則層級套用的商務用 Skype 伺服器原則設定，可以覆寫在另一個原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="f3c9c-114">商務用 Skype Server 原則優先順序為：使用者原則 (影響最大) 會覆寫網站原則，然後網站原則會覆寫全域原則 (影響最小)。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="f3c9c-115">也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="f3c9c-116">如需設定使用遠端使用者存取之原則的詳細資訊，請參閱 [在商務用 Skype Server 中設定原則以控制遠端使用者存取](../external-access-policies/configure-policies-to-control-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="f3c9c-117">啟用或停用組織的遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="f3c9c-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="f3c9c-118">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f3c9c-119">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f3c9c-120">在左導覽列中，按一下 [ **同盟和外部存取**]，然後按一下 [ **Access Edge** 設定]。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="f3c9c-121">在 [ **Access Edge** 設定] 頁面上，依序按一下 [ **全域**]、[ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f3c9c-122">在 [ **編輯 Access Edge** 設定] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="f3c9c-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="f3c9c-123">若要啟用組織的遠端使用者存取，請選取 [ **啟用遠端使用者存取** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="f3c9c-124">若要停用組織的遠端使用者存取，請清除 [ **啟用遠端使用者存取** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="f3c9c-125">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-125">Click **Commit**.</span></span>

<span data-ttu-id="f3c9c-126">若要讓遠端使用者登入執行商務用 Skype 伺服器的伺服器，您也必須至少設定一個外部存取原則，以支援遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="f3c9c-127">如需詳細資訊，請參閱 [Configure 原則 to control remote user access In 商務用 Skype Server](../external-access-policies/configure-policies-to-control-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f3c9c-128">使用 Windows PowerShell Cmdlet 來啟用或停用遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="f3c9c-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f3c9c-129">您可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration Cmdlet 來管理遠端使用者存取。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="f3c9c-130">您可以從商務用 Skype Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f3c9c-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="f3c9c-131">啟用遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="f3c9c-131">To enable remote user access</span></span>

  - <span data-ttu-id="f3c9c-132">若要啟用遠端使用者存取，請將 **AllowOutsideUsers** 屬性的值設為 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="f3c9c-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="f3c9c-133">停用遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="f3c9c-133">To disable remote user access</span></span>

  - <span data-ttu-id="f3c9c-134">若要停用遠端使用者存取，請將 **AllowOutsideUsers** 屬性的值設為 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="f3c9c-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


