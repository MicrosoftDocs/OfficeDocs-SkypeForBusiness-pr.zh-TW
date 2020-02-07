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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 本文提供與團隊或商務用 Skype 一起使用 proxy 伺服器的相關資訊。
ms.openlocfilehash: 7eeb319c9c352f4f04abef581b88c1eddf46951d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837303"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams 或商務用 Skype Online 的 Proxy 伺服器

本文提供有關將 proxy 伺服器與團隊或商務用 Skype 結合使用的指導方針。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建議您不要使用 proxy 伺服器

如果是來自 proxy 的小組或商務用 Skype 流量，Microsoft 建議您回避 proxy。 Proxy 不會讓小組或商務用 Skype 更加安全，因為通訊已經過加密。
  
而且擁有 proxy 可能會造成問題。 效能相關問題可透過延遲與資料包遺失來引進環境。 這類問題將導致在這些團隊或商務用 Skype 案例中使用音訊和影片的負面體驗，因為即時資料流非常重要。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果您需要使用 proxy 伺服器

有些組織沒有任何選項可讓小組或商務用 Skype 流量略過。 如果是這種情況，上述問題必須牢記在前面。
  
Microsoft 也強烈建議：
  
- 使用外部 DNS 解析
    
- 使用直接的以 UDP 為基礎的路由
    
- 允許 UDP 流量
    
- 遵循我們的網路指導方針中的其他建議：
    
  - [商務用 Skype Online 中的媒體質量和網路連線效能](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [針對商務用 Skype Online 優化您的網路](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
遵循此指導方針應該將潛在問題降至最低。
  
## <a name="related-topics"></a>相關主題

[針對商務用 Skype Online 優化您的網路](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 