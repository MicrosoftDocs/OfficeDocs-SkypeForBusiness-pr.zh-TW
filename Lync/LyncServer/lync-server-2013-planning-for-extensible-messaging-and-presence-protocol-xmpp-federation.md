---
title: 針對可擴展訊息和目前狀態通訊協定（XMPP）同盟進行規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4e1d8f9b7f164dd9e83f556dcc57809619278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="46860-102">在 Lync Server 2013 中規劃可擴展訊息和目前狀態通訊協定（XMPP）同盟</span><span class="sxs-lookup"><span data-stu-id="46860-102">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46860-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="46860-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="46860-104">舊版的 Lync Server 和 Office 通訊伺服器提供可擴展的訊息和目前狀態通訊協定（XMPP）閘道，可將其部署為個別的伺服器角色，以允許與 XMPP 部署進行聯盟。</span><span class="sxs-lookup"><span data-stu-id="46860-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="46860-105">在 Microsoft Lync Server 2013 中，您可以將 XMPP 功能部署為功能。</span><span class="sxs-lookup"><span data-stu-id="46860-105">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="46860-106">XMPP 功能是由兩個部分所安裝：在 Edge 伺服器上執行的 XMPP proxy，以及在前端伺服器上執行的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="46860-106">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="46860-107">XMPP 的部署與設定在[Lync Server 2013 中的 [部署外部使用者存取權](lync-server-2013-deploying-external-user-access.md)] 中，您打算在防火牆上定義埠和通訊協定規則、設定憑證的設定，以及新增 DNS 記錄，以規劃支援組織中的 XMPP。</span><span class="sxs-lookup"><span data-stu-id="46860-107">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="46860-108">本節中的下列主題摘要說明為您的部署順利規劃 XMPP 同盟時所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="46860-108">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="46860-109">Lync Server 2013 的 XMPP 功能是由 Microsoft 針對使用 Google 交談的立即訊息同盟進行測試和支援。</span><span class="sxs-lookup"><span data-stu-id="46860-109">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="46860-110">針對任何其他 XMPP 系統，請與協力廠商廠商聯繫，確認他們支援 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。</span><span class="sxs-lookup"><span data-stu-id="46860-110">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="46860-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="46860-111">In This Section</span></span>

  - [<span data-ttu-id="46860-112">認證摘要-Lync Server 2013 中的可擴展訊息和目前狀態通訊協定（XMPP）同盟</span><span class="sxs-lookup"><span data-stu-id="46860-112">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="46860-113">在 Lync Server 2013 中的埠摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟</span><span class="sxs-lookup"><span data-stu-id="46860-113">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="46860-114">在 Lync Server 2013 中的 DNS 摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟</span><span class="sxs-lookup"><span data-stu-id="46860-114">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46860-115">請參閱</span><span class="sxs-lookup"><span data-stu-id="46860-115">See Also</span></span>


[<span data-ttu-id="46860-116">在 Lync Server 2013 中設定 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="46860-116">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="46860-117">在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="46860-117">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="46860-118">在 Lync Server 2013 中管理 XMPP 同盟夥伴</span><span class="sxs-lookup"><span data-stu-id="46860-118">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="46860-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46860-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="46860-120">[CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46860-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="46860-121">[CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="46860-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

