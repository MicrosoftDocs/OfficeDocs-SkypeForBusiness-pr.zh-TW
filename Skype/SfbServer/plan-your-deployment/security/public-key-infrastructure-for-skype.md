---
title: 商務用 Skype Server 的公開金鑰基礎結構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: 商務用 Skype Server 依賴伺服器驗證的憑證，並在用戶端與伺服器之間以及不同的伺服器角色之間建立信任鏈。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 和 Windows Server 2008 公開金鑰基礎結構（PKI）提供建立及驗證此信任鏈的基礎結構。
ms.openlocfilehash: ec2ae6e94d9cf00a6193c45d6cefd7db6d5a5b62
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815631"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a><span data-ttu-id="c0123-104">商務用 Skype Server 的公開金鑰基礎結構</span><span class="sxs-lookup"><span data-stu-id="c0123-104">Public Key Infrastructure for Skype for Business Server</span></span>
 
<span data-ttu-id="c0123-105">商務用 Skype Server 依賴伺服器驗證的憑證，並在用戶端與伺服器之間以及不同的伺服器角色之間建立信任鏈。</span><span class="sxs-lookup"><span data-stu-id="c0123-105">Skype for Business Server relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="c0123-106">Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 和 Windows Server 2008 公開金鑰基礎結構（PKI）提供建立及驗證此信任鏈的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="c0123-106">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, and Windows Server 2008 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>
  
<span data-ttu-id="c0123-107">[憑證] 是數位識別碼。</span><span class="sxs-lookup"><span data-stu-id="c0123-107">Certificates are digital IDs.</span></span> <span data-ttu-id="c0123-108">它們會依名稱來識別伺服器，並指定其屬性。</span><span class="sxs-lookup"><span data-stu-id="c0123-108">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="c0123-109">若要確保憑證上的資訊有效，憑證必須由用戶端或連線到伺服器的其他伺服器所信任的 CA 頒發。</span><span class="sxs-lookup"><span data-stu-id="c0123-109">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="c0123-110">如果伺服器只與私人網路絡上的其他用戶端和伺服器連線，則 CA 可以是企業 CA。</span><span class="sxs-lookup"><span data-stu-id="c0123-110">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="c0123-111">如果伺服器與私人網路絡外的實體互動，可能需要公用 CA。</span><span class="sxs-lookup"><span data-stu-id="c0123-111">If the server interacts with entities outside the private network, a public CA might be required.</span></span>
  
<span data-ttu-id="c0123-112">即使憑證上的資訊有效，也必須以某種方式來確認出示證書的伺服器確實是憑證所代表的那一種。</span><span class="sxs-lookup"><span data-stu-id="c0123-112">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate.</span></span> <span data-ttu-id="c0123-113">這是 Windows PKI 隨附的位置。</span><span class="sxs-lookup"><span data-stu-id="c0123-113">This is where the Windows PKI comes in.</span></span>
  
<span data-ttu-id="c0123-114">每個憑證都連結到一個公開金鑰。</span><span class="sxs-lookup"><span data-stu-id="c0123-114">Each certificate is linked to a public key.</span></span> <span data-ttu-id="c0123-115">憑證上命名的伺服器會擁有只有它知道的對應私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="c0123-115">The server named on the certificate holds a corresponding private key that only it knows.</span></span> <span data-ttu-id="c0123-116">連線用戶端或伺服器會使用公開金鑰來加密一段隨機資訊，並將它傳送給伺服器。</span><span class="sxs-lookup"><span data-stu-id="c0123-116">A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server.</span></span> <span data-ttu-id="c0123-117">如果伺服器將資訊解密並以純文字格式傳回，則連接實體可以確保伺服器將私密金鑰儲存在憑證上，因此是在憑證上命名的伺服器。</span><span class="sxs-lookup"><span data-stu-id="c0123-117">If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0123-118">並非所有公用 Ca 都符合商務用 Skype Server 憑證的需求。</span><span class="sxs-lookup"><span data-stu-id="c0123-118">Not all public CAs comply with the requirements of Skype for Business Server certificates.</span></span> <span data-ttu-id="c0123-119">我們建議您參考認證的公用 CA 廠商清單，以瞭解您的公用證書需求。</span><span class="sxs-lookup"><span data-stu-id="c0123-119">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="c0123-120">如需詳細資訊，請參閱[整合通訊憑證合作夥伴](https://go.microsoft.com/fwlink/p/?LinkId=140898)。</span><span class="sxs-lookup"><span data-stu-id="c0123-120">For details, see [Unified Communications Certificate Partners](https://go.microsoft.com/fwlink/p/?LinkId=140898).</span></span> 
  
## <a name="crl-distribution-points"></a><span data-ttu-id="c0123-121">CRL 發佈點</span><span class="sxs-lookup"><span data-stu-id="c0123-121">CRL Distribution Points</span></span>

<span data-ttu-id="c0123-122">商務用 Skype 伺服器需要所有伺服器憑證，才能包含一或多個憑證吊銷清單（CRL）發佈點。</span><span class="sxs-lookup"><span data-stu-id="c0123-122">Skype for Business Server requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="c0123-123">CRL 發佈點（Cdp）是可供您下載 Crl 的位置，目的是確認憑證在發行之後，且證書仍在有效期限內。</span><span class="sxs-lookup"><span data-stu-id="c0123-123">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="c0123-124">CRL 發佈點在憑證的屬性中以 URL 的形式注明，通常是安全的 HTTP。</span><span class="sxs-lookup"><span data-stu-id="c0123-124">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>
  
## <a name="enhanced-key-usage"></a><span data-ttu-id="c0123-125">增強型金鑰用法</span><span class="sxs-lookup"><span data-stu-id="c0123-125">Enhanced Key Usage</span></span>

<span data-ttu-id="c0123-126">商務用 Skype 伺服器需要所有伺服器憑證來支援增強型金鑰用法（EKU），以用於伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="c0123-126">Skype for Business Server requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="c0123-127">針對伺服器驗證設定 EKU 欄位，表示憑證是有效的，目的在於驗證服務器。</span><span class="sxs-lookup"><span data-stu-id="c0123-127">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="c0123-128">此 EKU 對於 MTLS 而言是必要的。</span><span class="sxs-lookup"><span data-stu-id="c0123-128">This EKU is essential for MTLS.</span></span> <span data-ttu-id="c0123-129">在 EKU 中可能會有一個以上的專案，讓憑證可用於多種用途。</span><span class="sxs-lookup"><span data-stu-id="c0123-129">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>
  

