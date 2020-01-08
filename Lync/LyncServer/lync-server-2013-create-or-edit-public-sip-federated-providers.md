---
title: Lync Server 2013：建立或編輯公用 SIP 同盟提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876a79e840990afb0c9cf0bae4fc819ec10db5d8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a><span data-ttu-id="f0410-102">在 Lync Server 2013 中建立或編輯公用 SIP 同盟提供者</span><span class="sxs-lookup"><span data-stu-id="f0410-102">Create or edit public SIP federated providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0410-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f0410-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f0410-104">公用立即訊息（IM）連線功能可讓貴組織中的使用者使用 IM 與公用 IM 服務提供者所提供之 IM 服務的使用者通訊，包括 Windows Live Messenger\!、YAHOO 和 AOL。</span><span class="sxs-lookup"><span data-stu-id="f0410-104">Public instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by public IM service providers, including the Windows Live Messenger, Yahoo\!, and AOL.</span></span>

<span data-ttu-id="f0410-105">Lync Server 2013 具有適用于北美線上、Windows Live 和 Yahoo 的公用提供者配置\!</span><span class="sxs-lookup"><span data-stu-id="f0410-105">Lync Server 2013 has public provider configurations for America Online, Windows Live and Yahoo\!</span></span> <span data-ttu-id="f0410-106">立即訊息。</span><span class="sxs-lookup"><span data-stu-id="f0410-106">instant messaging.</span></span> <span data-ttu-id="f0410-107">每個公開提供者都是使用提供者的邊緣伺服器完整功能變數名稱來設定，而且預設驗證層級**可讓使用者只與他們的連絡人清單中使用這個提供者的人通訊**。</span><span class="sxs-lookup"><span data-stu-id="f0410-107">Each public provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="f0410-108">預設設定為 [未啟用任何公用提供者]。</span><span class="sxs-lookup"><span data-stu-id="f0410-108">As a default setting, none of the public providers are enabled.</span></span> <span data-ttu-id="f0410-109">在啟用公用提供者之前，您應該先完成授權協定和置備作業。</span><span class="sxs-lookup"><span data-stu-id="f0410-109">You should complete license agreement and provisioning work before enabling the public providers.</span></span> <span data-ttu-id="f0410-110">您可以先啟用提供者，然後才能完成授權及預配作業。</span><span class="sxs-lookup"><span data-stu-id="f0410-110">You can enable the provider before completing the licensing and provisioning work.</span></span> <span data-ttu-id="f0410-111">在完成先決條件工作完成之前，使用者將無法與這些提供者上的連絡人通訊。</span><span class="sxs-lookup"><span data-stu-id="f0410-111">Users will not be able to communicate with contacts on those providers until the pre-requisite work is completed.</span></span> <span data-ttu-id="f0410-112">如需授權與提供公用提供者的詳細資料，請參閱[在 Lync Server 2013 中設定控制公用使用者存取權的原則](lync-server-2013-configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="f0410-112">For details on licensing and provisioning of public providers, see [Configure policies to control public user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).</span></span>

<span data-ttu-id="f0410-113">使用下列程式來建立或編輯公用提供者：</span><span class="sxs-lookup"><span data-stu-id="f0410-113">Use the following procedure to create or edit Public providers:</span></span>

<div>

## <a name="to-create-or-edit-public-providers"></a><span data-ttu-id="f0410-114">建立或編輯公用提供者</span><span class="sxs-lookup"><span data-stu-id="f0410-114">To create or edit public providers</span></span>

1.  <span data-ttu-id="f0410-115">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="f0410-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f0410-116">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="f0410-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f0410-117">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f0410-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f0410-118">在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [ **SIP 同盟提供者**]。</span><span class="sxs-lookup"><span data-stu-id="f0410-118">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="f0410-119">如果您需要建立新的公用提供者，請按一下 [**新增**]，然後按一下 [**公用提供者**]。</span><span class="sxs-lookup"><span data-stu-id="f0410-119">If you need to create a new Public provider, click **New** and then click **Public provider**.</span></span>

5.  <span data-ttu-id="f0410-120">如果您需要從公用提供者清單中編輯專案，請選取公用提供者，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="f0410-120">If you need to edit an entry from the list of Public providers, select a public provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="f0410-121">在 [**編輯 SIP 聯盟提供者**] 頁面上，您可以輸入或編輯下列設定：</span><span class="sxs-lookup"><span data-stu-id="f0410-121">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="f0410-122">**啟用與此提供者**   的通訊選取此設定即可啟用與此提供者使用者的 IM。</span><span class="sxs-lookup"><span data-stu-id="f0410-122">**Enable communications with this provider**   Selecting this setting enables IM with this provider’s users.</span></span>
    
      - <span data-ttu-id="f0410-123">**提供者名稱：**   required 屬性，請輸入提供者的名稱，因為它會反映在 SIP 同盟提供者清單中。</span><span class="sxs-lookup"><span data-stu-id="f0410-123">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="f0410-124">**[存取邊緣服務（FQDN）]：**   [必要] 屬性，請輸入您要設定之提供者的存取邊緣服務的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="f0410-124">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the provider that you are configuring.</span></span> <span data-ttu-id="f0410-125">此資訊是以預設專案提供的，只有在公用提供者變更公用提供者的存取邊緣服務的 FQDN 時，才能加以變更。</span><span class="sxs-lookup"><span data-stu-id="f0410-125">This information is provided as a default item, and should only be changed if the public provider makes a change to the FQDN of the Access Edge service at the public provider.</span></span>
    
      - <span data-ttu-id="f0410-126">**預設驗證階層：**   預設設定是 [**允許使用者與連絡人清單中的人員通訊]，使用這個提供者**時，會將通訊限制在您已接受的連絡人，並在您的連絡人清單中。</span><span class="sxs-lookup"><span data-stu-id="f0410-126">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="f0410-127">選取 [**允許使用者與使用這個提供者的所有人通訊**]，就會移除您必須收到並接受連絡人邀請的限制。</span><span class="sxs-lookup"><span data-stu-id="f0410-127">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite.</span></span> <span data-ttu-id="f0410-128">此設定不會限制誰能從公用提供者的網路與您聯繫。</span><span class="sxs-lookup"><span data-stu-id="f0410-128">This setting does not limit who can contact you from the public provider’s network.</span></span>

7.  <span data-ttu-id="f0410-129">設定完畢後，請按一下 [**認可**] 來儲存，或按一下 [**取消**] 放棄您的變更。</span><span class="sxs-lookup"><span data-stu-id="f0410-129">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0410-130">請參閱</span><span class="sxs-lookup"><span data-stu-id="f0410-130">See Also</span></span>


[<span data-ttu-id="f0410-131">在 Lync Server 2013 中設定原則以控制公用使用者存取</span><span class="sxs-lookup"><span data-stu-id="f0410-131">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="f0410-132">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="f0410-132">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

