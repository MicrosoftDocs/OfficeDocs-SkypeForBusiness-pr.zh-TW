---
title: 前端中繼服務設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 您可以在此對話方塊中，編輯 [中繼伺服器 PSTN 閘道] 設定的屬性。 您可以定義下列設定：
ms.openlocfilehash: ad6aab0ce528db01621b1d43a62624d96649e66a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807053"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>前端中繼服務設定展開工具 (適用於 Lync Server 2010)
 
您可以在此對話方塊中，編輯 [中繼伺服器 PSTN 閘道] 設定的屬性。 您可以定義下列設定：
  
- 如果您想要使用此前端伺服器或前端集區來組合轉送伺服器，請選取 [ **已啟用的組合轉送伺服器** ]。
    
- **聆聽埠**：定義轉送伺服器將接聽的埠。 您可以定義 TLS (傳輸層安全性) 或 TCP (傳輸控制通訊協定) 連接埠。 若要使用 TCP 連接埠項目，您必須選取 [啟用 TCP 連接埠] 核取方塊。 
    
    > [!IMPORTANT]
    > 請參閱公用交換電話網路 (PSTN) 閘道的文件和組態設定，以決定是否需要啟用及定義連接埠值 TLS 及 (或) TCP。 TLS 是一種更安全的通訊協定，使用憑證來加密轉送伺服器和 PSTN 閘道之間的流量。 並非所有 PSTN 閘道都支援 TLS。 
  
- 目前相關聯及現有的 [主幹] (亦即工作階段初始通訊協定 (SIP) 主幹)、[閘道] (PSTN 閘道或 IP-PBX) 及 [網站] (為主幹和閘道設定的網站) 清單。
    
- 您可以選取 [主幹]、[閘道] 及 [網站]，然後按一下 [成為預設] 將這些選項設為此中繼服務的預設值。您也可以選取目前的預設值，然後按一下 [取消預設] 移除這些選項，使其不再是目前的預設值，然後選取新的預設值，再按一下 [成為預設]。
    
  **確定**：接受並認可對話方塊的變更。
  
  **取消**：捨棄變更，並關閉對話方塊。
  
  **說明**：顯示此說明畫面。
  

