---
title: Lync Server 2013： Enterprise Voice 的部署指導方針
description: Lync Server 2013： Enterprise Voice 的部署指導方針。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cd847f674ad4b04698be0f54f8fbd490b13d689
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562119"
---
# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="3c2d2-103">Lync Server 2013 中 Enterprise Voice 的部署指導方針</span><span class="sxs-lookup"><span data-stu-id="3c2d2-103">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c2d2-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="3c2d2-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="3c2d2-105">本主題說明當您規劃部署 Lync Server 2013 和 Enterprise Voice 工作負載時，應考慮的必要條件和其他指導方針。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-105">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="3c2d2-106">部署必要條件</span><span class="sxs-lookup"><span data-stu-id="3c2d2-106">Deployment Prerequisites</span></span>

<span data-ttu-id="3c2d2-107">若要在部署企業語音時獲得最佳的體驗，請確定您的 IT 基礎結構、網路和系統都符合下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="3c2d2-107">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="3c2d2-108">Lync Server 2013 Standard Edition 或 Enterprise Edition 已安裝且可在您的網路上運作。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-108">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="3c2d2-109">所有 Edge Server 都會在周邊網路中部署並運作，包括具有 Access Edge service 的 Edge Server、A/V Edge service、Web 會議 Edge service 及反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-109">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="3c2d2-110">有一或多個使用者已建立並啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-110">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="3c2d2-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) 或最新的 service pack，或已安裝 Microsoft Exchange Server 2010。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-111">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="3c2d2-112">其中一種方式是將 Exchange 整合通訊 (UM) 與 Lync Server 整合，並提供豐富的通知及通話記錄資訊給用戶端端點。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-112">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="3c2d2-113">針對每個要啟用 Enterprise Voice 的使用者，會將唯一的主要電話號碼指派、正常化，並複製到 **msRTCSIP-line** 屬性。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-113">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c2d2-114">Lync Server 支援 e.164 號碼和非直接向內撥號 (已) 號碼。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-114">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="3c2d2-115">未做的號碼可以以 e.164 <STRONG> &lt; &gt; ; ext = &lt; 副檔名 &gt; </STRONG>或數位字串表示，必須是整個企業中的私人分機是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-115">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="3c2d2-116">例如，1001的私營號碼可以表示為 <STRONG>+ 1425550100、ext = 1001</STRONG>或 <STRONG>1001</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-116">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="3c2d2-117">當表示為 <STRONG>1001</STRONG>時，預期是整個企業中的此私人號碼是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-117">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="3c2d2-118">部署 Enterprise Voice 的系統管理員應為 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-118">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="3c2d2-119">至少已成功部署 Office Communicator 2007。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-119">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="3c2d2-120">若要使用此版本的新功能，請部署 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-120">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="3c2d2-121">使用 Microsoft 或協力廠商憑證授權單位 (CA) 基礎結構，部署及設定 MKI) 的 Managed key 基礎 (結構。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-121">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="3c2d2-122">安裝轉送伺服器的每一部電腦都必須是：</span><span class="sxs-lookup"><span data-stu-id="3c2d2-122">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="3c2d2-123">網域的成員伺服器，並為 Active Directory 網域服務做好準備。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-123">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="3c2d2-124">如需 Active Directory 網域服務的準備程式，請參閱部署檔中的 [準備 Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md) 。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-124">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="3c2d2-125">執行下列其中一個作業系統：</span><span class="sxs-lookup"><span data-stu-id="3c2d2-125">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="3c2d2-126">64位版本的 Windows Server 2008 Standard 作業系統</span><span class="sxs-lookup"><span data-stu-id="3c2d2-126">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="3c2d2-127">64位版本的 Windows Server 2008 企業版作業系統</span><span class="sxs-lookup"><span data-stu-id="3c2d2-127">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="3c2d2-128">若連到公用交換電話網路的連線 (PSTN) 或私營分公司 exchange (PBX) 是透過一種時間分割多工 (TDM) 連線，則可以部署一或多個 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-128">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment.</span></span> <span data-ttu-id="3c2d2-129"> (如果是透過 SIP 主幹連線，則不需要 PSTN 閘道。 ) </span><span class="sxs-lookup"><span data-stu-id="3c2d2-129">(If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="3c2d2-130">電源、網路或電話語音中斷</span><span class="sxs-lookup"><span data-stu-id="3c2d2-130">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="3c2d2-131">如果您所在位置出現電源、網路或電話語音中斷、中斷或其他問題，則語音、立即訊息、目前狀態，以及 Lync Server 及任何連接至 Lync Server 之裝置的其他功能都可能無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-131">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="3c2d2-132">Enterprise Voice 取決於伺服器可用性和語音用戶端和硬體可操作性</span><span class="sxs-lookup"><span data-stu-id="3c2d2-132">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="3c2d2-133">與 Lync Server 的語音通訊取決於伺服器軟體的可用性，以及連接至伺服器軟體的語音用戶端或硬體電話裝置是否可正常運作。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-133">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="3c2d2-134">存取緊急服務的替代方法</span><span class="sxs-lookup"><span data-stu-id="3c2d2-134">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="3c2d2-135">針對您安裝語音用戶端 (的位置（例如，執行 Lync 用戶端或 Lync Phone Edition 裝置) 的電腦，我們建議您維護備份選項，讓使用者呼叫緊急服務 (例如，911或 999) 以防電源故障、網路連線能力降低、電話語音中斷，或可能阻礙 Lync Server、Lync 或 Lync Phone Edition 裝置運作的其他問題。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-135">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="3c2d2-136">這類替代選項可以包含連線到標準公用交換電話網路 line 或蜂窩電話的電話。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-136">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="3c2d2-137">緊急電話和多行電話系統</span><span class="sxs-lookup"><span data-stu-id="3c2d2-137">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="3c2d2-138">使用多行電話系統 (MLTS) 可能受制于 U.S 州或聯邦法律或其他國家/地區的法律，也就是當來電者進入緊急服務時，需要 MLTS 提供來電者的電話號碼、分機和/或實體位置，以供來電者使用時 (例如，撥號緊急存取號碼，例如911或 999) 。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-138">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="3c2d2-139">在此版本中，Lync Server 可以設定為向緊急服務提供者提供來電者的實體位置，如在 [Lync Server 2013 中規劃緊急服務 (E9-1-1) ](lync-server-2013-planning-for-emergency-services-e9-1-1.md)所述。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-139">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="3c2d2-140">遵守 MLTS 法律是 Lync Server、Lync 用戶端和 Lync Phone Edition 裝置的買方的唯一責任。</span><span class="sxs-lookup"><span data-stu-id="3c2d2-140">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

