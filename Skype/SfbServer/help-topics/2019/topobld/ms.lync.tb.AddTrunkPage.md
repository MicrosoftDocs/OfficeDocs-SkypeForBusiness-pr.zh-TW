---
title: 定義新主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以提供下列資訊來定義新的會話初始通訊協定（SIP）主幹：
ms.openlocfilehash: 17f6b72f1234813e717cfc72be60bb5f0352134a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794312"
---
# <a name="define-a-new-trunk"></a>定義新主幹

您可以提供下列資訊來定義新的會話初始通訊協定（SIP）主幹：

- **主幹名稱**：拓撲中要識別此主幹的唯一名稱

- **關聯的 PSTN 閘道**：從清單中選取部署和已設定的 pstn 閘道

- **Ip/PSTN 閘道的偵聽埠**： ip PBX 或 PSTN 閘道將接聽的埠。 在您部署中設定的所有其他中繼偵聽埠都必須是唯一的

- **SIP 傳輸通訊協定**：從清單中選取 [TCP] 或 [TLS]

- **關聯的中繼伺服器**：從清單中選取在您的部署中部署並設定的中繼伺服器

- **關聯的中繼伺服器埠**：將埠值設定為等於此 SIP 幹線將使用之中繼伺服器的 TCP 或 TLS 埠值

## <a name="see-also"></a>另請參閱

[商務用 Skype Server 中的 M:N 幹線](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[如何實作 SIP 主幹？](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
