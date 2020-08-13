---
title: Lync Server 2013：定義分支網站的 PSTN 閘道
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a47e395e74dae1eb6ec454e63fb343dcea7872
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="86070-102">在 Lync Server 2013 中定義分支網站的 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="86070-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86070-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="86070-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="86070-104">在中央網站（包含至少一個前端集區或 Standard Edition server）執行此程式。</span><span class="sxs-lookup"><span data-stu-id="86070-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="86070-105">在執行此程式之前，必須先進行下列條件：</span><span class="sxs-lookup"><span data-stu-id="86070-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="86070-106">Lync Server 2013 &nbsp; 通訊軟體必須在中央網站設定。</span><span class="sxs-lookup"><span data-stu-id="86070-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="86070-107">轉送伺服器必須部署在中央網站。</span><span class="sxs-lookup"><span data-stu-id="86070-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="86070-108">若要定義 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="86070-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="86070-109">依序按一下 [**開始**]、[**所有程式**] 及 [ **Microsoft lync server**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="86070-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="86070-110">在主控台樹中，展開中央網站，展開 [**分支 Office 網站**]，展開您要定義公用交換電話網路 (PSTN) 閘道的分支網站名稱，然後展開 [**共用元件**]。</span><span class="sxs-lookup"><span data-stu-id="86070-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="86070-111">以滑鼠右鍵按一下 [PSTN 閘道]\*\*\*\*，然後按一下 [新增 IP/PSTN 閘道]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="86070-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="86070-112">在 [**定義新的 IP/PSTN 閘道**] 對話方塊中，按一下 [**閘道 FQDN 或 IP 位址**]，然後輸入您要在分支網站上部署之閘道的完整功能變數名稱 (FQDN) 或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="86070-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="86070-113">按一下 [ **IP/PSTN 閘道的聆聽埠**]，然後接受預設值。</span><span class="sxs-lookup"><span data-stu-id="86070-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="86070-114">在 [ **SIP 傳輸通訊協定**] 清單中，按一下閘道使用的傳輸通訊協定，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="86070-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86070-115">基於安全性的考慮，強烈建議您使用支援傳輸層安全性 (TLS) 的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="86070-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="86070-116">使用 Cmdlet <STRONG>Set-CsPstnGateway</STRONG>修改 PSTN 閘道的屬性。</span><span class="sxs-lookup"><span data-stu-id="86070-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="86070-117">如需詳細資訊，請參閱 Lync Server Management Shell Help 中的<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>。</span><span class="sxs-lookup"><span data-stu-id="86070-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="86070-118">分支網站恢復功能的**下一個步驟**：[在 Lync Server 2013 中為分支網站恢復設定使用者](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="86070-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="86070-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="86070-119">See Also</span></span>


[<span data-ttu-id="86070-120">Lync Server 2013 中的 PSTN 閘道部署選項</span><span class="sxs-lookup"><span data-stu-id="86070-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

