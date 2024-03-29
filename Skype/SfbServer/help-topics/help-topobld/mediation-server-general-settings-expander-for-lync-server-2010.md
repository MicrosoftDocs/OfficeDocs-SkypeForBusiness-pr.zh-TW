---
title: 中繼伺服器一般設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 您可以在此對話方塊中編輯轉送伺服器的屬性。 左側是可前往 [一般] 設定、[下一個躍點] 設定及 [ PSTN 閘道] 設定的一組快速連結。 每個區段包含下列設定：
ms.openlocfilehash: 8277c34a01ac3ba1a487688fe511af174dd6db99
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396595"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>中繼伺服器一般設定展開工具 (適用於 Lync Server 2010)

您可以在此對話方塊中編輯轉送伺服器的屬性。 左側是可前往 [一般] 設定、[下一個躍點] 設定及 [ PSTN 閘道] 設定的一組快速連結。 每個區段包含下列設定：

 **一般**：

- **FQDN**：編輯轉送伺服器的完整功能變數名稱

- **關聯**：選取 [ **關聯 edge 集區 (的媒體) 元件** ] 核取方塊，然後選取要用來做為外部存取之媒體路徑的轉送伺服器的 edge Server 或 edge 集區。

  **下一個躍點**：

- **下一個躍點選取**：從清單中選取前端伺服器或前端集區，以作為轉送伺服器的路徑，以用於與您的部署進行通訊。

  **PSTN 閘道**：

  **中繼伺服器 PSTN 閘道**：

- **聆聽埠**：定義轉送伺服器將接聽的埠。 您可以定義 TLS (傳輸層安全性) 或 TCP (傳輸控制通訊協定) 連接埠。 若要使用 TCP 連接埠項目，您必須選取 [啟用 TCP 連接埠] 核取方塊。

    > [!IMPORTANT]
    > 請參閱公用交換電話網路 (PSTN) 閘道的文件和組態設定，以決定是否需要啟用及定義連接埠值 TLS 及 (或) TCP。 TLS 是一種更安全的通訊協定，使用憑證來加密轉送伺服器和 PSTN 閘道之間的流量。 並非所有 PSTN 閘道都支援 TLS。

- 以下列出針對部署定義及設定的 SIP 主幹和閘道清單。 如果不存在任何項目，則部署未設定任何 SIP 主幹 PSTN 閘道。 您可以在拓撲產生器中定義及設定 [ **共用元件** ] 底下的主幹與閘道。

## <a name="see-also"></a>另請參閱

[SIP 主幹連線概觀](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[PSTN 閘道部署選項](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)