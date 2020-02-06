---
title: 中繼伺服器一般設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: be969f1dc3c860ccae3cd12b4e86d4b9e97788f2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796222"
---
# <a name="mediation-server-general-settings-expander"></a>中繼伺服器一般設定展開工具
 


## <a name="general-settings"></a>一般設定

中繼伺服器池或中繼伺服器的完整功能變數名稱（FQDN）。 編輯伺服器的 FQDN 會變更此值。 您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。
  
在 [**關聯**性] 區段中，選取 [邊緣伺服器] 或 [edge 伺服器] 池，以與中繼伺服器池或轉送伺服器伺服器建立關聯。 您選取轉送伺服器媒體元件將用於外部使用者企業語音的邊緣。
  
如果您目前未定義 Edge 伺服器，且需要將中繼伺服器與 Edge 伺服器關聯，請按一下 [**新增**]，然後在 [定義新的邊緣池] 嚮導中定義新的 edge 伺服器或 edge 伺服器池。
  
## <a name="next-hop-settings"></a>下一個躍點設定

您可以從下拉式清單中選取已定義的企業版前端池或標準版前端伺服器，以指定中繼伺服器池或中繼伺服器的下一個躍點。 主管或主管池不是中繼伺服器池或中繼伺服器下一個躍點的有效選取範圍，且不會出現在清單中。 按一下 **[確定]** 接受並儲存您的變更。 按一下 [取消]**** 捨棄變更並結束內容頁面。
  
## <a name="pstn-gateway-settings"></a>PSTN 閘道設定

1. 您定義與中繼伺服器池或轉送伺服器伺服器相關聯的 PSTN 閘道。 如果您已定義閘道，就可以將它們與中繼伺服器建立關聯。 如果您啟用中繼伺服器的組合，便會在集區伺服器上針對傳輸層安全性 (TLS) 定義聆聽連接埠範圍。 此連接埠預設為 5067。 如果您選取 [啟用 TCP 連接埠]****，則必須為組合的中繼伺服器定義傳輸控制通訊協定 (TCP) 連接埠。 這是選用的設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。 TCP 連接埠值預設為 5068。
    
2. 與組合中繼伺服器相關聯的主幹。如果已經定義主幹，可以將其用來與中繼伺服器相關聯。 
    
3. 如果您有多個與中繼伺服器相關聯的幹線，您可以選取主幹，然後按一下 [**設為預設值**] 來指定預設幹線。 若要取消選取成為預設的閘道，請按一下 [取消預設]****。 
    

