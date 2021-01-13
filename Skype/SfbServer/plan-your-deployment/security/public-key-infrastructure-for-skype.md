---
title: 商務用 Skype Server 的公用機碼基礎結構
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: 商務用 Skype 伺服器依賴伺服器驗證的憑證，並在用戶端與伺服器之間，以及不同的伺服器角色間建立信任鏈。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 和 Windows Server 2008 公開金鑰基礎結構 (PKI) 提供基礎結構，用以建立及驗證此信任鏈。
ms.openlocfilehash: 3ee9411b5a9259ba7c66c46bf657bb5ee43ab52e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832143"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a><span data-ttu-id="8d385-104">商務用 Skype Server 的公用機碼基礎結構</span><span class="sxs-lookup"><span data-stu-id="8d385-104">Public Key Infrastructure for Skype for Business Server</span></span>
 
<span data-ttu-id="8d385-105">商務用 Skype 伺服器依賴伺服器驗證的憑證，並在用戶端與伺服器之間，以及不同的伺服器角色間建立信任鏈。</span><span class="sxs-lookup"><span data-stu-id="8d385-105">Skype for Business Server relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="8d385-106">Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 和 Windows Server 2008 公開金鑰基礎結構 (PKI) 提供基礎結構，用以建立及驗證此信任鏈。</span><span class="sxs-lookup"><span data-stu-id="8d385-106">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, and Windows Server 2008 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>
  
<span data-ttu-id="8d385-107">憑證是數位 IDs。</span><span class="sxs-lookup"><span data-stu-id="8d385-107">Certificates are digital IDs.</span></span> <span data-ttu-id="8d385-108">它們會以名稱識別伺服器，並指定其屬性。</span><span class="sxs-lookup"><span data-stu-id="8d385-108">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="8d385-109">為了確保憑證上的資訊有效，憑證必須由用戶端或連接至伺服器的其他伺服器所信任的 CA 所發出。</span><span class="sxs-lookup"><span data-stu-id="8d385-109">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="8d385-110">如果伺服器只與私人網路絡上的其他用戶端和伺服器連線，則 CA 可以是企業 CA。</span><span class="sxs-lookup"><span data-stu-id="8d385-110">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="8d385-111">如果伺服器與私人網路絡外的實體互動，則可能需要公用 CA。</span><span class="sxs-lookup"><span data-stu-id="8d385-111">If the server interacts with entities outside the private network, a public CA might be required.</span></span>
  
<span data-ttu-id="8d385-112">即使憑證上的資訊有效，仍然必須以某種方式驗證提供憑證的伺服器確實是憑證所代表的伺服器。</span><span class="sxs-lookup"><span data-stu-id="8d385-112">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate.</span></span> <span data-ttu-id="8d385-113">這是 Windows PKI 的所在位置。</span><span class="sxs-lookup"><span data-stu-id="8d385-113">This is where the Windows PKI comes in.</span></span>
  
<span data-ttu-id="8d385-114">每一個憑證都會連結到公開金鑰。</span><span class="sxs-lookup"><span data-stu-id="8d385-114">Each certificate is linked to a public key.</span></span> <span data-ttu-id="8d385-115">憑證上命名的伺服器擁有只有本身知道的對應私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="8d385-115">The server named on the certificate holds a corresponding private key that only it knows.</span></span> <span data-ttu-id="8d385-116">連接的用戶端或伺服器會使用公開金鑰加密資訊的任意片段，並將它傳送至伺服器。</span><span class="sxs-lookup"><span data-stu-id="8d385-116">A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server.</span></span> <span data-ttu-id="8d385-117">如果伺服器解密資訊並將其傳回為純文字，則連接實體可以確定伺服器是否要將私密金鑰保留在憑證中，因此是憑證中命名的伺服器。</span><span class="sxs-lookup"><span data-stu-id="8d385-117">If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d385-118">並非所有公用 Ca 都符合商務用 Skype Server 憑證的需求。</span><span class="sxs-lookup"><span data-stu-id="8d385-118">Not all public CAs comply with the requirements of Skype for Business Server certificates.</span></span> <span data-ttu-id="8d385-119">我們建議您參考已驗證的公用 CA 廠商清單，以滿足您的公用憑證需求。</span><span class="sxs-lookup"><span data-stu-id="8d385-119">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="8d385-120">如需詳細資訊，請參閱 [整合通訊憑證合作夥伴](https://go.microsoft.com/fwlink/p/?LinkId=140898)。</span><span class="sxs-lookup"><span data-stu-id="8d385-120">For details, see [Unified Communications Certificate Partners](https://go.microsoft.com/fwlink/p/?LinkId=140898).</span></span> 
  
## <a name="crl-distribution-points"></a><span data-ttu-id="8d385-121">CRL 發佈點</span><span class="sxs-lookup"><span data-stu-id="8d385-121">CRL Distribution Points</span></span>

<span data-ttu-id="8d385-122">商務用 Skype 伺服器要求所有伺服器憑證包含一或多個憑證吊銷清單 (CRL) 發佈點。</span><span class="sxs-lookup"><span data-stu-id="8d385-122">Skype for Business Server requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="8d385-123">CRL 發佈點 (Cdp) 是可從中下載 Crl 的位置，目的在於驗證憑證自發行之後起尚未撤銷，且憑證仍在有效期限內。</span><span class="sxs-lookup"><span data-stu-id="8d385-123">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="8d385-124">CRL 發佈點會在憑證的內容中注明為 URL，且通常為安全的 HTTP。</span><span class="sxs-lookup"><span data-stu-id="8d385-124">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>
  
## <a name="enhanced-key-usage"></a><span data-ttu-id="8d385-125">增強型金鑰使用方式</span><span class="sxs-lookup"><span data-stu-id="8d385-125">Enhanced Key Usage</span></span>

<span data-ttu-id="8d385-126">商務用 Skype 伺服器要求所有的伺服器憑證，以支援用於伺服器驗證之目的的增強金鑰使用 (EKU) 。</span><span class="sxs-lookup"><span data-stu-id="8d385-126">Skype for Business Server requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="8d385-127">設定 [伺服器驗證的 EKU] 欄位表示憑證是有效的，目的在於驗證服務器。</span><span class="sxs-lookup"><span data-stu-id="8d385-127">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="8d385-128">這個 EKU 對 MTLS 而言是必要的。</span><span class="sxs-lookup"><span data-stu-id="8d385-128">This EKU is essential for MTLS.</span></span> <span data-ttu-id="8d385-129">您可以在 EKU 中有一個以上的專案，為憑證啟用一個以上的目的。</span><span class="sxs-lookup"><span data-stu-id="8d385-129">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>
  

