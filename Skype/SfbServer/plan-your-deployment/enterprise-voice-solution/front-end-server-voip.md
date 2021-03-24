---
title: 適用于商務用 Skype Server 的前端伺服器 VoIP 元件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 瞭解位於商務用 Skype Server 的前端伺服器上的 Enterprise Voice 元件，包括轉譯服務和各種路由元件。
ms.openlocfilehash: 830f54e59e0d2135e3748fd03474b19e22741136
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101489"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a><span data-ttu-id="fecfe-103">適用于商務用 Skype Server 的前端伺服器 VoIP 元件</span><span class="sxs-lookup"><span data-stu-id="fecfe-103">Front End Server VoIP components for Skype for Business Server</span></span>

<span data-ttu-id="fecfe-104">瞭解位於商務用 Skype Server 的前端伺服器上的 Enterprise Voice 元件，包括轉譯服務和各種路由元件。</span><span class="sxs-lookup"><span data-stu-id="fecfe-104">Learn about the Enterprise Voice components that are located on Front End Servers in Skype for Business Server, including translation service and various routing components.</span></span>

<span data-ttu-id="fecfe-105">前端伺服器上的 VoIP 元件如下：</span><span class="sxs-lookup"><span data-stu-id="fecfe-105">The VoIP components located on Front End Servers are as follows:</span></span>

- <span data-ttu-id="fecfe-106">轉譯服務</span><span class="sxs-lookup"><span data-stu-id="fecfe-106">Translation Service</span></span>

- <span data-ttu-id="fecfe-107">輸入路由元件</span><span class="sxs-lookup"><span data-stu-id="fecfe-107">Inbound Routing component</span></span>

- <span data-ttu-id="fecfe-108">輸出路由元件</span><span class="sxs-lookup"><span data-stu-id="fecfe-108">Outbound Routing component</span></span>

- <span data-ttu-id="fecfe-109">Exchange UM 路由元件</span><span class="sxs-lookup"><span data-stu-id="fecfe-109">Exchange UM Routing component</span></span>

- <span data-ttu-id="fecfe-110">Intercluster 路由元件</span><span class="sxs-lookup"><span data-stu-id="fecfe-110">Intercluster Routing component</span></span>

- [<span data-ttu-id="fecfe-111">商務用 Skype Server 中的轉送伺服器元件</span><span class="sxs-lookup"><span data-stu-id="fecfe-111">Mediation Server component in Skype for Business Server</span></span>](mediation-server.md)

## <a name="translation-service"></a><span data-ttu-id="fecfe-112">轉譯服務</span><span class="sxs-lookup"><span data-stu-id="fecfe-112">Translation Service</span></span>

<span data-ttu-id="fecfe-p101">「轉譯服務」是負責根據系統管理員定義的正規化規則，將撥打的號碼轉譯成 E.164 格式或其他格式的伺服器元件。如果您的組織使用私人編號系統或使用不支援 E.164 的閘道或 PBX，則「轉譯服務」可以轉譯為 E.164 以外的其他格式。</span><span class="sxs-lookup"><span data-stu-id="fecfe-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

## <a name="inbound-routing-component"></a><span data-ttu-id="fecfe-115">輸入路由元件</span><span class="sxs-lookup"><span data-stu-id="fecfe-115">Inbound Routing Component</span></span>

<span data-ttu-id="fecfe-116">輸入路由元件主要會根據使用者在其 Enterprise Voice 用戶端所指定的喜好設定來處理來電。</span><span class="sxs-lookup"><span data-stu-id="fecfe-116">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="fecfe-117">它也有助於代理人響鈴與同時響鈴 (若使用者已設定) 的使用。</span><span class="sxs-lookup"><span data-stu-id="fecfe-117">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="fecfe-118">例如，使用者可指定未應答的電話是否要轉接，還是只記錄下來進行通知。</span><span class="sxs-lookup"><span data-stu-id="fecfe-118">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="fecfe-119">如果已啟用來電轉接，使用者可以指定是否要將未應答的呼叫轉寄到另一個號碼，或是已設定為提供呼叫應答的 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="fecfe-119">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="fecfe-120">預設會在所有 Standard Edition server 和前端伺服器上安裝傳入路由元件。</span><span class="sxs-lookup"><span data-stu-id="fecfe-120">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

