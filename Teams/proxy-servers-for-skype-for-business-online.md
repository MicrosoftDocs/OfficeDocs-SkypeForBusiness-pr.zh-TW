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
- seo-marvel-apr2020
description: 本文提供有關在 Microsoft 團隊或商務用 Skype 中使用 proxy 伺服器的資訊。
ms.openlocfilehash: 5a0d35ee2b8c95c4dea30886497e184f57077264
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905675"
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
    
- 遵循我們的網路指導方針中的其他建議：[針對團隊準備貴組織的網路](prepare-network.md)
  
    
遵循此指導方針應該將潛在問題降至最低。
  
## <a name="related-topics"></a>相關主題

[Office 365 網路連接原則](https://aka.ms/pnc)

[針對 Teams 準備組織的網路](prepare-network.md)
