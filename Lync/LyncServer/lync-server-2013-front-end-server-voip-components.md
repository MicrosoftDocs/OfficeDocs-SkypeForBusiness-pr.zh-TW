---
title: Lync Server 2013：前端伺服器 VoIP 元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bab5751fc0291047f3795731f379d1e14f5f12b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="c3e1d-102">Lync Server 2013 的前端伺服器 VoIP 元件</span><span class="sxs-lookup"><span data-stu-id="c3e1d-102">Front End Server VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3e1d-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c3e1d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c3e1d-104">位於前端伺服器的 VoIP 元件如下所示：</span><span class="sxs-lookup"><span data-stu-id="c3e1d-104">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="c3e1d-105">翻譯服務</span><span class="sxs-lookup"><span data-stu-id="c3e1d-105">Translation Service</span></span>

  - <span data-ttu-id="c3e1d-106">入站路由元件</span><span class="sxs-lookup"><span data-stu-id="c3e1d-106">Inbound Routing component</span></span>

  - <span data-ttu-id="c3e1d-107">輸出路由元件</span><span class="sxs-lookup"><span data-stu-id="c3e1d-107">Outbound Routing component</span></span>

  - <span data-ttu-id="c3e1d-108">Exchange UM 路由元件</span><span class="sxs-lookup"><span data-stu-id="c3e1d-108">Exchange UM Routing component</span></span>

  - <span data-ttu-id="c3e1d-109">Intercluster 路由元件</span><span class="sxs-lookup"><span data-stu-id="c3e1d-109">Intercluster Routing component</span></span>

  - [<span data-ttu-id="c3e1d-110">Lync Server 2013 中的中繼伺服器元件</span><span class="sxs-lookup"><span data-stu-id="c3e1d-110">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="c3e1d-111">翻譯服務</span><span class="sxs-lookup"><span data-stu-id="c3e1d-111">Translation Service</span></span>

<span data-ttu-id="c3e1d-112">翻譯服務是一個伺服器元件，負責根據管理員所定義的正常化規則，將撥入的號碼翻譯成 E. 164 格式或其他格式。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-112">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator.</span></span> <span data-ttu-id="c3e1d-113">如果您的組織使用的是私人編號系統，或使用不支援 E. 164 的閘道或 PBX，翻譯服務可以翻譯為 E.i 以外的格式。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-113">The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="c3e1d-114">入站路由元件</span><span class="sxs-lookup"><span data-stu-id="c3e1d-114">Inbound Routing Component</span></span>

<span data-ttu-id="c3e1d-115">入站路由元件會根據使用者在企業語音用戶端所指定的喜好設定，來處理來電的方式。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-115">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="c3e1d-116">如果使用者已設定，它也可協助代理人撥打及同時撥打。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-116">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="c3e1d-117">例如，使用者指定是否已轉寄未接聽的通話，或只是登入通知。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-117">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="c3e1d-118">如果已啟用 [來電轉接]，使用者可以指定是否應將無應答通話轉寄至另一個號碼，或轉接到已設定為提供呼叫應答的 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-118">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="c3e1d-119">入站路由元件預設會安裝在所有標準版伺服器和前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-119">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="c3e1d-120">輸出路由元件</span><span class="sxs-lookup"><span data-stu-id="c3e1d-120">Outbound Routing Component</span></span>

<span data-ttu-id="c3e1d-121">輸出路由元件會將呼叫傳送到 PBX 或 PSTN 目的地。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-121">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="c3e1d-122">它會將呼叫授權規則（由使用者的語音原則所定義）套用至呼叫者，並決定路由每個通話的最佳 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-122">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="c3e1d-123">在所有標準版伺服器和前端伺服器上，預設會安裝輸出路由元件。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-123">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="c3e1d-124">輸出路由元件所使用的路由邏輯，是根據組織的需求，由網路或電話系統管理員設定的大型測量。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-124">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="c3e1d-125">Exchange UM 路由元件</span><span class="sxs-lookup"><span data-stu-id="c3e1d-125">Exchange UM Routing Component</span></span>

<span data-ttu-id="c3e1d-126">Exchange UM 路由元件會處理 Lync Server 與執行 Exchange 整合通訊（UM）的伺服器之間的路由，以整合 Lync Server 與整合的郵件功能。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-126">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="c3e1d-127">如果 Exchange UM 伺服器無法使用，Exchange UM 路由元件也會處理經由 PSTN 的語音信箱重新路由。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-127">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="c3e1d-128">如果您在分支網站上有企業語音使用者，而該使用者沒有指向中央網站的彈性 WAN 連結，您在分支網站部署的 Survivable 分支裝置會在 WAN 停機期間為分支使用者提供語音信箱留存能力。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-128">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="c3e1d-129">WAN 連結無法使用時，Survivable 分支裝置會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c3e1d-129">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="c3e1d-130">將未接聽的電話重新傳送到中央網站的 Exchange 整合訊息伺服器</span><span class="sxs-lookup"><span data-stu-id="c3e1d-130">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="c3e1d-131">提供使用者在 PSTN 上檢索語音信箱訊息的能力</span><span class="sxs-lookup"><span data-stu-id="c3e1d-131">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="c3e1d-132">將未接來電通知列隊，然後在還原 WAN 連結時，將其上傳到 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-132">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="c3e1d-133">若要啟用語音信箱重新路由，建議您的 Exchange 管理員將 Exchange UM 自動語音應答（AA）設定為僅接受郵件。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-133">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="c3e1d-134">如需這些功能的詳細資訊，請參閱[在 Lync server 2013 規劃 Exchange 整合訊息整合](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)，以及分別[規劃 lync server 2013 中的企業語音復原](lync-server-2013-planning-for-enterprise-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-134">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="c3e1d-135">Intercluster 路由元件</span><span class="sxs-lookup"><span data-stu-id="c3e1d-135">Intercluster Routing Component</span></span>

<span data-ttu-id="c3e1d-136">Intercluster 路由元件負責將呼叫路由到被叫方的主要註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-136">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="c3e1d-137">如果無法使用，元件會將呼叫路由到被叫方的備份註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-137">If that is unavailable, the component routes the call to the callee’s backup Registrar pool.</span></span> <span data-ttu-id="c3e1d-138">如果被呼叫者的主要和備份註冊器池無法在 IP 網路上使用，則 Intercluster 路由元件會將呼叫從 PSTN 重新路由到使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-138">If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="c3e1d-139">VoIP 所需的其他前端伺服器元件</span><span class="sxs-lookup"><span data-stu-id="c3e1d-139">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="c3e1d-140">常駐在前端伺服器或控制器上的其他元件，可提供 VoIP 的必要支援，但不是本身的 VoIP 元件，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="c3e1d-140">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="c3e1d-141">**使用者服務。**</span><span class="sxs-lookup"><span data-stu-id="c3e1d-141">**User Services.**</span></span> <span data-ttu-id="c3e1d-142">在每個撥入通話的目的地電話號碼上執行 [反向號碼查閱]，並將該號碼與目的地使用者的 SIP URI 相符。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-142">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="c3e1d-143">使用此資訊，入站路由元件會將呼叫分發給該使用者的已註冊 SIP 端點。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-143">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="c3e1d-144">[使用者服務] 是所有前端伺服器和控制器上的核心元件。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-144">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="c3e1d-145">**使用者複製程式。**</span><span class="sxs-lookup"><span data-stu-id="c3e1d-145">**User Replicator.**</span></span> <span data-ttu-id="c3e1d-146">從 Active Directory 網域服務提取使用者電話號碼，並將它們寫入 RTC 資料庫中的資料表，這些資料可供使用者服務和通訊錄服務器使用。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-146">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="c3e1d-147">使用者複製程式是所有前端伺服器上的核心元件。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-147">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="c3e1d-148">**通訊錄服務器。**</span><span class="sxs-lookup"><span data-stu-id="c3e1d-148">**Address Book Server.**</span></span> <span data-ttu-id="c3e1d-149">提供從 Active Directory 網域服務到 Lync Server 用戶端的全域通訊清單資訊。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-149">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="c3e1d-150">它也會從 RTC 資料庫中檢索使用者與連絡人資訊，並將資訊寫入通訊錄檔案，然後將檔案儲存在由 Lync 用戶端下載的共用資料夾中。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-150">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="c3e1d-151">通訊錄服務器會將資訊寫入 RTCAb 資料庫，由通訊錄網頁查詢服務用來回應來自 Microsoft Lync 2010 Mobile 的使用者搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-151">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="c3e1d-152">您也可以選擇將寫入 RTC 資料庫的企業使用者電話號碼標準化，以便在 Lync 中提供使用者連絡人。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-152">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="c3e1d-153">通訊錄服務預設會安裝在所有前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-153">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="c3e1d-154">預設會安裝通訊錄 Web 查詢服務與每個前端伺服器上的 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="c3e1d-154">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

