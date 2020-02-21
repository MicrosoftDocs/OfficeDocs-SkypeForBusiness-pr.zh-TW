---
title: 規劃可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟
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
ms.openlocfilehash: 77884bdca8d02a29d98a2a4c2dd116abb72d8f20
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="e0e8b-102">可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中規劃</span><span class="sxs-lookup"><span data-stu-id="e0e8b-102">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0e8b-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="e0e8b-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e0e8b-104">舊版的 Lync Server 和 Office Communications Server 提供可延伸訊息和目前狀態通訊協定 (XMPP) 閘道，可以部署為不同的伺服器角色，以允許與 XMPP 部署同盟。</span><span class="sxs-lookup"><span data-stu-id="e0e8b-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="e0e8b-105">在 [Microsoft Lync Server 2013 XMPP 功能可以部署為功能。</span><span class="sxs-lookup"><span data-stu-id="e0e8b-105">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="e0e8b-106">XMPP 功能安裝在兩個部分： Edge Server 及 XMPP 閘道在前端伺服器上執行的伺服器執行 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="e0e8b-106">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="e0e8b-107">部署及設定 XMPP 涵蓋在[部署外部使用者存取 Lync Server 2013 中](lync-server-2013-deploying-external-user-access.md)規劃支援 XMPP 貴組織中所定義連接埠和通訊協定規則上您的防火牆、 設定憑證，以及新增 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="e0e8b-107">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="e0e8b-108">本節中的下列主題將摘要說明您必須成功計劃部署的 XMPP 同盟的資訊。</span><span class="sxs-lookup"><span data-stu-id="e0e8b-108">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e0e8b-109">測試及版與 Google Talk 的立即訊息同盟支援 Microsoft Lync Server 2013 XMPP 功能。</span><span class="sxs-lookup"><span data-stu-id="e0e8b-109">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="e0e8b-110">為任何其他 XMPP 系統連絡協力廠商連絡，以確認它們支援同盟與 Lync Server 2013，以及任何部署或疑難排解建議。</span><span class="sxs-lookup"><span data-stu-id="e0e8b-110">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e0e8b-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="e0e8b-111">In This Section</span></span>

  - [<span data-ttu-id="e0e8b-112">憑證摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="e0e8b-112">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="e0e8b-113">連接埠摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="e0e8b-113">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="e0e8b-114">DNS 摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="e0e8b-114">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0e8b-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e0e8b-115">See Also</span></span>


[<span data-ttu-id="e0e8b-116">設定 Lync Server 2013 中的 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="e0e8b-116">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="e0e8b-117">在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="e0e8b-117">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="e0e8b-118">管理 Lync Server 2013 中的 XMPP 同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="e0e8b-118">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="e0e8b-119">[Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e0e8b-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="e0e8b-120">[Get-csxmppallowedpartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e0e8b-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="e0e8b-121">[Get-csxmppgatewayconfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e0e8b-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

