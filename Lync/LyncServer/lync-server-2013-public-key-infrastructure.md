---
title: Lync Server 2013：公用機碼基礎結構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cee633f877a34dcf2ec0fd0b98891c62faf0bad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512410"
---
# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="01c43-102">Lync Server 2013 的公用機碼基礎結構</span><span class="sxs-lookup"><span data-stu-id="01c43-102">Public Key Infrastructure for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01c43-103">_**主題上次修改日期：** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="01c43-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="01c43-104">Microsoft Lync Server 2013 依賴伺服器驗證的憑證，並在用戶端與伺服器之間，以及不同的伺服器角色間建立信任鏈。</span><span class="sxs-lookup"><span data-stu-id="01c43-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="01c43-105">Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 及 Windows Server 2003 Public Key 基礎結構 (PKI) 提供基礎結構，用以建立及驗證此信任鏈。</span><span class="sxs-lookup"><span data-stu-id="01c43-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="01c43-106">憑證是數位 IDs。</span><span class="sxs-lookup"><span data-stu-id="01c43-106">Certificates are digital IDs.</span></span> <span data-ttu-id="01c43-107">它們會以名稱識別伺服器，並指定其屬性。</span><span class="sxs-lookup"><span data-stu-id="01c43-107">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="01c43-108">為了確保憑證上的資訊有效，憑證必須由用戶端或連接至伺服器的其他伺服器所信任的 CA 所發出。</span><span class="sxs-lookup"><span data-stu-id="01c43-108">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="01c43-109">如果伺服器只與私人網路絡上的其他用戶端和伺服器連線，則 CA 可以是企業 CA。</span><span class="sxs-lookup"><span data-stu-id="01c43-109">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="01c43-110">如果伺服器與私人網路絡外的實體互動，則可能需要公用 CA。</span><span class="sxs-lookup"><span data-stu-id="01c43-110">If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="01c43-111">即使憑證上的資訊有效，仍然必須以某種方式驗證提供憑證的伺服器確實是憑證所代表的伺服器。</span><span class="sxs-lookup"><span data-stu-id="01c43-111">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate.</span></span> <span data-ttu-id="01c43-112">這是 Windows PKI 的所在位置。</span><span class="sxs-lookup"><span data-stu-id="01c43-112">This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="01c43-113">每一個憑證都會連結到公開金鑰。</span><span class="sxs-lookup"><span data-stu-id="01c43-113">Each certificate is linked to a public key.</span></span> <span data-ttu-id="01c43-114">憑證上命名的伺服器擁有只有本身知道的對應私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="01c43-114">The server named on the certificate holds a corresponding private key that only it knows.</span></span> <span data-ttu-id="01c43-115">連接的用戶端或伺服器會使用公開金鑰加密資訊的任意片段，並將它傳送至伺服器。</span><span class="sxs-lookup"><span data-stu-id="01c43-115">A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server.</span></span> <span data-ttu-id="01c43-116">如果伺服器解密資訊並將其傳回為純文字，則連接實體可以確定伺服器是否要將私密金鑰保留在憑證中，因此是憑證中命名的伺服器。</span><span class="sxs-lookup"><span data-stu-id="01c43-116">If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01c43-117">並非所有公用 Ca 都符合 Lync Server 2013 憑證的需求。</span><span class="sxs-lookup"><span data-stu-id="01c43-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="01c43-118">我們建議您參考已驗證的公用 CA 廠商清單，以滿足您的公用憑證需求。</span><span class="sxs-lookup"><span data-stu-id="01c43-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="01c43-119">如需詳細資訊，請參閱整合通訊憑證合作夥伴，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A> 。</span><span class="sxs-lookup"><span data-stu-id="01c43-119">For details, see Unified Communications Certificate Partners at <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="01c43-120">CRL 發佈點</span><span class="sxs-lookup"><span data-stu-id="01c43-120">CRL Distribution Points</span></span>

<span data-ttu-id="01c43-121">Lync Server 2013 要求所有伺服器憑證包含一或多個憑證吊銷清單 (CRL) 發佈點。</span><span class="sxs-lookup"><span data-stu-id="01c43-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="01c43-122">CRL 發佈點 (Cdp) 是可從中下載 Crl 的位置，目的在於驗證憑證自發行之後起尚未撤銷，且憑證仍在有效期限內。</span><span class="sxs-lookup"><span data-stu-id="01c43-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="01c43-123">CRL 發佈點會在憑證的內容中注明為 URL，且通常為安全的 HTTP。</span><span class="sxs-lookup"><span data-stu-id="01c43-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="01c43-124">增強型金鑰使用方式</span><span class="sxs-lookup"><span data-stu-id="01c43-124">Enhanced Key Usage</span></span>

<span data-ttu-id="01c43-125">由於伺服器驗證的目的，Lync Server 2013 需要所有伺服器憑證以支援增強型金鑰使用 (EKU) 。</span><span class="sxs-lookup"><span data-stu-id="01c43-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="01c43-126">設定 [伺服器驗證的 EKU] 欄位表示憑證是有效的，目的在於驗證服務器。</span><span class="sxs-lookup"><span data-stu-id="01c43-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="01c43-127">這個 EKU 對 MTLS 而言是必要的。</span><span class="sxs-lookup"><span data-stu-id="01c43-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="01c43-128">您可以在 EKU 中有一個以上的專案，為憑證啟用一個以上的目的。</span><span class="sxs-lookup"><span data-stu-id="01c43-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01c43-129">即時通訊伺服器2003和即時通訊伺服器2005中的輸出 MTLS 連線需要用戶端驗證 EKU，但是不再需要。</span><span class="sxs-lookup"><span data-stu-id="01c43-129">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required.</span></span> <span data-ttu-id="01c43-130">不過，此 EKU 必須存在於透過公用 IM 連線方式連線到 AOL 的 Edge Server 上。</span><span class="sxs-lookup"><span data-stu-id="01c43-130">However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

