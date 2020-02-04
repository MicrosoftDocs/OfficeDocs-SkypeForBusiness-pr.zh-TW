---
title: Lync Server 2013：啟用或停用匿名使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d38d0d9f50ff06b2f7eb95944d9214c2c4c64a5c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="b06ad-102">在 Lync Server 2013 中啟用或停用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="b06ad-102">Enable or disable anonymous user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b06ad-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b06ad-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b06ad-104">匿名使用者是在組織的 Active Directory 網域服務或受支援的聯盟網域中沒有使用者帳戶的使用者，但在內部部署會議中可以受邀參與遠端參與。</span><span class="sxs-lookup"><span data-stu-id="b06ad-104">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="b06ad-105">透過允許匿名參與會議，您可以啟用匿名使用者（也就是僅透過會議或會議金鑰驗證身分識別的使用者）加入會議。</span><span class="sxs-lookup"><span data-stu-id="b06ad-105">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="b06ad-106">允許匿名參與需要為您的組織啟用。</span><span class="sxs-lookup"><span data-stu-id="b06ad-106">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="b06ad-107">如果您稍後想要暫時或永久避免匿名使用者的存取權，您可以針對您的組織停用它。</span><span class="sxs-lookup"><span data-stu-id="b06ad-107">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="b06ad-108">您可以使用本節中的程式來啟用或停用您組織的匿名使用者存取權。</span><span class="sxs-lookup"><span data-stu-id="b06ad-108">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b06ad-109">透過針對您的組織啟用匿名使用者存取，您只會指定執行存取邊緣服務的伺服器支援由匿名使用者進行存取。</span><span class="sxs-lookup"><span data-stu-id="b06ad-109">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="b06ad-110">匿名使用者無法參與貴組織中的任何會議，除非您也設定了至少一個會議原則，並將它套用至一或多個使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b06ad-110">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="b06ad-111">只有指派會議原則且設定為支援匿名使用者的使用者，才能邀請匿名使用者加入會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="b06ad-111">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="b06ad-112">如需設定會議原則以支援邀請匿名使用者的詳細資料，請參閱<A href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的會議原則</A>。</span><span class="sxs-lookup"><span data-stu-id="b06ad-112">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="b06ad-113">若要啟用或停用您組織的匿名使用者存取權</span><span class="sxs-lookup"><span data-stu-id="b06ad-113">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="b06ad-114">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="b06ad-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b06ad-115">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b06ad-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b06ad-116">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b06ad-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b06ad-117">在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。</span><span class="sxs-lookup"><span data-stu-id="b06ad-117">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="b06ad-118">在 [**存取邊緣**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="b06ad-118">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b06ad-119">在 [**編輯存取邊緣**設定] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="b06ad-119">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="b06ad-120">若要為您的組織啟用匿名使用者存取，請選取 [**啟用與匿名使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b06ad-120">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="b06ad-121">若要停用您組織的匿名使用者存取，請清除 [**啟用與匿名使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b06ad-121">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="b06ad-122">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b06ad-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b06ad-123">使用 Windows PowerShell Cmdlet 來啟用或停用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="b06ad-123">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b06ad-124">您可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** Cmdlet 來管理匿名使用者存取。</span><span class="sxs-lookup"><span data-stu-id="b06ad-124">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="b06ad-125">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b06ad-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b06ad-126">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="b06ad-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="b06ad-127">啟用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="b06ad-127">To enable anonymous user access</span></span>

  - <span data-ttu-id="b06ad-128">若要啟用匿名使用者存取，請將**AllowAnonymousUsers**屬性的值設定為 True （$True）：</span><span class="sxs-lookup"><span data-stu-id="b06ad-128">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="b06ad-129">若要停用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="b06ad-129">To disable anonymous user access</span></span>

  - <span data-ttu-id="b06ad-130">若要停用匿名使用者存取，請將**AllowAnonymousUsers**屬性的值設定為 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="b06ad-130">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b06ad-131">請參閱</span><span class="sxs-lookup"><span data-stu-id="b06ad-131">See Also</span></span>


[<span data-ttu-id="b06ad-132">Lync Server 2013 的會議原則設定參考</span><span class="sxs-lookup"><span data-stu-id="b06ad-132">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

