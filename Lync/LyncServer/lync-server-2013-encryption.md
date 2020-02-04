---
title: Lync Server 2013：加密
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
ms.openlocfilehash: 5f4b655ff632a50d2c28451a577f5be03bfabc82
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="93200-102">Lync Server 2013 的加密</span><span class="sxs-lookup"><span data-stu-id="93200-102">Encryption for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93200-103">_**主題上次修改日期：** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="93200-103">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="93200-104">Microsoft Lync Server 2013 使用 TLS 和 MTLS 來加密立即訊息。</span><span class="sxs-lookup"><span data-stu-id="93200-104">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="93200-105">不論流量是限制在內部網路或交叉對內部網路周邊，所有伺服器對伺服器的流量都必須是 MTLS。</span><span class="sxs-lookup"><span data-stu-id="93200-105">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="93200-106">TLS 是選擇性的，但強烈建議在中繼伺服器與媒體閘道之間使用。</span><span class="sxs-lookup"><span data-stu-id="93200-106">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="93200-107">如果在此連結上設定 TLS，則需要 MTLS。</span><span class="sxs-lookup"><span data-stu-id="93200-107">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="93200-108">因此，閘道必須使用來自中繼伺服器信任的 CA 的憑證進行設定。</span><span class="sxs-lookup"><span data-stu-id="93200-108">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93200-109">已在2014中發佈有關 SSL 3.0 的安全性通知。</span><span class="sxs-lookup"><span data-stu-id="93200-109">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="93200-110">在 Lync Server 2013 中停用 SSL 3.0 是受支援的選項。</span><span class="sxs-lookup"><span data-stu-id="93200-110">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="93200-111">若要深入瞭解安全性建議，請參閱<A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>。</span><span class="sxs-lookup"><span data-stu-id="93200-111">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" /><span data-ttu-id="93200-113">安全性注意事項：</span><span class="sxs-lookup"><span data-stu-id="93200-113">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="93200-114">為了確保使用最強的加密通訊協定，Lync Server 2013 將以下列順序為用戶端提供 TLS 加密通訊協定： <strong>tls 1.2</strong> 、 <strong>tls 1.1</strong>、 <strong>tls 1.0</strong>。</span><span class="sxs-lookup"><span data-stu-id="93200-114">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="93200-115">TLS 是 Lync Server 2013 的一個重要層面，因此需要維持支援的環境。</span><span class="sxs-lookup"><span data-stu-id="93200-115">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="93200-116">用戶端對用戶端流量的需求取決於通信量是否與內部公司防火牆交叉。</span><span class="sxs-lookup"><span data-stu-id="93200-116">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall.</span></span> <span data-ttu-id="93200-117">嚴格的內部流量可以使用 TLS，在這種情況下，立即訊息是經過加密，或 TCP，在這種情況下不會。</span><span class="sxs-lookup"><span data-stu-id="93200-117">Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="93200-118">下表摘要列出每種通信量類型的通訊協定需求。</span><span class="sxs-lookup"><span data-stu-id="93200-118">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="93200-119">交通防護</span><span class="sxs-lookup"><span data-stu-id="93200-119">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93200-120">流量類型</span><span class="sxs-lookup"><span data-stu-id="93200-120">Traffic type</span></span></th>
<th><span data-ttu-id="93200-121">受</span><span class="sxs-lookup"><span data-stu-id="93200-121">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93200-122">伺服器與伺服器</span><span class="sxs-lookup"><span data-stu-id="93200-122">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="93200-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="93200-123">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93200-124">用戶端到伺服器</span><span class="sxs-lookup"><span data-stu-id="93200-124">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="93200-125">EAP-TLS</span><span class="sxs-lookup"><span data-stu-id="93200-125">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93200-126">立即訊息與顯示狀態</span><span class="sxs-lookup"><span data-stu-id="93200-126">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="93200-127">TLS （如果針對 TLS 進行設定）</span><span class="sxs-lookup"><span data-stu-id="93200-127">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93200-128">媒體的音訊和影片與桌面共用</span><span class="sxs-lookup"><span data-stu-id="93200-128">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="93200-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="93200-129">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93200-130">桌面共用（信號）</span><span class="sxs-lookup"><span data-stu-id="93200-130">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="93200-131">EAP-TLS</span><span class="sxs-lookup"><span data-stu-id="93200-131">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93200-132">網路會議</span><span class="sxs-lookup"><span data-stu-id="93200-132">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="93200-133">EAP-TLS</span><span class="sxs-lookup"><span data-stu-id="93200-133">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93200-134">會議內容下載、通訊錄下載、通訊群組延伸</span><span class="sxs-lookup"><span data-stu-id="93200-134">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="93200-135">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="93200-135">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="93200-136">媒體加密</span><span class="sxs-lookup"><span data-stu-id="93200-136">Media Encryption</span></span>

