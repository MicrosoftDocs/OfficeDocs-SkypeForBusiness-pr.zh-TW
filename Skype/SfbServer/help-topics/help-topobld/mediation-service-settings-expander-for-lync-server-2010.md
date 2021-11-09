---
title: 中繼服務設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 您可以透過定義下列內容來編輯中繼服務的內容：
ms.openlocfilehash: 982d75a63818b3c548bcdea0e26504adfc5ff2e1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862560"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>中繼服務設定展開工具 (適用於 Lync Server 2010)
 
您可以透過定義下列內容來編輯中繼服務的內容：
  
- **聆聽連接埠**：定義中繼服務聆聽的 [TLS] 連接埠。連接埠值預設為 TCP 5067 (透過傳輸層安全性 (TLS))
    
    或者，定義 [TCP] 連接埠值。預設值為 TCP 5068。
    
    > [!NOTE]
    > 選取 [啟用 TCP 連接埠] 即可啟用 TCP 連接埠值設定。您應該參考公用交換電話網路 (PSTN) 閘道或網際網路通訊協定專用交換機 (IP-PBX) 文件中，有關與中繼服務通訊所需的連接埠設定需求。 
  
- 您可以啟用 TCP 連接埠定義從 PSTN 閘道或 IP-PBX 進行通訊的 TCP 連接埠值。
    
- 目前相關聯及現有的 [主幹] (亦即工作階段初始通訊協定 (SIP) 主幹)、[閘道] (PSTN 閘道或 IP-PBX) 及 [網站] (為主幹和閘道設定的網站) 清單。
    
- 您可以選取 [主幹]、[閘道] 及 [網站]，然後按一下 [成為預設] 將這些選項設為此中繼服務的預設值。您也可以選取目前的預設值，然後按一下 [取消預設] 移除這些選項，使其不再是目前的預設值，然後選取新的預設值，再按一下 [成為預設]。
    
  **確定**：接受並認可對話方塊的變更。
  
  **取消**：捨棄變更，並關閉對話方塊。
  
  **說明**：顯示此說明畫面。
  

