---
title: 定義新主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 您可以透過提供下列資訊來定義新的會話初始通訊協定 (SIP) 主幹：
ms.openlocfilehash: 4addcfbdb854de223f7942f55e2e2180136f9bbc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218554"
---
# <a name="define-a-new-trunk"></a>定義新主幹

您可以透過提供下列資訊來定義新的會話初始通訊協定 (SIP) 主幹：

- **主幹名稱**：您的拓撲中的唯一名稱，可識別此主幹

- **關聯的 PSTN 閘道**：從清單中選取部署中已部署及設定的 pstn 閘道

- **IP/PSTN 閘道的聆聽埠**： IP-PBX 或 PSTN 閘道將接聽的埠。 必須是部署中所設定之所有其他主幹偵聽埠的唯一

- **SIP 傳輸通訊協定**：從清單中選取 [TCP] 或 [TLS]

- **關聯**的轉送伺服器：從清單中選取部署中已部署及設定的轉送伺服器

- **關聯的轉送伺服器埠**：設定的埠值等於此 SIP 主幹將使用之轉送伺服器的 TCP 或 TLS 埠值。

## <a name="see-also"></a>請參閱

[在商務用 Skype Server 2015 中 M:N 主幹](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[如何執行 SIP 主幹？](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
