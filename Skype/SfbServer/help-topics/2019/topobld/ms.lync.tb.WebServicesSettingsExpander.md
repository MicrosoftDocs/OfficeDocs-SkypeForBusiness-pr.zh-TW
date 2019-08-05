---
title: Web 服務設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: 從拓撲建立器中, 您可以修改內部和外部 web 服務所使用的埠設定。 此外, 如果您要部署網域名稱系統 (DNS) 負載平衡, 您可以使用 [拓撲建立器] 來設定解析為該池中所有伺服器之物理 IP 位址的 [池] 完整功能變數名稱 (FQDN)。
ms.openlocfilehash: d3902b4dc54e15dc132fae09404e1b053b046b5e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193866"
---
# <a name="web-services-settings-expander"></a>Web 服務設定展開工具
 
從拓撲建立器中, 您可以修改內部和外部 web 服務所使用的埠設定。 此外, 如果您要部署網域名稱系統 (DNS) 負載平衡, 您可以使用 [拓撲建立器] 來設定解析為該池中所有伺服器之物理 IP 位址的 [池] 完整功能變數名稱 (FQDN)。
  
### <a name="editing-web-services-settings"></a>編輯 Web 服務設定

1. 選取適當的 Standard Edition 前端伺服器或適當的 Enterprise Edition 前端集區，然後按一下 [編輯內容]****。
    
2. 在 [編輯內容]**** 對話方塊中，按一下 [Web 服務]**** 索引標籤。
    
    > [!CAUTION]
    > 如果您有多個前端池或前端伺服器, 則外部 Web 服務 FQDN 必須是唯一的。 例如, 如果您將前端伺服器的外部 Web 服務 FQDN 定義為**pool01.contoso.com**, 則無法將**pool01.contoso.com**用於另一個前端池或前端伺服器。 如果您也要部署控制器, 則為任何主管或主管池定義的外部 Web 服務 FQDN, 都必須是與任何其他控制器或主管池以及任何前端池或前端伺服器的唯一名稱。 如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務, 則每個 FQDN 都必須是與任何其他的前端池、控制器或主管池都是唯一的。
  
3. 如果您編輯 Enterprise Edition 集區的內容，則有 [覆寫 FQDN]**** 的選項可選。 只有當您使用網域名稱系統 (DNS) 負載平衡時，才應選取此選項。 如果您使用 DNS 負載平衡，請選取 [覆寫 FQDN]****，然後在文字方塊中輸入集區的 FQDN，以解析至該集區中所有伺服器的實體 IP 位址。 如果您未使用 DNS 負載平衡，且未選取 [覆寫 FQDN]****，則無法變更內部 Web 服務 FQDN。 內部 web 服務 FQDN 是內部使用者用來連線到商務用 Skype Server 的 URL。
    
4. (選用) 在 [聆聽連接埠]**** 和 [發行的連接埠]**** 中輸入新的 HTTP、HTTPS 或是 HTTP 和 HTTPS 值。聆聽連接埠是 Internet Information Services (IIS) 用來聆聽傳入工作階段初始通訊協定 (SIP) 流量的連接埠；發行的連接埠是在負載平衡器或反向 Proxy 伺服器上設定的連接埠，同樣用來聆聽傳入 SIP 流量。根據預設，HTTP 聆聽連接埠和 HTTP 發行的連接埠都設為連接埠 80；對應的 HTTPS 連接埠都設為 443。兩個 HTTP 發行的連接埠的預設值都是 8080，對應的 HTTPS 連接埠設為 4443。
    
5. 按一下 [確定]****。
    
如果您修改內部 FQDN 或任何聆聽連接埠指派，則必須在集區中的所有伺服器上重新執行本機安裝程式，這些變更才會生效。
  

