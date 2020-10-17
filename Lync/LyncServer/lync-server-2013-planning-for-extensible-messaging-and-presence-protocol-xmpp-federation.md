---
title: 規劃可擴展郵件和顯示狀態通訊協定 (XMPP) 同盟
description: 規劃可擴展郵件和顯示狀態通訊協定 (XMPP) 同盟。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 511273b69181334821f446bcc4424641367ecf51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562799"
---
# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="f3c53-103">在 Lync Server 2013 中規劃可擴展郵件和顯示狀態通訊協定 (XMPP) 同盟</span><span class="sxs-lookup"><span data-stu-id="f3c53-103">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3c53-104">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f3c53-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f3c53-105">舊版的 Lync Server 和 Office 通訊伺服器提供可擴展的訊息和顯示狀態通訊協定 (XMPP) 閘道，可部署為個別的伺服器角色，以允許與 XMPP 部署同盟。</span><span class="sxs-lookup"><span data-stu-id="f3c53-105">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="f3c53-106">在 Microsoft Lync Server 2013 中，可以將 XMPP 功能部署為功能。</span><span class="sxs-lookup"><span data-stu-id="f3c53-106">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="f3c53-107">XMPP 功能是以兩個部分安裝：在 Edge Server 上執行的 XMPP proxy，以及在前端伺服器上執行的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="f3c53-107">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="f3c53-108">XMPP 的部署和設定涵蓋在 [Lync Server 2013 的部署外部使用者存取](lync-server-2013-deploying-external-user-access.md) 中，您可以在防火牆上定義埠和通訊協定規則、憑證的設定，以及新增 DNS 記錄，以支援組織中的 XMPP。</span><span class="sxs-lookup"><span data-stu-id="f3c53-108">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="f3c53-109">本節中的下列主題摘要說明為您的部署成功規劃 XMPP 同盟時所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="f3c53-109">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f3c53-110">Lync Server 2013 的 XMPP 功能會經過測試，並受 Microsoft 支援，以進行與 Google 交談的立即訊息同盟。</span><span class="sxs-lookup"><span data-stu-id="f3c53-110">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="f3c53-111">對於任何其他 XMPP 系統，請聯繫協力廠商廠商，以確認其支援與 Lync Server 2013 的同盟，以及任何部署或疑難排解建議。</span><span class="sxs-lookup"><span data-stu-id="f3c53-111">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f3c53-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="f3c53-112">In This Section</span></span>

  - [<span data-ttu-id="f3c53-113">憑證摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) 同盟 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3c53-113">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="f3c53-114">在 Lync Server 2013 中，埠摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) 同盟</span><span class="sxs-lookup"><span data-stu-id="f3c53-114">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="f3c53-115">Lync Server 2013 中的 DNS 摘要-可延伸的訊息和顯示狀態通訊協定 (XMPP) 同盟</span><span class="sxs-lookup"><span data-stu-id="f3c53-115">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3c53-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f3c53-116">See Also</span></span>


[<span data-ttu-id="f3c53-117">在 Lync Server 2013 中設定 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="f3c53-117">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="f3c53-118">在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="f3c53-118">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="f3c53-119">在 Lync Server 2013 中管理 XMPP 同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="f3c53-119">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="f3c53-120">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3c53-120">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="f3c53-121">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3c53-121">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="f3c53-122">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f3c53-122">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

