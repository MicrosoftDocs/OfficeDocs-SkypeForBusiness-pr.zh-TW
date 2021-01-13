---
title: 適用于商務用 Skype Server 的 TLS 及 MTLS
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
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: 傳輸層安全性 (TLS) 與相互傳輸層安全性 (MTLS) 通訊協定提供網際網路上的加密通訊和端點驗證。 商務用 Skype Server 使用這兩種通訊協定建立信任的伺服器網路，並確保所有透過該網路的通訊都已加密。 伺服器之間的所有 SIP 通訊都透過 MTLS 進行。 從用戶端到伺服器的 SIP 通訊會透過 TLS 進行。
ms.openlocfilehash: 7acc75ef35a9fe9c3f155ca31f06ac38df371e37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832013"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>適用于商務用 Skype Server 的 TLS 及 MTLS
 
傳輸層安全性 (TLS) 與相互傳輸層安全性 (MTLS) 通訊協定提供網際網路上的加密通訊和端點驗證。 商務用 Skype Server 使用這兩種通訊協定建立信任的伺服器網路，並確保所有透過該網路的通訊都已加密。 伺服器之間的所有 SIP 通訊都透過 MTLS 進行。 從用戶端到伺服器的 SIP 通訊會透過 TLS 進行。
  
TLS 可讓使用者透過用戶端軟體來驗證其所連接的商務用 Skype 伺服器伺服器。 在 TLS 連接上，用戶端會從伺服器要求有效的憑證。 若是有效的，則憑證必須由用戶端也信任的 CA 所發出，而且伺服器的 DNS 名稱必須符合憑證上的 DNS 名稱。 如果憑證有效，用戶端會使用憑證中的公開金鑰來加密要用於通訊的對稱加密金鑰，所以只有憑證的原始擁有者可以使用私密金鑰來解密通訊的內容。 產生的連線是受信任的，而來自于其他受信任的伺服器或用戶端不會有任何挑戰。 在此內容中，安全通訊端層 (SSL) （用於 Web 服務）可以與 TLS 基礎相關聯。
  
伺服器對伺服器連線依賴 MTLS 進行相互驗證。 在 MTLS 連線上，發起郵件的伺服器及接收它的伺服器會從相互信任的 CA 交換憑證。 憑證會將每個伺服器的身分識別證明為另一部伺服器。 在商務用 Skype Server 部署中，由所有內部用戶端和伺服器所發行的企業 CA 所發行的憑證，會自動視為所有內部用戶端和伺服器都有效，因為 Active Directory 網域的所有成員都信任該網域中的企業 CA。 在同盟案例中，雙方同盟協力廠商都必須信任發證 CA。 如有需要，每個合作夥伴都可以使用不同的 CA，只要另一個夥伴也信任該 CA。 當 Edge Server 具有夥伴的根 CA 憑證的根信任 Ca，或使用雙方所信任的協力廠商 CA 時，這項信任就會順利完成。
  
TLS 和 MTLS 可協助防止偷聽和中間人攻擊。 在中間人攻擊中，攻擊者會透過攻擊者的電腦重排兩個網路實體之間的通訊，而不需要任何一方的知識。 受信任伺服器的 TLS 和商務用 Skype Server 規格，只 (在) 拓撲產生器中所指定的伺服器，並使用這兩個端點之間的公開金鑰密碼編譯，以降低部分對應用程式層上之中間人攻擊的風險。而且，攻擊者必須具有對應私密金鑰的有效且受信任的憑證，而且會發佈給用戶端通訊的服務名稱，以解密通訊。 不過，最後，您必須遵循網路基礎結構的最佳安全性作法， (在此案例中的公司 DNS) 。 商務用 Skype Server 假設 DNS 伺服器的信任方式與網域控制站和通用類別目錄的信任方式相同，但 DNS 可防止攻擊者的伺服器以成功回應哄騙名稱的要求，而對 DNS 劫持攻擊提供保護層級。
  

