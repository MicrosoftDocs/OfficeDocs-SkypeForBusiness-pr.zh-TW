---
title: 'Lync Server 2013: Enterprise voice 的部署指導方針'
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
ms.openlocfilehash: 3fc2aee745a362e58003c62f483dda6c63ab244f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="044e7-102">Lync Server 2013 中的 Enterprise voice 的部署指導方針</span><span class="sxs-lookup"><span data-stu-id="044e7-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="044e7-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="044e7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="044e7-104">本主題說明先決條件和其他您計劃要部署 Lync Server 2013 和 Enterprise Voice 工作負載時所應考量的指導方針。</span><span class="sxs-lookup"><span data-stu-id="044e7-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="044e7-105">部署必要條件</span><span class="sxs-lookup"><span data-stu-id="044e7-105">Deployment Prerequisites</span></span>

<span data-ttu-id="044e7-106">部署 Enterprise Voice 時獲得最佳體驗，請確認您的 IT 基礎結構、 網路和系統都符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="044e7-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="044e7-107">Lync Server 2013 Standard Edition 或 Enterprise Edition 已安裝且正在運作您網路上。</span><span class="sxs-lookup"><span data-stu-id="044e7-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="044e7-108">所有 Edge Server 都都已部署、 作業在周邊網路，包括 Edge Server 與 Access Edge service，A / V Edge service、 Web Conferencing Edge service 和反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="044e7-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="044e7-109">已建立並啟用 Lync Server 的一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="044e7-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="044e7-110">已安裝 Microsoft Exchange Server 2007 Service Pack 1 (SP1) 或最新的 service pack 或 Microsoft Exchange Server 2010。</span><span class="sxs-lookup"><span data-stu-id="044e7-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="044e7-111">其中，才能將 Exchange 整合通訊 (UM) 整合搭配 Lync Server，以及用於提供豐富的通知及通話記錄資訊用戶端端點。</span><span class="sxs-lookup"><span data-stu-id="044e7-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="044e7-112">唯一的主要電話號碼已指定正規化，並複製到每個使用者啟用 Enterprise voice **msrtcsip-line**屬性。</span><span class="sxs-lookup"><span data-stu-id="044e7-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="044e7-113">Lync Server 支援 E.164 號碼和非-直接向內撥號 DID 號碼。</span><span class="sxs-lookup"><span data-stu-id="044e7-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="044e7-114">非-DID 號碼可以表示格式<STRONG>&lt;E.164&gt;; ext =&lt;分機&gt;</STRONG>或數字，整個企業的私用的分機號碼是唯一的需求與的字串。</span><span class="sxs-lookup"><span data-stu-id="044e7-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="044e7-115">例如，以表示 1001年專用號碼<STRONG>+1425550100; ext = 1001年</STRONG>，或為<STRONG>1001年</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="044e7-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="044e7-116">代表<STRONG>1001年</STRONG>，預期時，此私用的數字是唯一的整個企業。</span><span class="sxs-lookup"><span data-stu-id="044e7-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="044e7-117">部署 Enterprise Voice 的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="044e7-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="044e7-118">在最低限度下，Office Communicator 2007 是成功部署。</span><span class="sxs-lookup"><span data-stu-id="044e7-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="044e7-119">若要使用功能新增至這個版本，就會部署 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="044e7-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="044e7-120">受管理的公開金鑰基礎結構 (MKI) 是部署和設定，使用 Microsoft 或協力廠商憑證授權單位 (CA) 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="044e7-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="044e7-121">必須為每一部電腦安裝中繼伺服器：</span><span class="sxs-lookup"><span data-stu-id="044e7-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="044e7-122">成員伺服器的網域，並為 Active Directory 網域服務準備。</span><span class="sxs-lookup"><span data-stu-id="044e7-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="044e7-123">如需 Active Directory 網域服務準備程序，請參閱部署文件中的[準備 Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) 。</span><span class="sxs-lookup"><span data-stu-id="044e7-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="044e7-124">執行下列其中一個下列作業系統：</span><span class="sxs-lookup"><span data-stu-id="044e7-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="044e7-125">Windows Server 2008 Standard 作業系統 64 位元版本</span><span class="sxs-lookup"><span data-stu-id="044e7-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="044e7-126">Windows Server 2008 Enterprise 作業系統 64 位元版本</span><span class="sxs-lookup"><span data-stu-id="044e7-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="044e7-127">利用時間部門多工 (TDM) 連線至公用交換的電話網路 (PSTN) 或專用交換機 (PBX) 的連線時，一或多個 PSTN 閘道可供部署。</span><span class="sxs-lookup"><span data-stu-id="044e7-127">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment.</span></span> <span data-ttu-id="044e7-128">（如果透過 SIP 主幹連線，PSTN 閘道不是必要。）</span><span class="sxs-lookup"><span data-stu-id="044e7-128">(If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="044e7-129">電力、 網路或電話服務中斷</span><span class="sxs-lookup"><span data-stu-id="044e7-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="044e7-130">如果沒有中斷、 干擾或其他降低電力、 網路或電話服務所在位置，語音、 立即訊息、 目前狀態和 Lync Server 與任何裝置連線至 Lync Server 的其他功能可能無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="044e7-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="044e7-131">Enterprise Voice 取決於伺服器的可用性和 Voip 用戶端與硬體的可操作性</span><span class="sxs-lookup"><span data-stu-id="044e7-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="044e7-132">語音通訊與 Lync Server 取決於伺服器軟體的可用性，以及語音用戶端或硬體電話裝置連接到伺服器軟體的正常運作。</span><span class="sxs-lookup"><span data-stu-id="044e7-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="044e7-133">連絡緊急服務的替代方法</span><span class="sxs-lookup"><span data-stu-id="044e7-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="044e7-134">針對您安裝的語音用戶端 （例如，電腦執行 Lync 用戶端或 Lync Phone Edition 裝置） 這些位置，我們建議您電源失敗的情況下，維護備份的選項，讓使用者呼叫緊急服務 （例如，911 或 999）網路連線效能下降、 電話服務中斷或其他問題，可能會抑制 Lync 伺服器、 Lync 或 Lync Phone Edition 裝置的作業。</span><span class="sxs-lookup"><span data-stu-id="044e7-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="044e7-135">這類替代選項可以包括標準的公用交換的電話網路線路或行動電話連線的電話。</span><span class="sxs-lookup"><span data-stu-id="044e7-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="044e7-136">緊急救援電話與多線路電話系統</span><span class="sxs-lookup"><span data-stu-id="044e7-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="044e7-137">多行的電話系統 (MLTS) 使用可能需支付美國狀態或聯邦法律或其他國家/地區需要提供來電者的電話號碼、 副檔名及/或適用的緊急服務的實體位置時，來電者 MLTS 的法律撥至緊急服務 （例如，例如 911 或 999 緊急存取號碼來撥號時）。</span><span class="sxs-lookup"><span data-stu-id="044e7-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="044e7-138">在此版本中，可以設定 Lync Server[規劃緊急服務 (E9-1-1)，在 [Lync Server 2013 ](lync-server-2013-planning-for-emergency-services-e9-1-1.md)中所述，提供發話者的實體位置與緊急服務提供者。</span><span class="sxs-lookup"><span data-stu-id="044e7-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="044e7-139">與 MLTS 法律合規性是唯一的 Lync Server，Lync 用戶端和 Lync Phone Edition 裝置購買者的責任。</span><span class="sxs-lookup"><span data-stu-id="044e7-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