## <a name="outbound-routing-component"></a><span data-ttu-id="fecfe-121">輸出路由元件</span><span class="sxs-lookup"><span data-stu-id="fecfe-121">Outbound Routing Component</span></span>

<span data-ttu-id="fecfe-122">輸出路由元件會將電話路由傳送到 PBX 或 PSTN 目的地。</span><span class="sxs-lookup"><span data-stu-id="fecfe-122">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="fecfe-123">它會依照使用者的語音原則所定義的呼叫授權規則套用至來電者，並決定用於路由傳送每個通話的最佳 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="fecfe-123">It applies call authorization rules, as defined by the user's voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="fecfe-124">預設會在所有 Standard Edition server 和前端伺服器上安裝輸出路由元件。</span><span class="sxs-lookup"><span data-stu-id="fecfe-124">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="fecfe-125">輸出路由元件所使用的路由邏輯會使用大的度量 (由網路或電話語音管理員根據其組織的需求而設定)。</span><span class="sxs-lookup"><span data-stu-id="fecfe-125">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="fecfe-126">Exchange UM 路由元件</span><span class="sxs-lookup"><span data-stu-id="fecfe-126">Exchange UM Routing Component</span></span>

<span data-ttu-id="fecfe-127">Exchange UM 路由元件會處理在商務用 Skype 伺服器與執行 Exchange 整合通訊 (UM) 之間的路由，以整合商務用 Skype Server 與整合通訊功能。</span><span class="sxs-lookup"><span data-stu-id="fecfe-127">The Exchange UM routing component handles routing between Skype for Business Server and servers running Exchange Unified Messaging (UM), to integrate Skype for Business Server with Unified Messaging features.</span></span>

<span data-ttu-id="fecfe-128">Exchange UM 路由元件也會在 Exchange UM 伺服器無法使用時，處理透過 PSTN 的語音信箱重新路由。</span><span class="sxs-lookup"><span data-stu-id="fecfe-128">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="fecfe-129">如果您有在分支網站上的 Enterprise Voice 使用者，而該分支網站沒有指向中央網站的彈性 WAN 連結，您在分支網站上部署的 Survivable 分支裝置會在 WAN 中斷期間為分支使用者提供語音信箱留存能力。</span><span class="sxs-lookup"><span data-stu-id="fecfe-129">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="fecfe-130">當 WAN 連結無法使用時，Survivable 分支裝置會執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="fecfe-130">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

- <span data-ttu-id="fecfe-131">透過 PSTN，將未接聽的電話重新路由至中央網站的 Exchange Unified Messaging 伺服器</span><span class="sxs-lookup"><span data-stu-id="fecfe-131">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

- <span data-ttu-id="fecfe-132">提供使用者透過 PSTN 擷取語音信箱訊息的能力</span><span class="sxs-lookup"><span data-stu-id="fecfe-132">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

- <span data-ttu-id="fecfe-133">將未接來電通知排入佇列，然後在 WAN 連結恢復時將通知上傳至 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="fecfe-133">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="fecfe-134">為了啟用語音信箱重新路由，我們建議您的 Exchange 管理員設定 Exchange UM 自動語音應答 (AA) 僅接受郵件。</span><span class="sxs-lookup"><span data-stu-id="fecfe-134">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="fecfe-135">如需這些功能的詳細資訊，請分別參閱＜[On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration)＞及＜[Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)＞。</span><span class="sxs-lookup"><span data-stu-id="fecfe-135">For details about these features, see [On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration) and [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency), respectively.</span></span>

## <a name="intercluster-routing-component"></a><span data-ttu-id="fecfe-136">Intercluster 路由元件</span><span class="sxs-lookup"><span data-stu-id="fecfe-136">Intercluster Routing Component</span></span>

