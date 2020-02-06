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
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>商務用 Skype Server 的公開金鑰基礎結構
 
商務用 Skype Server 依賴伺服器驗證的憑證，並在用戶端與伺服器之間以及不同的伺服器角色之間建立信任鏈。 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2 和 Windows Server 2008 公開金鑰基礎結構（PKI）提供建立及驗證此信任鏈的基礎結構。
  
[憑證] 是數位識別碼。 它們會依名稱來識別伺服器，並指定其屬性。 若要確保憑證上的資訊有效，憑證必須由用戶端或連線到伺服器的其他伺服器所信任的 CA 頒發。 如果伺服器只與私人網路絡上的其他用戶端和伺服器連線，則 CA 可以是企業 CA。 如果伺服器與私人網路絡外的實體互動，可能需要公用 CA。
  
即使憑證上的資訊有效，也必須以某種方式來確認出示證書的伺服器確實是憑證所代表的那一種。 這是 Windows PKI 隨附的位置。
  
每個憑證都連結到一個公開金鑰。 憑證上命名的伺服器會擁有只有它知道的對應私密金鑰。 連線用戶端或伺服器會使用公開金鑰來加密一段隨機資訊，並將它傳送給伺服器。 如果伺服器將資訊解密並以純文字格式傳回，則連接實體可以確保伺服器將私密金鑰儲存在憑證上，因此是在憑證上命名的伺服器。
  
> [!NOTE]
> 並非所有公用 Ca 都符合商務用 Skype Server 憑證的需求。 我們建議您參考認證的公用 CA 廠商清單，以瞭解您的公用證書需求。 如需詳細資訊，請參閱[整合通訊憑證合作夥伴](https://go.microsoft.com/fwlink/p/?LinkId=140898)。 
  
## <a name="crl-distribution-points"></a>CRL 發佈點

商務用 Skype 伺服器需要所有伺服器憑證，才能包含一或多個憑證吊銷清單（CRL）發佈點。 CRL 發佈點（Cdp）是可供您下載 Crl 的位置，目的是確認憑證在發行之後，且證書仍在有效期限內。 CRL 發佈點在憑證的屬性中以 URL 的形式注明，通常是安全的 HTTP。
  
## <a name="enhanced-key-usage"></a>增強型金鑰用法

商務用 Skype 伺服器需要所有伺服器憑證來支援增強型金鑰用法（EKU），以用於伺服器驗證。 針對伺服器驗證設定 EKU 欄位，表示憑證是有效的，目的在於驗證服務器。 此 EKU 對於 MTLS 而言是必要的。 在 EKU 中可能會有一個以上的專案，讓憑證可用於多種用途。
  

