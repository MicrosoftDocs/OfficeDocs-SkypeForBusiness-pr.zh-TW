---
title: Lync Server 2013： E9-1-1 簡介
description: Lync Server 2013： E9-1-1 簡介。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fa13d8bfd1c273e8cbbb1d70f1fb3d733ac6167
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571899"
---
# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="1011c-103">Lync Server 2013 中的 E9-1-1 簡介</span><span class="sxs-lookup"><span data-stu-id="1011c-103">Overview of E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1011c-104">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="1011c-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="1011c-105">Microsoft Lync Server 2013 支援 E9-1-1) 從 Lync 用戶端和 Lync Phone Edition 裝置呼叫的增強 9-1-1 (。</span><span class="sxs-lookup"><span data-stu-id="1011c-105">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="1011c-106">當您設定 Lync Server 的 E9-1-1 時，來自 Lync 2013 或 Lync Phone Edition 的緊急通話會包含緊急回應位置 (ERL) 位置資訊服務資料庫中的資訊。</span><span class="sxs-lookup"><span data-stu-id="1011c-106">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="1011c-107">Erl 是由市政 (所組成，也就是街道) 位址及其他資訊，可協助識別 office 大樓和其他多租戶設施中的更精確位置。</span><span class="sxs-lookup"><span data-stu-id="1011c-107">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="1011c-108">當使用者進行緊急通話時，Lync Server 會透過轉送伺服器將通話音訊路由傳送至 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="1011c-108">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="1011c-109">E9-1-1 服務提供者會使用來電者的市政位址，將通話路由傳送至公用安全回應點 (PSAP) 會提供給來電者的位置，並以緊急服務查詢金鑰 (ESQK 一起) 傳送，PSAP 用來查閱來電者的 ERL。</span><span class="sxs-lookup"><span data-stu-id="1011c-109">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="1011c-110">Lync Server 支援兩種方法，可將緊急通話路由傳送至 E9-1-1 服務提供者：</span><span class="sxs-lookup"><span data-stu-id="1011c-110">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="1011c-111">E9-1-1 服務提供者的會話初始通訊協定 (SIP) 主幹連接</span><span class="sxs-lookup"><span data-stu-id="1011c-111">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="1011c-112"> (PSTN) E9-1-1-1-1-1-1-1-1-1-1-1-1-1-1-1 服務提供者)  (</span><span class="sxs-lookup"><span data-stu-id="1011c-112">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="1011c-113">當您使用 SIP 主幹 E9-1-1 服務提供者時，會將 Erl 新增至位置資訊服務資料庫，然後依照主要街道位址指南 (MSAG) （由 E9-1-1 服務提供者所維護）來驗證位置。</span><span class="sxs-lookup"><span data-stu-id="1011c-113">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="1011c-114">如果 E9-1-1 服務提供者收到的來電沒有位置資訊，或其位置尚未針對 MSAG 驗證，請 E9-1-1 服務提供者會將通話路由傳送到國內/地區緊急通話回應中心 (ECRC) ，其專為訓練有素的人員，其口頭取得來電者的位置，並手動將通話路由到適當的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="1011c-114">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="1011c-115"> (某些 SIP 主幹 E9-1-1 服務提供者也會為客戶提供 PSTN direct 向內撥號 (是否) 號碼傳送至 ECRC，如果 SIP 主幹因任何原因而失敗，則會提供另一種路由9-1-1 呼叫的方式。 ) </span><span class="sxs-lookup"><span data-stu-id="1011c-115">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="1011c-116">不同于時間分割多工 (TDM) 和 IP 型專用交換機 (PBX) 電話（具有固定位置），Lync 端點可以是非常行動的。</span><span class="sxs-lookup"><span data-stu-id="1011c-116">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="1011c-117">當您部署 E9-1-1 功能時，Lync Server 會協助確保無論來電者位於何處，緊急呼叫都可以路由傳送到叫用來電者位置的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="1011c-117">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="1011c-118">例如，如果使用者的主辦公室位於 Redmond，但使用者在 Wichita 中從分公司的電腦撥打緊急電話，則 Kansas 會在 SIP 主幹或 PSTN 型 E9-1-1-1-1-1-1-1-1-1-1-1 服務提供者將通話路由傳送至 Wichita 中的 PSAP</span><span class="sxs-lookup"><span data-stu-id="1011c-118">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="1011c-119">當您使用 ELIN 閘道時，您也可以將 Erl 新增至位置資訊服務資料庫，但也包含每個位置的 ELIN 號碼。</span><span class="sxs-lookup"><span data-stu-id="1011c-119">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="1011c-120">ELIN 號碼會在緊急通話期間成為緊急電話號碼。</span><span class="sxs-lookup"><span data-stu-id="1011c-120">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="1011c-121">接著，您必須確定 PSTN 電信公司將 Elin 上傳至自動位置識別， (阿裡) 資料庫。</span><span class="sxs-lookup"><span data-stu-id="1011c-121">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1011c-122">Lync 連接的類比裝置無法從位置資訊服務接收位置資訊，或將位置資訊傳送至 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="1011c-122">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="1011c-123">如果您使用 SIP 主幹 E9-1-1 服務提供者選項，且需要從類比電話支援 E9-1-1，您有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="1011c-123">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="1011c-124"><STRONG>傳統 PS-ALI 選項</STRONG> &nbsp; &nbsp; &nbsp;如果您在每個部署類比電話的網站上都有本機 PSTN 閘道，且每個類比電話都有，您可以直接布建類比裝置的位置，以專用交換機/自動位置識別 (PS-ALI) 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="1011c-124"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="1011c-125">在此情況下，您可以設定巧盡心思構建的 Lync 語音原則，並將它們指派給類比裝置連絡人物件，使來自這些電話的 E9-1-1 呼叫直接路由傳送至 (服務提供者的 PSTN 提供者，而不是將通話路由傳送至 E9-1-1 服務提供者的 SIP 主幹) 。</span><span class="sxs-lookup"><span data-stu-id="1011c-125">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="1011c-126">當緊急通話時，與 PSTN 主幹相關聯之 PS-ALI 提供者的資料庫，會將每個類比電話的執行對應至實體位置，並提供此 PSAP 的位置。</span><span class="sxs-lookup"><span data-stu-id="1011c-126">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="1011c-127">這些記錄必須隨 PS-ALI 服務提供者一起更新，每次行動電話至不同的 Erl。</span><span class="sxs-lookup"><span data-stu-id="1011c-127">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="1011c-128"><STRONG>E9-1-1 服務提供者選項</STRONG> &nbsp; &nbsp; &nbsp;您可以使用 E9-1-1 服務提供者註冊類比電話 DIDs 及其對應的 Erl （如果 E9-1-1 服務提供者支援此功能）。</span><span class="sxs-lookup"><span data-stu-id="1011c-128"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="1011c-129">如果提供者接收到來自 Lync Server 的呼叫，但該呼叫不包含 PIDF-LO 資料，則提供者可以查看是否有資料庫與呼叫方的執行號碼相符。</span><span class="sxs-lookup"><span data-stu-id="1011c-129">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="1011c-130">透過使用從其資料庫中取得的 ERL，提供者可以自動將緊急通話路由傳送到正確的 PSAP，PSAP 將會收到類比裝置和 ESQK 一起記錄的執行，讓 dispatcher 能夠查閱來電者的位置。</span><span class="sxs-lookup"><span data-stu-id="1011c-130">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="1011c-131">如果您使用 ELIN 閘道選項，且需要支援類比電話的 E9-1-1，您可以直接使用 PS-ALI 服務提供者布建類比裝置的位置，如上述第一個選項所述。</span><span class="sxs-lookup"><span data-stu-id="1011c-131">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.</span></span>



