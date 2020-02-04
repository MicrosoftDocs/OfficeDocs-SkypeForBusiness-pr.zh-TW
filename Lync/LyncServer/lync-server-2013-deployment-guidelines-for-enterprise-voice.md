---
title: Lync Server 2013：Enterprise Voice 的部署指導方針
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
ms.openlocfilehash: 221c09fc5dadda267baad35f4784c22cc4f3c9c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="32287-102">Lync Server 2013 中 Enterprise Voice 的部署指導方針</span><span class="sxs-lookup"><span data-stu-id="32287-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32287-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="32287-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="32287-104">本主題說明當您規劃要部署 Lync Server 2013 和企業語音工作負載時，要考慮的先決條件及其他指導方針。</span><span class="sxs-lookup"><span data-stu-id="32287-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="32287-105">部署先決條件</span><span class="sxs-lookup"><span data-stu-id="32287-105">Deployment Prerequisites</span></span>

<span data-ttu-id="32287-106">若要在部署企業語音時獲得最佳體驗，請確定您的 IT 基礎結構、網路和系統符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="32287-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="32287-107">Lync Server 2013 標準版或 Enterprise Edition 已安裝並在您的網路上運作。</span><span class="sxs-lookup"><span data-stu-id="32287-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="32287-108">所有邊緣伺服器都是在您的周邊網路中部署和運作，包括具有存取邊緣服務的邊緣伺服器、A/V 邊緣服務、網頁會議 Edge 服務，以及反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="32287-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="32287-109">已為 Lync Server 建立並啟用一或多位使用者。</span><span class="sxs-lookup"><span data-stu-id="32287-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="32287-110">[Microsoft Exchange Server 2007 Service Pack 1 （SP1）] 或 [最新 Service pack] 或 [Microsoft Exchange Server 2010 已安裝]。</span><span class="sxs-lookup"><span data-stu-id="32287-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="32287-111">這其中一個是將 Exchange 整合通訊（UM）與 Lync Server 整合所需，並提供豐富的通知及通話記錄資訊給用戶端端點。</span><span class="sxs-lookup"><span data-stu-id="32287-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="32287-112">已針對要啟用企業語音的每位使用者，將唯一的主要電話號碼指派、標準化，並複製到**msRTCSIP**屬性。</span><span class="sxs-lookup"><span data-stu-id="32287-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32287-113">Lync Server 支援 E. 164 個數字和非直接撥入式撥號（已有）號碼。</span><span class="sxs-lookup"><span data-stu-id="32287-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="32287-114">非使用中的數位可以用<STRONG> &lt;E. 164&gt;; ext =&lt;extension&gt; </STRONG>或數位字串來表示，且要求私人副檔名在整個企業中都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="32287-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="32287-115">例如，1001的私用號碼可以表示為<STRONG>+ 1425550100; ext = 1001</STRONG>，或<STRONG>1001</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="32287-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="32287-116">當表示為<STRONG>1001</STRONG>時，預期是該私人數位在整個企業中都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="32287-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="32287-117">部署企業語音的系統管理員應該是 RTCUniversalServerAdmins 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="32287-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="32287-118">Office Communicator 2007 至少已成功部署。</span><span class="sxs-lookup"><span data-stu-id="32287-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="32287-119">若要使用此版本的新功能，請部署 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="32287-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="32287-120">管理的金鑰結構（MKI）是使用 Microsoft 或協力廠商憑證授權單位（CA）基礎結構來部署和設定。</span><span class="sxs-lookup"><span data-stu-id="32287-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="32287-121">安裝轉送伺服器的每台電腦都必須是：</span><span class="sxs-lookup"><span data-stu-id="32287-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="32287-122">網域的成員伺服器，並準備好使用 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="32287-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="32287-123">如需 Active Directory 網域服務的準備程式，請參閱在部署檔中[為 Lync Server 2013 準備 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="32287-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="32287-124">執行下列其中一個作業系統：</span><span class="sxs-lookup"><span data-stu-id="32287-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="32287-125">Windows Server 2008 標準作業系統的64位版本</span><span class="sxs-lookup"><span data-stu-id="32287-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="32287-126">Windows Server 2008 Enterprise 作業系統的64位版本</span><span class="sxs-lookup"><span data-stu-id="32287-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="32287-127">如果連線到公用交換式電話網絡（PSTN）或私人分支交換（PBX）是透過時間除法複用（TDM）連線，則可以使用一或多個 PSTN 閘道進行部署。</span><span class="sxs-lookup"><span data-stu-id="32287-127">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment.</span></span> <span data-ttu-id="32287-128">（如果連線是透過 SIP 幹線來進行，則不需要 PSTN 閘道。）</span><span class="sxs-lookup"><span data-stu-id="32287-128">(If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="32287-129">電源、網路或電話語音中斷</span><span class="sxs-lookup"><span data-stu-id="32287-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="32287-130">如果您所在位置有停機、中斷或其他電源、網路或電話語音的下降，請語音、立即訊息、目前狀態，以及 Lync Server 和任何連接至 Lync Server 的裝置都可能無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="32287-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="32287-131">企業語音依賴伺服器可用性與語音用戶端及硬體可操作性</span><span class="sxs-lookup"><span data-stu-id="32287-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="32287-132">使用 Lync Server 的語音通訊，取決於伺服器軟體的可用性，以及連線到伺服器軟體的語音用戶端或硬體電話裝置是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="32287-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="32287-133">存取緊急服務的替代方法</span><span class="sxs-lookup"><span data-stu-id="32287-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="32287-134">針對您安裝語音用戶端的位置（例如，執行 Lync 用戶端或 Lync 手機版裝置的電腦），建議您維護備份選項，讓使用者呼叫緊急服務（例如，911或999）以防電源故障、網路連線能力下降、電話語音中斷或其他可能會阻礙 Lync Server、Lync 或 Lync Phone Edition 裝置運作的問題。</span><span class="sxs-lookup"><span data-stu-id="32287-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="32287-135">這類替代選項可以包含連線至標準公用交換電話網絡線路或手機的電話。</span><span class="sxs-lookup"><span data-stu-id="32287-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="32287-136">緊急通話和多行電話系統</span><span class="sxs-lookup"><span data-stu-id="32287-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="32287-137">使用多行電話系統（MLTS）可能受限於美國州或聯邦法律，或其他國家/地區的法律，需要 MLTS 來提供來電者的電話號碼、延伸及/或物理位置給緊急服務（例如，當您撥打緊急存取號碼，例如911或999）。</span><span class="sxs-lookup"><span data-stu-id="32287-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="32287-138">在這個版本中，Lync Server 可以設定為向緊急服務提供者提供來電者的物理位置，如在[Lync Server 2013 的緊急服務（E9-1）中](lync-server-2013-planning-for-emergency-services-e9-1-1.md)所述。</span><span class="sxs-lookup"><span data-stu-id="32287-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="32287-139">遵守 MLTS 法律是 Lync Server、Lync 用戶端和 Lync Phone Edition 裝置的購買者的唯一責任。</span><span class="sxs-lookup"><span data-stu-id="32287-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

