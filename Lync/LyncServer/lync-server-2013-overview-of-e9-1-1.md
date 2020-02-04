---
title: Lync Server 2013：E9-1-1 概觀
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
ms.openlocfilehash: 48b261ed0b173c85ccd076be14d65aa456558830
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="2656e-102">Lync Server 2013 中的 E9-1-1 概觀</span><span class="sxs-lookup"><span data-stu-id="2656e-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2656e-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="2656e-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="2656e-104">Microsoft Lync Server 2013 支援從 Lync 用戶端和 Lync Phone Edition 裝置呼叫增強版9-1-1 （E9-1）。</span><span class="sxs-lookup"><span data-stu-id="2656e-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="2656e-105">當您設定 Lync Server for E9-1-1 時，從 Lync 2013 或 Lync Phone Edition 發出緊急通話，包括來自位置資訊服務資料庫的緊急回應位置（ERL）資訊。</span><span class="sxs-lookup"><span data-stu-id="2656e-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="2656e-106">ERLs 是由市政（也就是街道）位址及其他資訊所組成，這些資訊可協助您識別更精確的 office 辦公樓及其他具多租戶功能的位置。</span><span class="sxs-lookup"><span data-stu-id="2656e-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="2656e-107">當使用者進行緊急通話時，Lync Server 會透過轉送伺服器傳送呼叫音訊，以及位置與回呼資訊，並透過中繼伺服器傳送給 E9-1-1 服務提供者。</span><span class="sxs-lookup"><span data-stu-id="2656e-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="2656e-108">E9-1 服務提供者使用來電者的市政位址，將呼叫路由至提供來電者位置的公用安全應答點（PSAP），然後沿著 PSAP 用來查詢來電者 ERL 的緊急服務查詢鍵（ESQK）傳送通話。</span><span class="sxs-lookup"><span data-stu-id="2656e-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="2656e-109">Lync Server 支援兩種方法，可將緊急呼叫路由至 E9-1-1 服務提供者：</span><span class="sxs-lookup"><span data-stu-id="2656e-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="2656e-110">與合格 E9-1-1 服務提供者的會話初始通訊協定（SIP）中繼連線</span><span class="sxs-lookup"><span data-stu-id="2656e-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="2656e-111">將緊急位置識別號碼（ELIN）閘道移至公用交換電話（PSTN）的 E9-1-1 服務提供者</span><span class="sxs-lookup"><span data-stu-id="2656e-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="2656e-112">當您使用 SIP 幹線 E9-1 服務提供者時，您會將 ERLs 新增至位置資訊服務資料庫，然後根據 E9-1 服務提供者所維護的主要街道位址指南（MSAG）來驗證位置。</span><span class="sxs-lookup"><span data-stu-id="2656e-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="2656e-113">如果 E9-1-1 服務提供者收到的通話沒有位置資訊，或有未針對 MSAG 驗證的位置，E9-1-1 服務提供者會將呼叫路由至國內/地區緊急電話回應中心（ECRC），該人員是由經過專門訓練的人員所組成，verbally 取得來電者的位置，並將呼叫手動傳送給適當的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="2656e-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="2656e-114">（部分 SIP 幹線 E9-1 服務提供者也會將 PSTN 直向內撥號（已）號碼提供給 ECRC，這會提供路由9-1-1 呼叫的替代方法，如果 SIP 幹線由於任何原因而失敗。）</span><span class="sxs-lookup"><span data-stu-id="2656e-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="2656e-115">與時間系分複用（TDM）和 IP 專用分支 exchange （PBX）電話（具有固定位置）不同，Lync 端點可以是非常行動。</span><span class="sxs-lookup"><span data-stu-id="2656e-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="2656e-116">當您部署 E9-1-1 功能時，Lync Server 有助於確保無論來電者位於何處，緊急通話都可以傳送給提供來電者位置的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="2656e-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="2656e-117">例如，如果使用者的主要 office 位於華盛頓州的雷蒙德，但使用者是在 Wichita、堪薩斯、SIP 主幹或 PSTN E9-1-1 服務提供者將呼叫傳送給 Wichita 中的 PSAP，但使用者是從分支辦公室中的電腦撥打緊急電話。，而不是在雷德蒙的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="2656e-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="2656e-118">當您使用 ELIN 閘道時，您也會將 ERLs 新增至位置資訊服務資料庫，但每個位置也包含一個 ELIN 號碼。</span><span class="sxs-lookup"><span data-stu-id="2656e-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="2656e-119">ELIN 號碼會在緊急通話期間變成緊急電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2656e-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="2656e-120">接著，您必須確認 PSTN 載波會將 ELINs 上傳到自動位置識別（阿裡）資料庫。</span><span class="sxs-lookup"><span data-stu-id="2656e-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2656e-121">Lync 連線的模擬裝置無法從位置資訊服務接收位置資訊，或是從 E9-1-1 服務提供者傳送位置。</span><span class="sxs-lookup"><span data-stu-id="2656e-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="2656e-122">如果您使用 SIP 幹線 E9-1-1 服務提供者選項，且需要從類比電話支援 E9-1-1，您有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="2656e-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="2656e-123"><STRONG>傳統 PS-阿裡選項</STRONG>&nbsp;&nbsp;&nbsp;如果您在每個部署類比手機且每個類比電話都有的位置都有本機 PSTN 閘道，您可以直接使用私人開關/自動位置識別（PS-阿裡）服務提供者來預配類比裝置的位置。</span><span class="sxs-lookup"><span data-stu-id="2656e-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="2656e-124">在這種情況下，您可以設定巧盡心思設計的 Lync 語音原則，並將它們指派給類比裝置連絡人物件，讓來自這些電話的 E9-1 呼叫直接透過本機閘道路由至服務網站的 PSTN 提供者（而不是路由呼叫 E9-1-1 服務提供者 SIP 主幹）。</span><span class="sxs-lookup"><span data-stu-id="2656e-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="2656e-125">當緊急通話進入時，PS-阿裡 provider 中與 PSTN 幹線相關的資料庫會將每個類比電話的執行對應到一個物理位置，並提供此位置至 PSAP。</span><span class="sxs-lookup"><span data-stu-id="2656e-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="2656e-126">每次將手機移至不同的 ERLs，就必須使用 PS-阿裡服務提供者來更新這些記錄。</span><span class="sxs-lookup"><span data-stu-id="2656e-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="2656e-127"><STRONG>E9-1-1 服務提供者選項</STRONG>&nbsp;&nbsp;&nbsp;您可以使用 E9-1-1 服務提供者（如果 E9-1-1 服務提供者支援）來登錄類比電話 DIDs 及其對應的 ERLs。</span><span class="sxs-lookup"><span data-stu-id="2656e-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="2656e-128">如果提供者從 Lync Server 接收不含 PIDF-LO 資料的呼叫，提供者可以查看呼叫方是否有相符的資料庫。</span><span class="sxs-lookup"><span data-stu-id="2656e-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="2656e-129">透過使用從其資料庫取得的 ERL，提供者可以自動將緊急呼叫路由至正確的 PSAP，而 PSAP 會收到類比裝置的功能，以及允許 dispatcher 查閱來電者位置的 ESQK 記錄。</span><span class="sxs-lookup"><span data-stu-id="2656e-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="2656e-130">如果您使用的是 ELIN 閘道選項，且需要從類比電話支援 E9-1-1，您可以直接使用 PS-阿裡服務提供者來設定類比裝置的位置，如上述第一個選項中所述。</span><span class="sxs-lookup"><span data-stu-id="2656e-130">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.</span></span>



