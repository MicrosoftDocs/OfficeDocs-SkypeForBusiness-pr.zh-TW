---
title: Lync Server 2013： 加密
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
ms.openlocfilehash: 2b87e395f56c7dfdbd03bf35c5c1c8cf37795652
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="77a4b-102">Lync Server 2013 的加密</span><span class="sxs-lookup"><span data-stu-id="77a4b-102">Encryption for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77a4b-103">_**主題上次修改日期：** 2017年-09-14_</span><span class="sxs-lookup"><span data-stu-id="77a4b-103">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="77a4b-104">Microsoft Lync Server 2013 使用 TLS 和 MTLS 加密立即訊息。</span><span class="sxs-lookup"><span data-stu-id="77a4b-104">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="77a4b-105">伺服器對伺服器的所有流量都需要 MTLS，不論是否流量局限於內部網路或跨越內部網路周邊網路。</span><span class="sxs-lookup"><span data-stu-id="77a4b-105">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="77a4b-106">TLS 是選擇性的但強烈建議在中繼伺服器和媒體閘道之間。</span><span class="sxs-lookup"><span data-stu-id="77a4b-106">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="77a4b-107">如果在此連結上設定 TLS，則 MTLS 是必要的。</span><span class="sxs-lookup"><span data-stu-id="77a4b-107">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="77a4b-108">因此，必須設定閘道，以從中繼伺服器所信任的 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="77a4b-108">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77a4b-109">安全性公告有關 SSL 3.0 發佈在 2014年。</span><span class="sxs-lookup"><span data-stu-id="77a4b-109">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="77a4b-110">停用 Lync Server 2013 中的 SSL 3.0 是支援的選項。</span><span class="sxs-lookup"><span data-stu-id="77a4b-110">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="77a4b-111">若要深入了解安全性摘要報告，請參閱<A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>。</span><span class="sxs-lookup"><span data-stu-id="77a4b-111">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全性" alt="security" /><span data-ttu-id="77a4b-113">安全性附註：</span><span class="sxs-lookup"><span data-stu-id="77a4b-113">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="77a4b-114">若要確保會使用最強的密碼編譯通訊協定，Lync Server 2013 將用戶端提供 TLS 加密通訊協定，依下列順序： <strong>TLS 1.2</strong> 、 <strong>TLS 1.1</strong>、 <strong>TLS 1.0</strong>。</span><span class="sxs-lookup"><span data-stu-id="77a4b-114">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="77a4b-115">TLS 是不可或缺的 Lync Server 2013，因此它必須要有維持支援的環境。</span><span class="sxs-lookup"><span data-stu-id="77a4b-115">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="77a4b-p104">用戶端對用戶端流量的需求是根據流量是否通過內部企業防火牆而定。嚴格內部流量可以使用 TLS (此時即時訊息會經過加密)，或者使用 TCP (此時就不會加密)。</span><span class="sxs-lookup"><span data-stu-id="77a4b-p104">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall. Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="77a4b-118">下表摘要說明每一種流量類型的通訊協定需求。</span><span class="sxs-lookup"><span data-stu-id="77a4b-118">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="77a4b-119">流量保護</span><span class="sxs-lookup"><span data-stu-id="77a4b-119">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77a4b-120">流量類型</span><span class="sxs-lookup"><span data-stu-id="77a4b-120">Traffic type</span></span></th>
<th><span data-ttu-id="77a4b-121">提供保護的通訊協定</span><span class="sxs-lookup"><span data-stu-id="77a4b-121">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77a4b-122">伺服器對伺服器</span><span class="sxs-lookup"><span data-stu-id="77a4b-122">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="77a4b-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="77a4b-123">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77a4b-124">用戶端對伺服器</span><span class="sxs-lookup"><span data-stu-id="77a4b-124">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="77a4b-125">TLS</span><span class="sxs-lookup"><span data-stu-id="77a4b-125">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77a4b-126">立即訊息和目前狀態</span><span class="sxs-lookup"><span data-stu-id="77a4b-126">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="77a4b-127">TLS (若設定為 TLS)</span><span class="sxs-lookup"><span data-stu-id="77a4b-127">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77a4b-128">音訊和視訊及媒體的桌面共用</span><span class="sxs-lookup"><span data-stu-id="77a4b-128">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="77a4b-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="77a4b-129">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77a4b-130">桌面共用 (訊號)</span><span class="sxs-lookup"><span data-stu-id="77a4b-130">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="77a4b-131">TLS</span><span class="sxs-lookup"><span data-stu-id="77a4b-131">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77a4b-132">Web 會議</span><span class="sxs-lookup"><span data-stu-id="77a4b-132">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="77a4b-133">TLS</span><span class="sxs-lookup"><span data-stu-id="77a4b-133">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77a4b-134">會議內容下載、通訊錄下載、通訊群組擴充</span><span class="sxs-lookup"><span data-stu-id="77a4b-134">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="77a4b-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="77a4b-135">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="77a4b-136">媒體加密</span><span class="sxs-lookup"><span data-stu-id="77a4b-136">Media Encryption</span></span>

