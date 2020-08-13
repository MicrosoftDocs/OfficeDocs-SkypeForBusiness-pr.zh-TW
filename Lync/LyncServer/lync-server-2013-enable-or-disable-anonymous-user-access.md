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
ms.openlocfilehash: 076cfd8b787c85ba94d3538c5510d7c12ca11b22
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a><span data-ttu-id="d87fe-102">在 Lync Server 2013 中啟用或停用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="d87fe-102">Enable or disable anonymous user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d87fe-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d87fe-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d87fe-104">匿名使用者是指沒有組織的 Active Directory 網域服務或支援的同盟網域中的使用者帳戶的使用者，但可邀請他們在內部部署會議中遠端參與。</span><span class="sxs-lookup"><span data-stu-id="d87fe-104">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="d87fe-105">透過允許匿名參與會議，您可以啟用匿名使用者 (也就是說，其身分識別透過會議或會議金鑰驗證的使用者，只) 加入會議。</span><span class="sxs-lookup"><span data-stu-id="d87fe-105">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="d87fe-106">允許匿名參與必須為您的組織啟用它。</span><span class="sxs-lookup"><span data-stu-id="d87fe-106">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="d87fe-107">如果您稍後想要暫時或永久禁止匿名使用者進行存取，您可以對組織停用。</span><span class="sxs-lookup"><span data-stu-id="d87fe-107">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="d87fe-108">使用本節中的程式來啟用或停用組織的匿名使用者存取。</span><span class="sxs-lookup"><span data-stu-id="d87fe-108">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d87fe-109">透過為您的組織啟用匿名使用者存取，您只會指定執行 Access Edge service 的伺服器支援匿名使用者的存取。</span><span class="sxs-lookup"><span data-stu-id="d87fe-109">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="d87fe-110">除非您也至少要設定一個會議原則，並將其套用至一或多個使用者或使用者群組，否則匿名使用者無法參與您組織中的任何會議。</span><span class="sxs-lookup"><span data-stu-id="d87fe-110">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="d87fe-111">只有被指派為支援匿名使用者之會議原則的使用者，才可邀請匿名使用者加入會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="d87fe-111">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="d87fe-112">如需設定會議原則以支援邀請匿名使用者的詳細資訊，請參閱<A href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的會議原則</A>。</span><span class="sxs-lookup"><span data-stu-id="d87fe-112">For details about configuring conferencing policies to support inviting anonymous users, see <A href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="d87fe-113">啟用或停用組織的匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="d87fe-113">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="d87fe-114">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d87fe-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d87fe-115">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d87fe-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d87fe-116">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d87fe-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d87fe-117">在左導覽列中，按一下 [**外部使用者存取**]，然後按一下 [ **Access Edge**設定]。</span><span class="sxs-lookup"><span data-stu-id="d87fe-117">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="d87fe-118">在 [ **Access Edge**設定] 頁面上，依序按一下 [**全域**]、[**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="d87fe-118">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d87fe-119">在 [**編輯 Access Edge**設定] 中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="d87fe-119">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="d87fe-120">若要為您的組織啟用匿名使用者存取，請選取 [**啟用與匿名使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d87fe-120">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="d87fe-121">若要停用組織的匿名使用者存取，請清除 [**啟用與匿名使用者的通訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d87fe-121">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="d87fe-122">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="d87fe-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d87fe-123">使用 Windows PowerShell Cmdlet 來啟用或停用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="d87fe-123">Enabling or Disabling Anonymous User Access by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d87fe-124">您可以使用 Windows PowerShell 和**Set-CsAccessEdgeConfiguration** Cmdlet 來管理匿名使用者存取。</span><span class="sxs-lookup"><span data-stu-id="d87fe-124">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="d87fe-125">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d87fe-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d87fe-126">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="d87fe-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="d87fe-127">啟用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="d87fe-127">To enable anonymous user access</span></span>

  - <span data-ttu-id="d87fe-128">若要啟用匿名使用者存取，請將**AllowAnonymousUsers**屬性的值設為 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="d87fe-128">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="d87fe-129">停用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="d87fe-129">To disable anonymous user access</span></span>

  - <span data-ttu-id="d87fe-130">若要停用匿名使用者存取，請將**AllowAnonymousUsers**屬性值設為 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="d87fe-130">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d87fe-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d87fe-131">See Also</span></span>


[<span data-ttu-id="d87fe-132">Lync Server 2013 的會議原則設定參考</span><span class="sxs-lookup"><span data-stu-id="d87fe-132">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

