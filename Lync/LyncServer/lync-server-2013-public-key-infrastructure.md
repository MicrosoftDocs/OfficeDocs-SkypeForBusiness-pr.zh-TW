---
title: Lync Server 2013：公用金鑰基礎結構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb79340b29ab4bfa6942d2b2cb62483c79b4ce9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="f0ecc-102">Lync Server 2013 的公開金鑰基礎結構</span><span class="sxs-lookup"><span data-stu-id="f0ecc-102">Public Key Infrastructure for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0ecc-103">_**主題上次修改日期：** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="f0ecc-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="f0ecc-104">Microsoft Lync Server 2013 依賴伺服器驗證的憑證，並在用戶端與伺服器之間以及不同的伺服器角色之間建立信任鏈。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="f0ecc-105">Windows Server 2012 R2，Windows Server 2012，Windows Server 2008 R2，Windows Server 2008，以及 Windows Server 2003 公開金鑰基礎結構（PKI）提供建立及驗證此信任鏈的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="f0ecc-106">[憑證] 是數位識別碼。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-106">Certificates are digital IDs.</span></span> <span data-ttu-id="f0ecc-107">它們會依名稱來識別伺服器，並指定其屬性。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-107">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="f0ecc-108">若要確保憑證上的資訊有效，憑證必須由用戶端或連線到伺服器的其他伺服器所信任的 CA 頒發。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-108">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="f0ecc-109">如果伺服器只與私人網路絡上的其他用戶端和伺服器連線，則 CA 可以是企業 CA。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-109">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="f0ecc-110">如果伺服器與私人網路絡外的實體互動，可能需要公用 CA。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-110">If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="f0ecc-111">即使憑證上的資訊有效，也必須以某種方式來確認出示證書的伺服器確實是憑證所代表的那一種。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-111">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate.</span></span> <span data-ttu-id="f0ecc-112">這是 Windows PKI 隨附的位置。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-112">This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="f0ecc-113">每個憑證都連結到一個公開金鑰。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-113">Each certificate is linked to a public key.</span></span> <span data-ttu-id="f0ecc-114">憑證上命名的伺服器會擁有只有它知道的對應私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-114">The server named on the certificate holds a corresponding private key that only it knows.</span></span> <span data-ttu-id="f0ecc-115">連線用戶端或伺服器會使用公開金鑰來加密一段隨機資訊，並將它傳送給伺服器。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-115">A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server.</span></span> <span data-ttu-id="f0ecc-116">如果伺服器將資訊解密並以純文字格式傳回，則連接實體可以確保伺服器將私密金鑰儲存在憑證上，因此是在憑證上命名的伺服器。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-116">If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0ecc-117">並非所有公用 Ca 都符合 Lync Server 2013 憑證的需求。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="f0ecc-118">我們建議您參考認證的公用 CA 廠商清單，以瞭解您的公用證書需求。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="f0ecc-119">如需詳細資訊，請參閱整合通訊<A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>憑證合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-119">For details, see Unified Communications Certificate Partners at <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="f0ecc-120">CRL 發佈點</span><span class="sxs-lookup"><span data-stu-id="f0ecc-120">CRL Distribution Points</span></span>

<span data-ttu-id="f0ecc-121">Lync Server 2013 需要所有伺服器憑證，才能包含一或多個憑證吊銷清單（CRL）發佈點。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="f0ecc-122">CRL 發佈點（Cdp）是可供您下載 Crl 的位置，目的是確認憑證在發行之後，且證書仍在有效期限內。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="f0ecc-123">CRL 發佈點在憑證的屬性中以 URL 的形式注明，通常是安全的 HTTP。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="f0ecc-124">增強型金鑰用法</span><span class="sxs-lookup"><span data-stu-id="f0ecc-124">Enhanced Key Usage</span></span>

<span data-ttu-id="f0ecc-125">Lync Server 2013 需要所有伺服器憑證來支援增強型金鑰用法（EKU），以用於伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="f0ecc-126">針對伺服器驗證設定 EKU 欄位，表示憑證是有效的，目的在於驗證服務器。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="f0ecc-127">此 EKU 對於 MTLS 而言是必要的。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="f0ecc-128">在 EKU 中可能會有一個以上的專案，讓憑證可用於多種用途。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0ecc-129">從即時通訊伺服器2003與即時通訊伺服器2005進行輸出 MTLS 連線需要用戶端驗證 EKU，但不再需要。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-129">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required.</span></span> <span data-ttu-id="f0ecc-130">不過，此 EKU 必須存在於透過公用 IM 連線方式連線至 AOL 的邊緣伺服器上。</span><span class="sxs-lookup"><span data-stu-id="f0ecc-130">However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