<span data-ttu-id="77a4b-137">媒體流量都是使用安全 RTP (SRTP) 加密，它是即時傳輸通訊協定 (RTP) 的設定檔，為 RTP 流量提供機密性、驗證功能和重播攻擊防護。</span><span class="sxs-lookup"><span data-stu-id="77a4b-137">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="77a4b-138">此外，在中繼伺服器及其內部下一個躍點之間往返流動的媒體也是使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="77a4b-138">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="77a4b-139">依預設不會加密雙向中繼伺服器和媒體閘道之間流動的媒體。</span><span class="sxs-lookup"><span data-stu-id="77a4b-139">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="77a4b-140">中繼伺服器可支援媒體閘道加密，但是閘道必須支援 MTLS 和憑證存放。</span><span class="sxs-lookup"><span data-stu-id="77a4b-140">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77a4b-141">音訊/視訊 (A / V) 支援與 Windows Live Messenger 的新版本。</span><span class="sxs-lookup"><span data-stu-id="77a4b-141">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="77a4b-142">如果您要實作 Windows Live Messenger 的 A/V 同盟，則必須修改 Lync Server 加密層級。</span><span class="sxs-lookup"><span data-stu-id="77a4b-142">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="77a4b-143">根據預設，加密層級為 [必要]。</span><span class="sxs-lookup"><span data-stu-id="77a4b-143">By default, the encryption level is Required.</span></span> <span data-ttu-id="77a4b-144">您必須使用 Lync Server 管理命令介面，將此設定變更為支援。</span><span class="sxs-lookup"><span data-stu-id="77a4b-144">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="77a4b-145">如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-deploying-external-user-access.md">Deploying Lync Server 2013 中的外部使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="77a4b-145">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="77a4b-146">音訊和視訊媒體流量並未加密 Microsoft Lync 2013 與 Windows Live 用戶端之間。</span><span class="sxs-lookup"><span data-stu-id="77a4b-146">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="77a4b-147">FIPS</span><span class="sxs-lookup"><span data-stu-id="77a4b-147">FIPS</span></span>

<span data-ttu-id="77a4b-148">Lync Server 2013 和 Microsoft Exchange Server 2013 操作與支援的聯邦資訊處理標準 (FIPS) 140-2 演算法如果 Windows Server 作業系統設定為使用 FIPS 140-2 演算法系統密碼編譯。</span><span class="sxs-lookup"><span data-stu-id="77a4b-148">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="77a4b-149">若要實作 FIPS 支援，您必須設定執行 Lync Server 2013 到支援它的每部伺服器。</span><span class="sxs-lookup"><span data-stu-id="77a4b-149">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="77a4b-150">如需使用 FIPS 相容演算法以及如何實作 FIPS 支援的詳細資訊，請參閱 Microsoft 知識庫文章 811833，啟用效果 」 系統密碼編譯： 使用 FIPS 相容演算法進行加密，雜湊，以及簽章 」 安全性設定和更新版本的 Windows，Windows XP 中[https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)。</span><span class="sxs-lookup"><span data-stu-id="77a4b-150">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="77a4b-151">如需 FIPS 140-2 支援和限制在 Exchange 2010 中，請參閱 Exchange 2010 SP1 和支援的 FIPS 相容演算法在[https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)。</span><span class="sxs-lookup"><span data-stu-id="77a4b-151">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

