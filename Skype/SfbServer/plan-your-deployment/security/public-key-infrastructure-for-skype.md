---
title: 商務用 Skype Server 的公用金鑰基礎結構
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: 商務用 Skype Server 取決於伺服器驗證的憑證，並在用戶端與伺服器之間，以及不同的伺服器角色間建立信任鏈。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 及 Windows Server 2008 公開金鑰基礎結構 (PKI) 提供基礎結構，用以建立及驗證此信任鏈。
ms.openlocfilehash: 733b1bb946147edd184a7b0fecb16ffab2adba51
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627925"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>商務用 Skype Server 的公用金鑰基礎結構
 
商務用 Skype Server 取決於伺服器驗證的憑證，並在用戶端與伺服器之間，以及不同的伺服器角色間建立信任鏈。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 及 Windows Server 2008 公開金鑰基礎結構 (PKI) 提供基礎結構，用以建立及驗證此信任鏈。
  
憑證是數位 IDs。 它們會以名稱識別伺服器，並指定其屬性。 為了確保憑證上的資訊有效，憑證必須由用戶端或連接至伺服器的其他伺服器所信任的 CA 所發出。 如果伺服器只與私人網路絡上的其他用戶端和伺服器連線，則 CA 可以是企業 CA。 如果伺服器與私人網路絡外的實體互動，則可能需要公用 CA。
  
即使憑證上的資訊有效，仍然必須以某種方式驗證提供憑證的伺服器確實是憑證所代表的伺服器。 這是 Windows PKI 的所在位置。
  
每一個憑證都會連結到公開金鑰。 憑證上命名的伺服器擁有只有本身知道的對應私密金鑰。 連接的用戶端或伺服器會使用公開金鑰加密資訊的任意片段，並將它傳送至伺服器。 如果伺服器解密資訊並將其傳回為純文字，則連接實體可以確定伺服器是否要將私密金鑰保留在憑證中，因此是憑證中命名的伺服器。
  
> [!NOTE]
> 並非所有公用 ca 都符合商務用 Skype Server 憑證的需求。 我們建議您參考已驗證的公用 CA 廠商清單，以滿足您的公用憑證需求。 如需詳細資訊，請參閱 [整合通訊憑證合作夥伴](https://go.microsoft.com/fwlink/p/?LinkId=140898)。 
  
## <a name="crl-distribution-points"></a>CRL 發佈點

商務用 Skype Server 要求所有伺服器憑證都包含一或多個憑證吊銷清單 (CRL) 發佈點。 CRL 發佈點 (Cdp) 是可從中下載 Crl 的位置，目的在於驗證憑證自發行之後起尚未撤銷，且憑證仍在有效期限內。 CRL 發佈點會在憑證的內容中注明為 URL，且通常為安全的 HTTP。
  
## <a name="enhanced-key-usage"></a>增強型金鑰使用方式

商務用 Skype Server 需要所有伺服器憑證才能支援針對伺服器驗證目的 (EKU) 的增強金鑰使用方式。 設定 [伺服器驗證的 EKU] 欄位表示憑證是有效的，目的在於驗證服務器。 這個 EKU 對 MTLS 而言是必要的。 您可以在 EKU 中有一個以上的專案，為憑證啟用一個以上的目的。
  