</div>

<span data-ttu-id="1011c-132">從 Lync Server 的觀點來看，E9-1-1 程式可以分為兩個階段：</span><span class="sxs-lookup"><span data-stu-id="1011c-132">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="1011c-133">階段1：取得位置</span><span class="sxs-lookup"><span data-stu-id="1011c-133">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="1011c-134">階段2：將緊急通話路由傳送至 E9-1-1 服務提供者</span><span class="sxs-lookup"><span data-stu-id="1011c-134">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="1011c-135">本節說明這些階段的運作方式。</span><span class="sxs-lookup"><span data-stu-id="1011c-135">This section describes how these stages work.</span></span>

<span data-ttu-id="1011c-136">如果您計畫將基礎結構設定為自動偵測用戶端位置，您必須先決定要用來將來電者對應至位置的網路元素。</span><span class="sxs-lookup"><span data-stu-id="1011c-136">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="1011c-137">如需可能選項的詳細資訊，請參閱 [在 Lync Server 2013 中定義用來判斷位置的網路元素](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)。</span><span class="sxs-lookup"><span data-stu-id="1011c-137">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1011c-138">本章節內容</span><span class="sxs-lookup"><span data-stu-id="1011c-138">In This Section</span></span>

  - [<span data-ttu-id="1011c-139">在 Lync Server 2013 中取得位置</span><span class="sxs-lookup"><span data-stu-id="1011c-139">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="1011c-140">在 Lync Server 2013 中使用 SIP 主幹路由傳送 E9-1-1 通話</span><span class="sxs-lookup"><span data-stu-id="1011c-140">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="1011c-141">在 Lync Server 2013 中使用 ELIN 閘道路由 E9-1-1 通話</span><span class="sxs-lookup"><span data-stu-id="1011c-141">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

