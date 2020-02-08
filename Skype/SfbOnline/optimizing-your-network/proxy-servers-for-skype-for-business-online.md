---
title: Teams 或商務用 Skype Online 的 Proxy 伺服器
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
description: 本文提供在商務用 Skype 中使用 proxy 伺服器的相關資訊。
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863746"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>商務用 Skype Online 的 Proxy 伺服器

本文提供有關在商務用 Skype 中使用 proxy 伺服器的指導方針。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建議您不要使用 proxy 伺服器

如果是來自 proxy 的商務用 Skype 流量，Microsoft 建議您回避 proxy。 Proxy 不會讓商務用 Skype 更加安全，因為通訊已加密。
  
而且擁有 proxy 可能會造成問題。 效能相關問題可透過延遲與資料包遺失來引進環境。 這類問題將導致在這些團隊或商務用 Skype 案例中使用音訊和影片的負面體驗，因為即時資料流非常重要。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果您需要使用 proxy 伺服器

有些組織沒有任何選項可讓商務用 Skype 流量略過 proxy。 如果是這種情況，上述問題必須牢記在前面。
  
Microsoft 也強烈建議：
  
- 使用外部 DNS 解析
    
- 使用直接的以 UDP 為基礎的路由
    
- 允許 UDP 流量
    
- 遵循我們的網路指導方針中的其他建議：
    
  - [商務用 Skype Online 中的媒體質量和網路連線效能](media-quality-and-network-connectivity-performance.md)
    
  - [針對商務用 Skype Online 優化您的網路](optimizing-your-network.md)
    
遵循此指導方針應該將潛在問題降至最低。
  
## <a name="related-topics"></a>相關主題

[針對商務用 Skype Online 優化您的網路](optimizing-your-network.md)
 