</div>

<span data-ttu-id="2656e-131">從 Lync Server 的角度來看，E9-1-1 處理常式可以分為兩個階段：</span><span class="sxs-lookup"><span data-stu-id="2656e-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="2656e-132">階段1：取得位置</span><span class="sxs-lookup"><span data-stu-id="2656e-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="2656e-133">階段2：傳送緊急通話至 E9-1-1 服務提供者</span><span class="sxs-lookup"><span data-stu-id="2656e-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="2656e-134">本節說明這些階段的運作方式。</span><span class="sxs-lookup"><span data-stu-id="2656e-134">This section describes how these stages work.</span></span>

<span data-ttu-id="2656e-135">如果您打算將基礎結構設定為自動偵測用戶端位置，您必須先決定要用哪些網路元素將呼叫者對應到位置。</span><span class="sxs-lookup"><span data-stu-id="2656e-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="2656e-136">如需有關可能選項的詳細資訊，請參閱[定義用來判斷 Lync Server 2013 中的位置的網路元素](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)。</span><span class="sxs-lookup"><span data-stu-id="2656e-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2656e-137">本節內容</span><span class="sxs-lookup"><span data-stu-id="2656e-137">In This Section</span></span>

  - [<span data-ttu-id="2656e-138">在 Lync Server 2013 中擷取位置</span><span class="sxs-lookup"><span data-stu-id="2656e-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="2656e-139">在 Lync Server 2013 中使用 SIP 主幹路由 E9-1-1 來電</span><span class="sxs-lookup"><span data-stu-id="2656e-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="2656e-140">在 Lync Server 2013 中使用 ELIN 閘道路由 E9-1-1 來電</span><span class="sxs-lookup"><span data-stu-id="2656e-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

