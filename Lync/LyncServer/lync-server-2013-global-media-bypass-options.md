---
title: Lync Server 2013：全域媒體旁路選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ebe39b6faeffd36f0dfc9e25959fe7a0b356153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="5254b-102">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="5254b-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5254b-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="5254b-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5254b-104">本主題假設您已針對特定網站或服務，將任何 trunks 的媒體旁路設定為對等（在網際網路電話服務提供者的公用交換電話網絡（PSTN）閘道、IP PBX 或會話邊界控制器（SBC）您希望媒體略過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="5254b-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="5254b-105">除了為與對等相關聯的個別幹線連線啟用媒體旁路之外，您還必須啟用全域旁路媒體。</span><span class="sxs-lookup"><span data-stu-id="5254b-105">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="5254b-106">全域媒體旁路設定可以指定媒體略過嘗試撥打電話給 PSTN，或者使用子網至網路網站和網路區域的對應，就像是由通話許可控制所做的一樣，另一個[高級語音] 功能。</span><span class="sxs-lookup"><span data-stu-id="5254b-106">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="5254b-107">當 [媒體旁路] 和 [呼叫許可控制] 都已啟用時，系統會在判斷是否要使用媒體旁路時，自動使用為 [呼叫許可控制] 所指定的網路區域、網路網站及子網資訊。</span><span class="sxs-lookup"><span data-stu-id="5254b-107">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="5254b-108">這表示您無法指定在已啟用呼叫許可控制的情況下，不會針對 PSTN 呼叫總是嘗試使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="5254b-108">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="5254b-109">本主題說明如何搭配使用 Lync Server [控制台] 和 Lync Server 管理命令介面來設定全域媒體旁路設定。</span><span class="sxs-lookup"><span data-stu-id="5254b-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5254b-110">當您使用這些步驟來設定媒體旁路時，假設您在用戶端與中繼伺服器對等（例如 PSTN 閘道、IP PBX 或 SIP 中繼提供者的 SBC）之間有良好的連線能力。</span><span class="sxs-lookup"><span data-stu-id="5254b-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="5254b-111">如果連結有任何頻寬限制，則無法將媒體略過套用至通話。</span><span class="sxs-lookup"><span data-stu-id="5254b-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="5254b-112">媒體旁路將無法與每個 PSTN 閘道、IP PBX 和 SBC 進行交互操作。</span><span class="sxs-lookup"><span data-stu-id="5254b-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="5254b-113">Microsoft 已經測試了一組 PSTN 閘道，並有已認證的合作夥伴，且已使用 Cisco IP-Pbx 進行了一些測試。</span><span class="sxs-lookup"><span data-stu-id="5254b-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="5254b-114">只有在整合通訊開啟互通性計畫（Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>）中所列的產品和版本，才能支援媒體略過。</span><span class="sxs-lookup"><span data-stu-id="5254b-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="5254b-115">後續步驟：選擇全域媒體旁路設定</span><span class="sxs-lookup"><span data-stu-id="5254b-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="5254b-116">在針對特定網站或服務在對等的任何干線連線上啟用媒體旁路之後，請使用下列內容之一：</span><span class="sxs-lookup"><span data-stu-id="5254b-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="5254b-117">[在[Lync server 2013 中設定媒體旁路](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)] 中所述的 [自動啟用媒體旁路]，以永遠略過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="5254b-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="5254b-118">或者，將 [媒體旁路] 設定為使用網站和區域資訊，如在[Lync Server 2013 中設定媒體旁路全域設定以使用網站和區域資訊](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)所述。</span><span class="sxs-lookup"><span data-stu-id="5254b-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5254b-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="5254b-119">See Also</span></span>


<span data-ttu-id="5254b-120">[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="5254b-120">[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span></span>  
[<span data-ttu-id="5254b-121">在 Lync Server 2013 中建立子網路與網路站台的關聯</span><span class="sxs-lookup"><span data-stu-id="5254b-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="5254b-122">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="5254b-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="5254b-123">Lync Server 2013 中的媒體旁路和中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="5254b-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

