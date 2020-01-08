---
title: 協力廠商 PSTN 閘道或 PBX 的通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1996b56a50dbe616c8dc6e9b9b1c779c564b185
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="560e7-102">Lync Server 2013 中的協力廠商 PSTN 閘道或 PBX 的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="560e7-102">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="560e7-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="560e7-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="560e7-104">本主題說明如何將呼叫許可控制（CAC）部署在中繼伺服器的閘道介面與協力廠商公用交換電話網絡（PSTN）閘道或私人分支 exchange （PBX）之間的連結上。</span><span class="sxs-lookup"><span data-stu-id="560e7-104">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="560e7-105">Case 1：在中繼伺服器與 PSTN 閘道之間的 CAC</span><span class="sxs-lookup"><span data-stu-id="560e7-105">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="560e7-106">在從中繼伺服器的閘道介面到協力廠商 PBX 或 PSTN 閘道的 WAN 連結上，可以部署 CAC。</span><span class="sxs-lookup"><span data-stu-id="560e7-106">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="560e7-107">**Case 1：在中繼伺服器與 PSTN 閘道之間的 CAC**</span><span class="sxs-lookup"><span data-stu-id="560e7-107">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="560e7-108">![Case 1：在中繼伺服器 Pstn 閘道之間出現 cac]的情況(images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "1：在中繼伺服器 pstn 閘道之間出現 cac")</span><span class="sxs-lookup"><span data-stu-id="560e7-108">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="560e7-109">在這個範例中，在中繼伺服器和 PSTN 閘道之間會套用 CAC。</span><span class="sxs-lookup"><span data-stu-id="560e7-109">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="560e7-110">如果在網路網站1的 Lync 用戶端使用者要透過 Network Site 2 中的 PSTN 閘道撥 PSTN 通話，媒體會透過 WAN 連結來流動。</span><span class="sxs-lookup"><span data-stu-id="560e7-110">If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="560e7-111">因此，每個 PSTN 會話都會執行兩個 CAC 檢查：</span><span class="sxs-lookup"><span data-stu-id="560e7-111">Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="560e7-112">在 Lync 用戶端應用程式與中繼伺服器之間</span><span class="sxs-lookup"><span data-stu-id="560e7-112">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="560e7-113">在中繼伺服器與 PSTN 閘道之間</span><span class="sxs-lookup"><span data-stu-id="560e7-113">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="560e7-114">這適用于網路 Site 1 中的用戶端撥入 PSTN 呼叫，以及源自網路 Site 1 中用戶端應用程式的出局 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="560e7-114">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="560e7-115">確認 PSTN 閘道所屬的 IP 子網已設定並與網路 Site 2 相關聯。</span><span class="sxs-lookup"><span data-stu-id="560e7-115">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="560e7-116">請確定已設定中繼伺服器的兩個介面所屬的 IP 子網，並與網路 Site 1 產生關聯。</span><span class="sxs-lookup"><span data-stu-id="560e7-116">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="560e7-117">如需詳細資訊，請參閱<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中將子網與網路網站建立關聯</A>。</span><span class="sxs-lookup"><span data-stu-id="560e7-117">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="560e7-118">Case 2：在中繼伺服器與含媒體端接點的協力廠商 PBX 之間使用 CAC</span><span class="sxs-lookup"><span data-stu-id="560e7-118">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="560e7-119">此設定類似于 Case 1。</span><span class="sxs-lookup"><span data-stu-id="560e7-119">This configuration is similar to Case 1.</span></span> <span data-ttu-id="560e7-120">在這兩種情況下，中繼伺服器會知道在 WAN 連結的另一端終止媒體的裝置，以及具有媒體端接點（MTP）之 PSTN 閘道或 PBX 的 IP 位址，都是在轉送伺服器上設定為下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="560e7-120">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="560e7-121">**Case 2：在中繼伺服器與含 MTP 的協力廠商 PBX 之間使用的 CAC**</span><span class="sxs-lookup"><span data-stu-id="560e7-121">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="560e7-122">![Case 2：在具有 mtp 的中繼伺服器 pbx 之間使用的 cac](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "： CAC （含 Mtp 的中繼伺服器 pbx") ）</span><span class="sxs-lookup"><span data-stu-id="560e7-122">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="560e7-123">在這個範例中，在中繼伺服器與 PBX/MTP 之間會套用 CAC。</span><span class="sxs-lookup"><span data-stu-id="560e7-123">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="560e7-124">如果網路網站1的 Lync 用戶端使用者是透過網路 Site 2 中的 PBX/MTP 來撥打 PSTN 電話，則媒體會透過 WAN 連結來流動。</span><span class="sxs-lookup"><span data-stu-id="560e7-124">If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="560e7-125">因此，對於每個 PSTN 會話，都會執行兩個 CAC 檢查：</span><span class="sxs-lookup"><span data-stu-id="560e7-125">Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="560e7-126">在 Lync 用戶端應用程式與中繼伺服器之間</span><span class="sxs-lookup"><span data-stu-id="560e7-126">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="560e7-127">在中繼伺服器與 PBX/MTP 之間</span><span class="sxs-lookup"><span data-stu-id="560e7-127">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="560e7-128">這適用于對網路 Site 1 中的用戶端進行撥入 PSTN 呼叫，以及源自網路 Site 1 中用戶端的出局 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="560e7-128">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="560e7-129">確認 MTP 所屬的 IP 子網已設定並與網路 Site 2 相關聯。</span><span class="sxs-lookup"><span data-stu-id="560e7-129">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="560e7-130">請確定已設定中繼伺服器的兩個介面所屬的 IP 子網，並與網路 Site 1 產生關聯。</span><span class="sxs-lookup"><span data-stu-id="560e7-130">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="560e7-131">如需詳細資訊，請參閱<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中將子網與網路網站建立關聯</A>。</span><span class="sxs-lookup"><span data-stu-id="560e7-131">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="560e7-132">Case 3：在中繼伺服器與協力廠商 PBX 之間的 CAC （不含媒體終止點）</span><span class="sxs-lookup"><span data-stu-id="560e7-132">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="560e7-133">Case 3 與前兩個案例稍有不同。</span><span class="sxs-lookup"><span data-stu-id="560e7-133">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="560e7-134">如果在協力廠商 PBX 上沒有 MTP，那麼對於協力廠商 PBX 的傳出會話要求，中繼伺服器不知道媒體將在 PBX 邊界中終止的位置。</span><span class="sxs-lookup"><span data-stu-id="560e7-134">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="560e7-135">在這種情況下，媒體會直接在中繼伺服器與協力廠商端點裝置之間流動。</span><span class="sxs-lookup"><span data-stu-id="560e7-135">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="560e7-136">**Case 3：在中繼伺服器與沒有 MTP 的協力廠商 PBX 之間使用 CAC**</span><span class="sxs-lookup"><span data-stu-id="560e7-136">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="560e7-137">![案例3：在中繼伺服器 pbx 之間的 cac 沒有 mtp](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "案例3：在中繼伺服器 PBX 之間沒有 mtp")</span><span class="sxs-lookup"><span data-stu-id="560e7-137">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="560e7-138">在這個範例中，如果網路網站1的 Lync 用戶端使用者透過 PBX 撥打電話給使用者，則中繼伺服器只能在 proxy 腿（在 Lync 用戶端應用程式和中繼伺服器之間）執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="560e7-138">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server).</span></span> <span data-ttu-id="560e7-139">因為在進行會話時，中繼伺服器沒有端點裝置的相關資訊，所以在通話建立之前，無法在 WAN 連結（在中繼伺服器與協力廠商端點之間）執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="560e7-139">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="560e7-140">不過，在建立會話之後，中繼伺服器會針對主幹上使用的頻寬進行記帳。</span><span class="sxs-lookup"><span data-stu-id="560e7-140">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="560e7-141">針對源自協力廠商端點的呼叫，您可以在進行會話要求時，在中繼伺服器端的兩面執行 CAC 檢查時，提供該端點裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="560e7-141">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="560e7-142">確認端點裝置所屬的 IP 子網已設定並與網路 Site 2 相關聯。</span><span class="sxs-lookup"><span data-stu-id="560e7-142">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="560e7-143">請確定已設定中繼伺服器的兩個介面所屬的 IP 子網，並與網路 Site 1 產生關聯。</span><span class="sxs-lookup"><span data-stu-id="560e7-143">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="560e7-144">如需詳細資訊，請參閱<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">在 Lync Server 2013 中將子網與網路網站建立關聯</A>。</span><span class="sxs-lookup"><span data-stu-id="560e7-144">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