<span data-ttu-id="fecfe-137">Intercluster 路由元件負責將通話路由傳送至被呼叫者的主要註冊集區。</span><span class="sxs-lookup"><span data-stu-id="fecfe-137">The Intercluster routing component is responsible for routing calls to the callee's primary Registrar pool.</span></span> <span data-ttu-id="fecfe-138">如果無法使用該元件，該元件會將通話路由傳送給被呼叫者的備份報名者集區。</span><span class="sxs-lookup"><span data-stu-id="fecfe-138">If that is unavailable, the component routes the call to the callee's backup Registrar pool.</span></span> <span data-ttu-id="fecfe-139">如果被呼叫者的主要和備份報名者集區無法透過 IP 網路到達，Intercluster 路由元件會將通話透過 PSTN 重新路由至使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="fecfe-139">If the callee's primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user's telephone number.</span></span>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="fecfe-140">VoIP 所需的其他前端伺服器元件</span><span class="sxs-lookup"><span data-stu-id="fecfe-140">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="fecfe-141">位於前端伺服器或 Director 上的其他元件，可為 VoIP 提供必要的支援，但不是本身 VoIP 元件，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="fecfe-141">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

- <span data-ttu-id="fecfe-142">**使用者服務。**</span><span class="sxs-lookup"><span data-stu-id="fecfe-142">**User Services.**</span></span> <span data-ttu-id="fecfe-143">針對每一來電的目的地電話號碼執行反向號碼查閱，並將該號碼與目的地使用者的 SIP URI 相比對。</span><span class="sxs-lookup"><span data-stu-id="fecfe-143">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="fecfe-144">使用此資訊，輸入路由元件會將通話散佈給該使用者已註冊的 SIP 端點。</span><span class="sxs-lookup"><span data-stu-id="fecfe-144">Using this information, the Inbound Routing component distributes the call to that user's registered SIP endpoints.</span></span> <span data-ttu-id="fecfe-145">使用者服務是所有前端伺服器及 Director 上的核心元件。</span><span class="sxs-lookup"><span data-stu-id="fecfe-145">User Services is a core component on all Front End Servers and Directors.</span></span>

- <span data-ttu-id="fecfe-146">**使用者複寫器。**</span><span class="sxs-lookup"><span data-stu-id="fecfe-146">**User Replicator.**</span></span> <span data-ttu-id="fecfe-147">從 Active Directory 網域服務析取使用者電話號碼，並將它們寫入 RTC 資料庫中的表格，以供使用者服務和通訊錄服務器使用。</span><span class="sxs-lookup"><span data-stu-id="fecfe-147">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="fecfe-148">使用者複製器是所有前端伺服器上的核心元件。</span><span class="sxs-lookup"><span data-stu-id="fecfe-148">User Replicator is a core component on all Front End Servers.</span></span>

- <span data-ttu-id="fecfe-149">**Address Book Server。**</span><span class="sxs-lookup"><span data-stu-id="fecfe-149">**Address Book Server.**</span></span> <span data-ttu-id="fecfe-150">將 Active Directory 網域服務的全域通訊清單資訊提供給商務用 Skype Server 用戶端。</span><span class="sxs-lookup"><span data-stu-id="fecfe-150">Provides global address list information from Active Directory Domain Services to Skype for Business Server clients.</span></span> <span data-ttu-id="fecfe-151">它也會從 RTC 資料庫中取得使用者和連絡人資訊，並將資訊寫入通訊錄檔案，然後將檔案儲存在由商務用 Skype 用戶端下載之共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="fecfe-151">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Skype for Business clients.</span></span> <span data-ttu-id="fecfe-152">Address Book Server 會將資訊寫入 RTCAb 資料庫，而通訊錄 Web 查詢服務會使用該資訊，回應商務用 Skype mobile 的使用者搜尋查詢。</span><span class="sxs-lookup"><span data-stu-id="fecfe-152">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Skype for Business mobile.</span></span> <span data-ttu-id="fecfe-153">它會選擇性地正常化為了在商務用 Skype 中布建使用者連絡人而寫入 RTC 資料庫的企業使用者電話號碼。</span><span class="sxs-lookup"><span data-stu-id="fecfe-153">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Skype for Business.</span></span> <span data-ttu-id="fecfe-154">預設會在所有前端伺服器上安裝通訊錄服務。</span><span class="sxs-lookup"><span data-stu-id="fecfe-154">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="fecfe-155">預設會隨每一部前端伺服器上的 Web 服務安裝通訊錄 Web 查詢服務。</span><span class="sxs-lookup"><span data-stu-id="fecfe-155">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>