<span data-ttu-id="93200-137">媒體流量是使用安全的 RTP （SRTP）來加密，這是一種即時傳輸通訊協定（RTP）設定檔，可為 RTP 流量提供保密性、驗證及重放攻擊保護。</span><span class="sxs-lookup"><span data-stu-id="93200-137">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="93200-138">此外，在中繼伺服器與其內部下一個躍點之間的兩個方向上，媒體也會使用 SRTP 來加密。</span><span class="sxs-lookup"><span data-stu-id="93200-138">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="93200-139">在中繼伺服器與媒體閘道之間的兩個方向上的媒體都會流動，預設不會加密。</span><span class="sxs-lookup"><span data-stu-id="93200-139">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="93200-140">中繼伺服器可以支援對媒體閘道進行加密，但閘道必須支援 MTLS 和儲存憑證。</span><span class="sxs-lookup"><span data-stu-id="93200-140">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93200-141">新版本的 Windows Live Messenger 支援音訊/視頻（A/V）。</span><span class="sxs-lookup"><span data-stu-id="93200-141">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="93200-142">如果您是使用 Windows Live Messenger 來實現 A/V 同盟，您也必須修改 Lync 伺服器加密層級。</span><span class="sxs-lookup"><span data-stu-id="93200-142">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="93200-143">根據預設，加密層級是必要的。</span><span class="sxs-lookup"><span data-stu-id="93200-143">By default, the encryption level is Required.</span></span> <span data-ttu-id="93200-144">您必須使用 Lync Server 管理命令介面將此設定變更為 [支援]。</span><span class="sxs-lookup"><span data-stu-id="93200-144">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="93200-145">如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 中的 [部署外部使用者存取</A>]。</span><span class="sxs-lookup"><span data-stu-id="93200-145">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="93200-146">在 Microsoft Lync 2013 和 Windows Live 用戶端之間，音訊及視頻媒體流量沒有加密。</span><span class="sxs-lookup"><span data-stu-id="93200-146">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="93200-147">FIPS</span><span class="sxs-lookup"><span data-stu-id="93200-147">FIPS</span></span>

<span data-ttu-id="93200-148">如果 Windows 伺服器作業系統已設定為使用 FIPS 140-2 演算法進行系統加密，則 Lync Server 2013 和 Microsoft Exchange Server 2013 會使用聯邦資訊處理標準（FIPS）140-2 演算法的支援運作。</span><span class="sxs-lookup"><span data-stu-id="93200-148">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="93200-149">若要實現 FIPS 支援，您必須設定執行 Lync Server 2013 的每個伺服器以支援它。</span><span class="sxs-lookup"><span data-stu-id="93200-149">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="93200-150">如需有關使用 FIPS 相容的演算法及如何實現 FIPS 支援的詳細資料，請參閱 Microsoft 知識庫文章811833：啟用「系統加密：使用 FIPS 相容的演算法來加密、雜湊及簽署」安全設定（在 Windows XP 中）及更新版本的 Windows 中[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)。</span><span class="sxs-lookup"><span data-stu-id="93200-150">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="93200-151">如需有關 FIPS 140-2 支援的詳細資訊，以及 Exchange 2010 中的限制，請參閱 Exchange 2010 SP1， [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)以及支援 fips 相容的演算法。</span><span class="sxs-lookup"><span data-stu-id="93200-151">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

