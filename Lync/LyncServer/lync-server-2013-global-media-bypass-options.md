---
title: Lync Server 2013： 通用媒體旁路選項
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
ms.openlocfilehash: 5b6a5f0d7a6a89b30b0ef08f8631b06fb9047616
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="44658-102">通用媒體旁路 Lync Server 2013 中的選項</span><span class="sxs-lookup"><span data-stu-id="44658-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44658-103">_**主題上次修改日期：** 2012年-10-04_</span><span class="sxs-lookup"><span data-stu-id="44658-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44658-104">本主題會假設您已設定好主幹對等端 （公用交換的電話網路 (PSTN) 閘道、 IP PBX 或在網際網路電話語音服務提供者的工作階段邊界控制器 (SBC)） 的媒體旁路的特定網站或服務您想要媒體略過此中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="44658-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="44658-105">除了啟用對等端相關之個別主幹連線的媒體旁路，您也必須通用啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="44658-105">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="44658-106">通用媒體旁路設定可以指定媒體旁路永遠嘗試 pstn 通話或媒體旁路所使用的子網路以網路網站與網路地區對應採用 — 類似所執行之動作的通話許可控制，另一個進階的語音功能。</span><span class="sxs-lookup"><span data-stu-id="44658-106">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="44658-107">媒體旁路和通話許可控制會同時啟用，然後網路地區、 網路網站，並針對指定的子網路資訊時決定是否要使用媒體旁路時，都會自動會使用通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="44658-107">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="44658-108">啟用通話許可控制時，這表示，您不能指定媒體旁路會永遠會嘗試至 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="44658-108">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="44658-109">本主題說明如何使用 Lync Server 控制台] 及 [Lync Server 管理命令介面在一起進行通用媒體旁路設定。</span><span class="sxs-lookup"><span data-stu-id="44658-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44658-110">使用下列步驟設定媒體旁路時，假設前提是用戶端和中繼伺服器對等端 (例如 PSTN 閘道、IP-PBX 或 SIP 主幹提供者上的 SBC) 之間的連線良好。</span><span class="sxs-lookup"><span data-stu-id="44658-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="44658-111">如果連結上有頻寬限制，就無法將媒體旁路套用至通話。</span><span class="sxs-lookup"><span data-stu-id="44658-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="44658-112">媒體旁路不會與每個 PSTN 閘道、IP-PBX 以及 SBC 相互溝通。</span><span class="sxs-lookup"><span data-stu-id="44658-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="44658-113">Microsoft 已測試一組的 PSTN 閘道與 Sbc 與認證合作夥伴，並已執行一些測試與 Cisco Ip-pbx。</span><span class="sxs-lookup"><span data-stu-id="44658-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="44658-114">媒體旁路只支援的產品和版本列在 Unified Communications Open Interoperability Program – 在 Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>。</span><span class="sxs-lookup"><span data-stu-id="44658-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="44658-115">後續步驟：選擇通用媒體旁路設定</span><span class="sxs-lookup"><span data-stu-id="44658-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="44658-116">在針對特定網站或服務對等端的主幹連線啟用媒體旁路後，使用下列內容可執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="44658-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="44658-117">[設定媒體旁路以始終略過中繼伺服器的 Lync Server 2013 中](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)所述，一律，啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="44658-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="44658-118">或者，設定媒體旁路使用網站與地區資訊，[設定媒體旁路使用網站與地區資訊的 Lync Server 2013 中的全域設定](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="44658-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="44658-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="44658-119">See Also</span></span>


[<span data-ttu-id="44658-120">設定與 Lync Server 2013 中的媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="44658-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="44658-121">關聯子網路與 Lync Server 2013 中的網路網站</span><span class="sxs-lookup"><span data-stu-id="44658-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="44658-122">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="44658-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="44658-123">媒體旁路和 Lync Server 2013 中的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="44658-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

