---
title: 中繼伺服器一般設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 您可以在此對話方塊中編輯中繼伺服器的屬性。 沿左側是一組快速連結，可將您帶到 [一般設定]、[下個躍點設定] 和 [PSTN 閘道設定] 的設定。 在每個區段中都有下列設定：
ms.openlocfilehash: d439698bf0e383f9c89fb749ef4cedc7ae253997
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684546"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a>中繼伺服器一般設定展開工具 (適用於 Lync Server 2010)

您可以在此對話方塊中編輯中繼伺服器的屬性。 沿左側是一組快速連結，可將您帶到 [一般設定]、[下個躍點設定] 和 [PSTN 閘道設定] 的設定。 在每個區段中都有下列設定：

 **一般**：

- **FQDN**：編輯中繼伺服器的完整功能變數名稱

- **關聯**：選取 [**關聯邊緣池] （適用于 [媒體元件]）** 核取方塊，然後選取要用來做為外部存取媒體路徑的中繼伺服器的邊緣伺服器或邊緣池。

  **下一個躍點**：

- **下一個躍點選取**：從清單中選取 [前端伺服器] 或 [頂層端] 池，以做為用於與您的部署進行通訊的中繼伺服器路徑。

  **PSTN 閘道**：

  **中繼伺服器 PSTN 閘道**：

- **偵聽埠**：定義轉送伺服器將偵聽的埠。 您可以為**TLS**或傳輸層安全性（或**TCP**）或傳輸控制通訊協定定義埠。 若要使用 TCP 的埠專案，您必須選取 [**啟用 TCP 埠**] 的核取方塊。

    > [!IMPORTANT]
    > 請參閱您的公用交換電話網絡（PSTN）閘道的檔和設定設定，以判斷您是否需要啟用和定義埠值 TLS、TCP 或兩者。 TLS 是更安全的通訊協定，使用憑證來加密中繼伺服器與 PSTN 閘道之間的流量。 並非所有 PSTN 閘道都支援 TLS。

- 系統會列出 SIP trunks 及針對您的部署定義及設定的閘道清單。 如果沒有任何專案出現，則表示您的部署沒有設定 SIP trunks 或 PSTN 閘道。 您可以在拓撲建立器中的 [**共用元件**] 底下定義及設定 trunks 和閘道。

## <a name="see-also"></a>另請參閱

[SIP 中繼概覽](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[PSTN 閘道部署選項](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
