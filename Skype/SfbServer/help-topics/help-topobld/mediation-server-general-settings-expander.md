---
title: 中繼伺服器一般設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: bd3047832b23604f87a1e298a42798b13bb6822a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215164"
---
# <a name="mediation-server-general-settings-expander"></a>中繼伺服器一般設定展開工具
 


## <a name="general-settings"></a>一般設定

中繼伺服器集區或中繼伺服器的完整網域名稱 (FQDN)。編輯伺服器的 FQDN 會變更此值。您必須有符合新值的網域名稱系統 (DNS) 主機 (A) 記錄。
  
在 [關聯]**** 區段中，選取要與中繼伺服器集區或中繼伺服器關聯的 Edge Server 或 Edge Server 集區。 您選取的邊界是轉送伺服器的媒體元件將用於外部使用者 Enterprise Voice。
  
如果您目前並未定義 Edge Server，而需要將中繼伺服器與 Edge Server 關聯，請按一下 [新增]**** 並在 [定義新的 Edge 集區精靈] 中定義新的 Edge Server 或 Edge Server 集區。
  
## <a name="next-hop-settings"></a>下一個躍點設定

您可以從下拉式清單中選取定義的 Enterprise Edition 前端集區或 Standard Edition 前端伺服器，指定中繼伺服器集區或中繼伺服器的下一個躍點。 Director 或 Director 集區不是中繼伺服器集區或中繼伺服器下一個躍點的有效選項，亦不會顯示在清單中。 按一下 **[確定]** 以接受並儲存變更。 按一下 [取消]**** 捨棄變更並結束內容頁面。
  
## <a name="pstn-gateway-settings"></a>PSTN 閘道設定

1. 您將定義與中繼伺服器集區或中繼伺服器關聯的 PSTN 閘道。如果已經定義閘道，可以將其用來與中繼伺服器相關聯。如果您啟用中繼伺服器的組合，便會在集區伺服器上針對傳輸層安全性 (TLS) 定義聆聽連接埠範圍。此連接埠預設為 5067。如果您選取 [啟用 TCP 連接埠]****，則必須為組合的中繼伺服器定義傳輸控制通訊協定 (TCP) 連接埠。這是選用的設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。TCP 連接埠值預設為 5068。
    
2. 與組合中繼伺服器相關聯的主幹。如果已經定義主幹，可以將其用來與中繼伺服器相關聯。 
    
3. 如果您有多個主幹與中繼伺服器相關聯，您可以選取主幹，然後按一下 [成為預設]**** 指定預設主幹。若要取消選取成為預設的閘道，請按一下 [取消預設]****。 
    

