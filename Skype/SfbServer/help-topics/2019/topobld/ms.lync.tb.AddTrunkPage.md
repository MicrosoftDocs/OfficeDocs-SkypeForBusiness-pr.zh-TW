---
title: 定義新主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: '您可以提供下列資訊來定義新的會話初始通訊協定 (SIP) 主幹:'
ms.openlocfilehash: c6586f9da069c3a3fc149b086562592db113b31e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189505"
---
# <a name="define-a-new-trunk"></a>定義新主幹

您可以提供下列資訊來定義新的會話初始通訊協定 (SIP) 主幹:

- **主幹名稱**: 拓撲中要識別此主幹的唯一名稱

- **關聯的 PSTN 閘道**: 從清單中選取部署和已設定的 pstn 閘道

- **Ip/PSTN 閘道的偵聽埠**: ip PBX 或 PSTN 閘道將接聽的埠。 在您部署中設定的所有其他中繼偵聽埠都必須是唯一的

- **SIP 傳輸通訊協定**: 從清單中選取 [TCP] 或 [TLS]

- **關聯的中繼伺服器**: 從清單中選取在您的部署中部署並設定的中繼伺服器

- **關聯的中繼伺服器埠**: 將埠值設定為等於此 SIP 幹線將使用之中繼伺服器的 TCP 或 TLS 埠值

## <a name="see-also"></a>另請參閱

[商務用 Skype Server 中的 M:N 幹線](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[如何實作 SIP 主幹？](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
