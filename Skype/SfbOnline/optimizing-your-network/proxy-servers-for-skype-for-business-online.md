---
title: 適用於 Microsoft Teams 或商務用 Skype® 2015 Online 的 Proxy 伺服器
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 本文提供有關在用戶端使用 proxy 伺服器商務用 Skype。
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240412"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>適用于 商務用 Skype Online 的 Proxy 伺服器

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文提供有關在用戶端使用 proxy 伺服器商務用 Skype。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建議您不要使用 Proxy 伺服器

當涉及代理商務用 Skype流量時，Microsoft 建議忽略代理。 由於流量已加密商務用 Skype代理不會讓資料更安全。
  
而擁有 Proxy 可能會導致問題。 透過延遲和封包遺失，可能會將與績效相關的問題引入環境。 這類問題會導致音訊和視Teams或商務用 Skype等情況下的負面體驗，而即時資料流是不可或缺的。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果您需要使用 Proxy 伺服器

有些組織無法針對流量忽略 proxy商務用 Skype。 如果是這種情況，您必須記住上述問題。
  
Microsoft 也強烈建議您：
  
- 使用外部 DNS 解析
    
- 使用直接 UDP 路由
    
- 允許 UDP 流量
    
- 遵循我們的網路指導方針中的其他建議：
    
  - [線上媒體質量與網路連線商務用 Skype](media-quality-and-network-connectivity-performance.md)
    
  - [優化您的網路以商務用 Skype Online](optimizing-your-network.md)
    
遵循此指引應能將潛在問題降到最低。
  
## <a name="related-topics"></a>相關主題

[優化您的網路以商務用 Skype Online](optimizing-your-network.md)
 
