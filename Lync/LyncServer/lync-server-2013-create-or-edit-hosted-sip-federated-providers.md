---
title: Lync Server 2013：建立或編輯主控的 SIP 同盟提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b78e9be0f3b885a40fcf313173a1281ac5489936
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a><span data-ttu-id="bb59d-102">建立或編輯主控的 SIP 同盟提供者 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb59d-102">Create or edit hosted SIP federated providers Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb59d-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="bb59d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="bb59d-104">主控提供者立即訊息（IM）連線功能可讓您組織中的使用者使用 IM，與託管提供者提供的 IM 服務使用者通訊，包括 Microsoft 365 和 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="bb59d-104">Hosted provider instant messaging (IM) connectivity enables users in your organization to use IM to communicate with users of IM services provided by hosted providers, including Microsoft 365 and Lync Online.</span></span>

<span data-ttu-id="bb59d-105">每個裝載提供者都設有提供者的 Edge Server 完整網域名稱，以及預設驗證層級 [允許使用者僅與其連絡人清單中使用此提供者的人通訊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb59d-105">Each hosted provider is configured with the provider’s Edge server fully qualified domain name, and the default verification level **Allow users to communicate only with people on their Contacts list who use this provider**.</span></span>

<span data-ttu-id="bb59d-106">使用下列程序來建立或編輯裝載提供者：</span><span class="sxs-lookup"><span data-stu-id="bb59d-106">Use the following procedure to create or edit Hosted providers:</span></span>

<div>

## <a name="to-create-or-edit-hosted-providers"></a><span data-ttu-id="bb59d-107">建立或編輯裝載提供者</span><span class="sxs-lookup"><span data-stu-id="bb59d-107">To create or edit hosted providers</span></span>

1.  <span data-ttu-id="bb59d-108">從 RTCUniversalServerAdmins 群組成員的使用者帳戶（或具有相等的使用者權限）或指派給 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bb59d-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bb59d-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bb59d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bb59d-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bb59d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bb59d-111">在左導覽列中，按一下 [同盟及外部存取]\*\*\*\*，然後按一下 [SIP 同盟提供者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb59d-111">In the left navigation bar, click **Federation and External Access**, and then click **SIP Federated Providers**.</span></span>

4.  <span data-ttu-id="bb59d-112">如果您需要建立新的裝載提供者，請按一下 [新增]\*\*\*\*，然後按一下 [裝載提供者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb59d-112">If you need to create a new Hosted provider, click **New** and then click **Hosted provider**.</span></span>

5.  <span data-ttu-id="bb59d-113">如果您需要編輯裝載提供者清單中的項目，請選取裝載提供者，按一下 [編輯]\*\*\*\*，然後按一下 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bb59d-113">If you need to edit an entry from the list of Hosted providers, select a hosted provider, click **Edit**, then click **Show details**.</span></span>

6.  <span data-ttu-id="bb59d-114">在「編輯 SIP 同盟提供者」\*\*\*\* 頁面上，您可以輸入或編輯下列設定：</span><span class="sxs-lookup"><span data-stu-id="bb59d-114">On the **Edit SIP Federated Provider** page, you can type or edit the following settings:</span></span>
    
      - <span data-ttu-id="bb59d-115">**啟用與此提供者**     的通訊選取此設定便可與此提供者的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="bb59d-115">**Enable communications with this provider**   Selecting this setting enables communications with this provider’s users.</span></span>
    
      - <span data-ttu-id="bb59d-116">**提供者名稱：**    必要的屬性，請輸入提供者的名稱，因為它會反映在 SIP 同盟提供者的清單中。</span><span class="sxs-lookup"><span data-stu-id="bb59d-116">**Provider name:**   A required property, type the name of the provider as it will be reflected in the listing of SIP Federated Providers.</span></span>
    
      - <span data-ttu-id="bb59d-117">**Access Edge service （FQDN）：**    必要的屬性，請輸入您要設定之主控提供者的 Access Edge service 的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="bb59d-117">**Access Edge service (FQDN):**   A required property, type the fully qualified domain name of the Access Edge service of the hosted provider that you are configuring.</span></span> <span data-ttu-id="bb59d-118">此資訊應由主控的提供者提供，而且只有在主控提供者對主控提供者的 Access Edge service 的 FQDN 進行變更時，才應變更此資訊。</span><span class="sxs-lookup"><span data-stu-id="bb59d-118">This information should be provided by the hosted provider, and should only be changed if the hosted provider makes a change to the FQDN of the Access Edge service at the hosted provider.</span></span>
    
      - <span data-ttu-id="bb59d-119">**預設驗證層級：**    預設設定為 [**允許使用者與使用此提供者的連絡人清單上的人員通訊**]，會限制對您已接受的連絡人和連絡人清單中的連絡人進行通訊。</span><span class="sxs-lookup"><span data-stu-id="bb59d-119">**Default verification level:**   The default setting, **Allow users to communicate with people on their Contacts list who use this provider** will limit communication to contacts that you have accepted and are in your contact list.</span></span>
        
        <span data-ttu-id="bb59d-p103">選取 [允許使用者與使用此提供者的所有人通訊]\*\*\*\* 會移除您必須收到並接受連絡人邀請的限制。此設定不限制哪些人可以從裝載提供者的網路連絡您。</span><span class="sxs-lookup"><span data-stu-id="bb59d-p103">Selecting **Allow users to communicate with everyone using this provider** removes the restriction that you must have received and accepted a contact invite. This setting does not limit who can contact you from the hosted provider’s network.</span></span>

7.  <span data-ttu-id="bb59d-122">完成設定時，按一下 [認可]\*\*\*\* 以儲存，或按一下 [取消]\*\*\*\* 以捨棄變更。</span><span class="sxs-lookup"><span data-stu-id="bb59d-122">When you are done configuring the settings, click **Commit** to save, or click **Cancel** to discard your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb59d-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bb59d-123">See Also</span></span>


[<span data-ttu-id="bb59d-124">在 Lync Server 2013 中設定原則以控制公用使用者存取</span><span class="sxs-lookup"><span data-stu-id="bb59d-124">Configure policies to control public user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[<span data-ttu-id="bb59d-125">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="bb59d-125">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

