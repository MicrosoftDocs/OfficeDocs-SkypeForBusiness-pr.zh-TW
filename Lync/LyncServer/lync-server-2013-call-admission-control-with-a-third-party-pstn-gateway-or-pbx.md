---
title: 使用協力廠商 PSTN 閘道或 PBX 的通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e9223722b37fa703bcc0410092ebdf933beb5d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="1bd35-102">使用協力廠商 PSTN 閘道或 PBX 的 Lync Server 2013 中的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="1bd35-102">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bd35-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="1bd35-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="1bd35-104">本主題說明如何在轉送伺服器的閘道介面和協力廠商公用交換電話網路 (PSTN) 閘道或專用交換機 (PBX) 之間的連結上，部署通話許可控制 (CAC) 的範例。</span><span class="sxs-lookup"><span data-stu-id="1bd35-104">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="1bd35-105">案例1：轉送伺服器和 PSTN 閘道之間的 CAC</span><span class="sxs-lookup"><span data-stu-id="1bd35-105">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="1bd35-106">CAC 可以從轉送伺服器閘道介面到協力廠商 PBX 或 PSTN 閘道的 WAN 連結上部署。</span><span class="sxs-lookup"><span data-stu-id="1bd35-106">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="1bd35-107">**案例1：轉送伺服器和 PSTN 閘道之間的 CAC**</span><span class="sxs-lookup"><span data-stu-id="1bd35-107">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="1bd35-108">![案例1：轉送伺服器 PSTN 閘道之間的 CAC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "案例1：轉送伺服器 PSTN 閘道之間的 CAC")</span><span class="sxs-lookup"><span data-stu-id="1bd35-108">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="1bd35-109">在此範例中，轉送伺服器和 PSTN 閘道之間會套用 CAC。</span><span class="sxs-lookup"><span data-stu-id="1bd35-109">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="1bd35-110">如果網路 Site 1 上的 Lync 用戶端使用者透過網路 Site 2 中的 PSTN 閘道撥打 PSTN 電話，該媒體會透過 WAN 連結進行流量。</span><span class="sxs-lookup"><span data-stu-id="1bd35-110">If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="1bd35-111">因此，每個 PSTN 會話會執行兩個 CAC 檢查：</span><span class="sxs-lookup"><span data-stu-id="1bd35-111">Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="1bd35-112">Lync 用戶端應用程式與轉送伺服器之間</span><span class="sxs-lookup"><span data-stu-id="1bd35-112">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="1bd35-113">轉送伺服器和 PSTN 閘道之間</span><span class="sxs-lookup"><span data-stu-id="1bd35-113">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="1bd35-114">這適用于網路 Site 1 中的用戶端傳入 PSTN 通話，以及來自網路 Site 1 中用戶端應用程式的撥出 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="1bd35-114">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1bd35-115">確定 PSTN 閘道所屬的 IP 子網已經過設定，並與網路網站2相關聯。</span><span class="sxs-lookup"><span data-stu-id="1bd35-115">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="1bd35-116">請確定轉送伺服器的兩個介面都屬於的 IP 子網已設定，並與網路網站1產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1bd35-116">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="1bd35-117">如需詳細資訊，請參閱<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中建立子網與網路網站的關聯</A>。</span><span class="sxs-lookup"><span data-stu-id="1bd35-117">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="1bd35-118">案例2：轉送伺服器和具有媒體終止點之協力廠商 PBX 之間的 CAC</span><span class="sxs-lookup"><span data-stu-id="1bd35-118">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="1bd35-119">這種設定與案例1類似。</span><span class="sxs-lookup"><span data-stu-id="1bd35-119">This configuration is similar to Case 1.</span></span> <span data-ttu-id="1bd35-120">在這兩種情況下，轉送伺服器都知道在 WAN 連結的相對端終止媒體的方式，以及 PSTN 閘道或 PBX 的 IP 位址，以及具有媒體終止點 (MTP) 會在轉送伺服器上設定為下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="1bd35-120">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="1bd35-121">**案例2：轉送伺服器和具有 MTP 之協力廠商 PBX 之間的 CAC**</span><span class="sxs-lookup"><span data-stu-id="1bd35-121">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="1bd35-122">![案例2：轉送伺服器 PBX 與 MTP 之間的 CAC](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "案例2：轉送伺服器 PBX 與 MTP 之間的 CAC")</span><span class="sxs-lookup"><span data-stu-id="1bd35-122">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="1bd35-123">在此範例中，轉送伺服器和 PBX/MTP 之間會套用 CAC。</span><span class="sxs-lookup"><span data-stu-id="1bd35-123">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="1bd35-124">如果網路網站1上的 Lync 用戶端使用者透過位於網路 Site 2 的 PBX/MTP 來撥打 PSTN 電話，該媒體會透過 WAN 連結進行流量。</span><span class="sxs-lookup"><span data-stu-id="1bd35-124">If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="1bd35-125">因此，每個 PSTN 會話都會執行兩個 CAC 檢查：</span><span class="sxs-lookup"><span data-stu-id="1bd35-125">Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="1bd35-126">Lync 用戶端應用程式與轉送伺服器之間</span><span class="sxs-lookup"><span data-stu-id="1bd35-126">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="1bd35-127">轉送伺服器和 PBX/MTP 之間</span><span class="sxs-lookup"><span data-stu-id="1bd35-127">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="1bd35-128">這適用于對網路 Site 1 中的用戶端進行傳入 PSTN 通話，以及發自來自網路 Site 1 之用戶端的傳出 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="1bd35-128">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1bd35-129">確定 MTP 所屬的 IP 子網已經過設定，並與網路網站2相關聯。</span><span class="sxs-lookup"><span data-stu-id="1bd35-129">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="1bd35-130">請確定轉送伺服器的兩個介面都屬於的 IP 子網已設定，並與網路網站1產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1bd35-130">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="1bd35-131">如需詳細資訊，請參閱<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中建立子網與網路網站的關聯</A>。</span><span class="sxs-lookup"><span data-stu-id="1bd35-131">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="1bd35-132">案例3：轉送伺服器和不具有媒體終端點之協力廠商 PBX 之間的 CAC</span><span class="sxs-lookup"><span data-stu-id="1bd35-132">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="1bd35-133">Case 3 與前兩個案例稍有不同。</span><span class="sxs-lookup"><span data-stu-id="1bd35-133">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="1bd35-134">如果在協力廠商 PBX 上沒有 MTP，轉送伺服器不會知道媒體在 PBX 界限中將終止的哪個位置。</span><span class="sxs-lookup"><span data-stu-id="1bd35-134">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="1bd35-135">在此情況下，媒體會直接流過轉送伺服器和協力廠商端點裝置。</span><span class="sxs-lookup"><span data-stu-id="1bd35-135">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="1bd35-136">**案例3：轉送伺服器和不具有 MTP 之協力廠商 PBX 之間的 CAC**</span><span class="sxs-lookup"><span data-stu-id="1bd35-136">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="1bd35-137">![案例3：轉送伺服器 PBX 之間的 CAC 無 MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "案例3：轉送伺服器 PBX 之間的 CAC 無 MTP")</span><span class="sxs-lookup"><span data-stu-id="1bd35-137">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="1bd35-138">在此範例中，如果網路 Site 1 上的 Lync 用戶端使用者透過 PBX 呼叫使用者，則轉送伺服器只能在 Lync 用戶端應用程式與轉送伺服器) 之間的 proxy 腿 (執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="1bd35-138">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server).</span></span> <span data-ttu-id="1bd35-139">因為在要求會話時，轉送伺服器沒有端點裝置的相關資訊，所以在建立通話之前，無法在轉送伺服器和協力廠商) 端點之間的 WAN 連結 (上執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="1bd35-139">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="1bd35-140">在建立會話後，轉送伺服器會為主幹使用的頻寬進行會計核算。</span><span class="sxs-lookup"><span data-stu-id="1bd35-140">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="1bd35-141">針對來自協力廠商端點的呼叫，在會話要求時可使用該端點裝置的相關資訊，同時也可以在轉送伺服器的兩側執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="1bd35-141">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1bd35-142">確定端點裝置所屬的 IP 子網已經過設定，並與網路網站2相關聯。</span><span class="sxs-lookup"><span data-stu-id="1bd35-142">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="1bd35-143">請確定轉送伺服器的兩個介面都屬於的 IP 子網已設定，並與網路網站1產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1bd35-143">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="1bd35-144">如需詳細資訊，請參閱<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中建立子網與網路網站的關聯</A>。</span><span class="sxs-lookup"><span data-stu-id="1bd35-144">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

