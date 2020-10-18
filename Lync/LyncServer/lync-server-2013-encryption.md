---
title: Lync Server 2013：加密
description: Lync Server 2013：加密。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab2c46af16cfdbb9a01631777e65219acb2ceb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575649"
---
# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="f4a11-103">Lync Server 2013 的加密</span><span class="sxs-lookup"><span data-stu-id="f4a11-103">Encryption for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4a11-104">_**主題上次修改日期：** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="f4a11-104">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="f4a11-105">Microsoft Lync Server 2013 使用 TLS 和 MTLS 來加密立即訊息。</span><span class="sxs-lookup"><span data-stu-id="f4a11-105">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="f4a11-106">不論流量是限制在內部網路或越過內部網路周邊，所有伺服器對伺服器的流量都需要 MTLS。</span><span class="sxs-lookup"><span data-stu-id="f4a11-106">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="f4a11-107">TLS 是選擇性的，但在轉送伺服器和媒體閘道之間強烈建議使用。</span><span class="sxs-lookup"><span data-stu-id="f4a11-107">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="f4a11-108">如果在此連結上設定 TLS，則需要 MTLS。</span><span class="sxs-lookup"><span data-stu-id="f4a11-108">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="f4a11-109">因此，閘道必須使用來自轉送伺服器所信任之 CA 的憑證加以設定。</span><span class="sxs-lookup"><span data-stu-id="f4a11-109">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4a11-110">有關 SSL 3.0 的安全性通報已在2014中發佈。</span><span class="sxs-lookup"><span data-stu-id="f4a11-110">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="f4a11-111">在 Lync Server 2013 中停用 SSL 3.0 是支援的選項。</span><span class="sxs-lookup"><span data-stu-id="f4a11-111">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="f4a11-112">若要深入瞭解安全性通報，請參閱 <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A> 。</span><span class="sxs-lookup"><span data-stu-id="f4a11-112">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" /><span data-ttu-id="f4a11-114">安全性附注：</span><span class="sxs-lookup"><span data-stu-id="f4a11-114">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f4a11-115">為了確保使用最強的加密通訊協定，Lync Server 2013 會以下列順序為用戶端提供 TLS 加密通訊協定： <strong>tls 1.2</strong> ， <strong>tls 1.1</strong>， <strong>tls 1.0</strong>。</span><span class="sxs-lookup"><span data-stu-id="f4a11-115">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="f4a11-116">TLS 是 Lync Server 2013 的重要層面，因此必須使用此功能才能維護支援的環境。</span><span class="sxs-lookup"><span data-stu-id="f4a11-116">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="f4a11-p104">用戶端對用戶端流量的需求是根據流量是否通過內部企業防火牆而定。嚴格內部流量可以使用 TLS (此時即時訊息會經過加密)，或者使用 TCP (此時就不會加密)。</span><span class="sxs-lookup"><span data-stu-id="f4a11-p104">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall. Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="f4a11-119">下表摘要說明每一種流量類型的通訊協定需求。</span><span class="sxs-lookup"><span data-stu-id="f4a11-119">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="f4a11-120">流量保護</span><span class="sxs-lookup"><span data-stu-id="f4a11-120">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f4a11-121">流量類型</span><span class="sxs-lookup"><span data-stu-id="f4a11-121">Traffic type</span></span></th>
<th><span data-ttu-id="f4a11-122">提供保護的通訊協定</span><span class="sxs-lookup"><span data-stu-id="f4a11-122">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f4a11-123">伺服器對伺服器</span><span class="sxs-lookup"><span data-stu-id="f4a11-123">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="f4a11-124">MTLS</span><span class="sxs-lookup"><span data-stu-id="f4a11-124">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4a11-125">用戶端對伺服器</span><span class="sxs-lookup"><span data-stu-id="f4a11-125">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="f4a11-126">TLS</span><span class="sxs-lookup"><span data-stu-id="f4a11-126">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4a11-127">立即訊息和目前狀態</span><span class="sxs-lookup"><span data-stu-id="f4a11-127">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="f4a11-128">TLS (若設定為 TLS)</span><span class="sxs-lookup"><span data-stu-id="f4a11-128">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4a11-129">音訊和視訊及媒體的桌面共用</span><span class="sxs-lookup"><span data-stu-id="f4a11-129">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="f4a11-130">SRTP</span><span class="sxs-lookup"><span data-stu-id="f4a11-130">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4a11-131">桌面共用 (訊號)</span><span class="sxs-lookup"><span data-stu-id="f4a11-131">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="f4a11-132">TLS</span><span class="sxs-lookup"><span data-stu-id="f4a11-132">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f4a11-133">Web 會議</span><span class="sxs-lookup"><span data-stu-id="f4a11-133">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="f4a11-134">TLS</span><span class="sxs-lookup"><span data-stu-id="f4a11-134">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f4a11-135">會議內容下載、通訊錄下載、通訊群組擴充</span><span class="sxs-lookup"><span data-stu-id="f4a11-135">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="f4a11-136">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="f4a11-136">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="f4a11-137">媒體加密</span><span class="sxs-lookup"><span data-stu-id="f4a11-137">Media Encryption</span></span>

