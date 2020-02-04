---
title: 前端中繼服務設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 您可以在此對話方塊中編輯 [轉送伺服器 PSTN 閘道] 設定的屬性。 您定義下列設定：
ms.openlocfilehash: bd24c24d14e24ed7e4ce53bc30d01b2e955be6cf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697278"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>前端中繼服務設定展開工具 (適用於 Lync Server 2010)
 
您可以在此對話方塊中編輯 [**轉送伺服器 PSTN 閘道**] 設定的屬性。 您定義下列設定：
  
- 如果您想要 collocate 使用此前端伺服器或前端池的中繼伺服器，請選取 [**已啟用的 Collocated 中繼伺服器**]。
    
- **偵聽埠**：定義轉送伺服器將偵聽的埠。 您可以為**TLS**或傳輸層安全性（或**TCP**）或傳輸控制通訊協定定義埠。 若要使用 TCP 的埠專案，您必須選取 [**啟用 TCP 埠**] 的核取方塊。 
    
    > [!IMPORTANT]
    > 請參閱您的公用交換電話網絡（PSTN）閘道的檔和設定設定，以判斷您是否需要啟用和定義埠值 TLS、TCP 或兩者。 TLS 是更安全的通訊協定，使用憑證來加密中繼伺服器與 PSTN 閘道之間的流量。 並非所有 PSTN 閘道都支援 TLS。 
  
- 目前相關聯及現有的 [主幹]**** (亦即工作階段初始通訊協定 (SIP) 主幹)、[閘道]**** (PSTN 閘道或 IP-PBX) 及 [網站]**** (為主幹和閘道設定的網站) 清單。
    
- 您可以選取 [主幹]、[閘道] 及 [站台]，然後按一下 [成為預設]**** 將這些選項設為此中繼服務的預設值。您也可以選取目前的預設值，然後按一下 [取消預設]**** 移除這些選項，使其不再是目前的預設值，然後選取新的預設值，再按一下 [成為預設]****。
    
  **確定**：接受並認可對話方塊的變更。
  
  **取消**：捨棄變更，並關閉對話方塊。
  
  **說明**：顯示此說明畫面。
  

