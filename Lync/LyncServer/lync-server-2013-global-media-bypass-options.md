---
title: Lync Server 2013：全域媒體旁路選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec067e84c87321374ed1d9beb98c086633f3e28c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515330"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="32f02-102">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="32f02-102">Global media bypass options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32f02-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="32f02-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32f02-104">本主題假設您已針對您想要讓媒體略過轉送伺服器的特定網站或服務，在網際網路電話語音服務提供者 (上，對對等 ( (PSTN) 閘道、IP-PBX 或會話邊界控制器) SBC) 的任何主幹，都已設定媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="32f02-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="32f02-105">除了啟用對等端相關之個別主幹連線的媒體旁路，您也必須通用啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="32f02-105">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="32f02-106">通用媒體旁路設定可以指定媒體旁路對 PSTN 的呼叫永遠嘗試，或使用子網對應至網路網站和網路地區（類似于通話許可控制，另一種高級語音功能）來使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="32f02-106">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="32f02-107">當 media 旁路和通話許可控制皆已啟用時，系統會自動使用為通話許可控制指定的網路地區、網路網站及子網資訊，以決定是否使用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="32f02-107">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="32f02-108">這表示您無法指定啟用通話許可控制時，永遠會嘗試對 PSTN 呼叫媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="32f02-108">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="32f02-109">本主題說明如何將 Lync Server 控制台和 Lync Server 管理命令介面一起使用，以設定全域媒體旁路設定。</span><span class="sxs-lookup"><span data-stu-id="32f02-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32f02-110">使用下列步驟設定媒體旁路時，假設前提是用戶端和中繼伺服器對等端 (例如 PSTN 閘道、IP-PBX 或 SIP 主幹提供者上的 SBC) 之間的連線良好。</span><span class="sxs-lookup"><span data-stu-id="32f02-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="32f02-111">如果連結上有頻寬限制，就無法將媒體旁路套用至通話。</span><span class="sxs-lookup"><span data-stu-id="32f02-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="32f02-112">媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。</span><span class="sxs-lookup"><span data-stu-id="32f02-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="32f02-113">Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。</span><span class="sxs-lookup"><span data-stu-id="32f02-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="32f02-114">只有在整合通訊開啟互通性計畫– Lync Server at 上列出的產品及版本，才支援媒體旁路 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。</span><span class="sxs-lookup"><span data-stu-id="32f02-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="32f02-115">後續步驟：選擇通用媒體旁路設定</span><span class="sxs-lookup"><span data-stu-id="32f02-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="32f02-116">在針對特定網站或服務對等端的主幹連線啟用媒體旁路後，使用下列內容可執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="32f02-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="32f02-117">啟用媒體旁路，如在 [Lync server 2013 設定媒體旁路中所述，永遠略過轉送伺服器](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="32f02-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="32f02-118">或者，設定媒體旁路使用網站與地區資訊，如在 [Lync Server 2013 設定媒體旁路全域設定中所述，以使用網站與地區資訊](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)。</span><span class="sxs-lookup"><span data-stu-id="32f02-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32f02-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="32f02-119">See Also</span></span>


[<span data-ttu-id="32f02-120">在 Lync Server 2013 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="32f02-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="32f02-121">在 Lync Server 2013 中建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="32f02-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="32f02-122">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="32f02-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="32f02-123">Lync Server 2013 中的媒體旁路和轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="32f02-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