<span data-ttu-id="f4a11-138">媒體流量都是使用安全 RTP (SRTP) 加密，它是即時傳輸通訊協定 (RTP) 的設定檔，為 RTP 流量提供機密性、驗證功能和重播攻擊防護。</span><span class="sxs-lookup"><span data-stu-id="f4a11-138">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="f4a11-139">此外，中繼伺服器與其下一個內部躍點之間的雙向媒體流量也是使用 SRTP 來加密。</span><span class="sxs-lookup"><span data-stu-id="f4a11-139">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="f4a11-140">轉送伺服器和媒體閘道之間的兩種方向的媒體會預設不加密。</span><span class="sxs-lookup"><span data-stu-id="f4a11-140">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="f4a11-141">中繼伺服器可支援媒體閘道加密，但是閘道必須支援 MTLS 和憑證存放。</span><span class="sxs-lookup"><span data-stu-id="f4a11-141">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4a11-142">Windows Live Messenger 的新版本支援 Audio/Video (A/V) 。</span><span class="sxs-lookup"><span data-stu-id="f4a11-142">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="f4a11-143">如果您要實作 Windows Live Messenger 的 A/V 同盟，則必須修改 Lync Server 加密層級。</span><span class="sxs-lookup"><span data-stu-id="f4a11-143">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="f4a11-144">根據預設，加密層級為 [必要]。</span><span class="sxs-lookup"><span data-stu-id="f4a11-144">By default, the encryption level is Required.</span></span> <span data-ttu-id="f4a11-145">您必須使用 Lync Server 管理命令介面將此設定變更為 [支援]。</span><span class="sxs-lookup"><span data-stu-id="f4a11-145">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="f4a11-146">如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 中部署外部使用者存取</A> 。</span><span class="sxs-lookup"><span data-stu-id="f4a11-146">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="f4a11-147">在 Microsoft Lync 2013 和 Windows Live 用戶端之間未加密音訊和影片媒體流量。</span><span class="sxs-lookup"><span data-stu-id="f4a11-147">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="f4a11-148">Fips</span><span class="sxs-lookup"><span data-stu-id="f4a11-148">FIPS</span></span>

<span data-ttu-id="f4a11-149">Lync Server 2013 和 Microsoft Exchange Server 2013 的運作方式是使用聯邦資訊處理標準 (FIPS) 140-2 演算法如果 Windows Server 作業系統設定為使用 FIPS 140-2 演算法進行系統加密。</span><span class="sxs-lookup"><span data-stu-id="f4a11-149">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="f4a11-150">若要實施 FIPS 支援，您必須設定每台執行 Lync Server 2013 的伺服器以支援它。</span><span class="sxs-lookup"><span data-stu-id="f4a11-150">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="f4a11-151">如需使用 FIPS 相容的演算法及如何實施 FIPS 支援的詳細資訊，請參閱 Microsoft 知識庫文章811833：在 Windows XP 和更新版本的 Windows 中，啟用「系統加密：使用 FIPS 相容的演算法進行加密、雜湊和簽署」安全性設定的影響 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) 。</span><span class="sxs-lookup"><span data-stu-id="f4a11-151">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="f4a11-152">如需 Exchange 2010 中的 FIPS 140-2 支援和限制的詳細資訊，請參閱 Exchange 2010 SP1 及支援 FIPS 相容的演算法 [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) 。</span><span class="sxs-lookup"><span data-stu-id="f4a11-152">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

