---
title: 適用於 Microsoft Teams 或商務用 Skype® 2015 Online 的 Proxy 伺服器
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: 本文提供搭配Microsoft Teams或商務用 Skype使用 Proxy 伺服器的相關資訊。
ms.openlocfilehash: 61a1878b3c7057de7dddbcd63c480f80c2f16e0f
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045432"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>適用於 Microsoft Teams 或商務用 Skype® 2015 Online 的 Proxy 伺服器

本文提供搭配Teams或商務用 Skype使用 Proxy 伺服器的指導方針。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建議您不要使用 Proxy 伺服器

若要透過 proxy Teams或商務用 Skype流量，Microsoft 建議略過 Proxy。 Proxy 不會讓Teams或商務用 Skype更安全，因為流量已加密。
  
而擁有 Proxy 可能會造成問題。 效能相關問題可透過延遲和封包遺失而引入環境。 這類問題會導致在音訊和視訊等Teams或商務用 Skype案例中產生負的體驗，而即時串流是必要的。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果您需要使用 Proxy 伺服器

有些組織無法略過Teams或商務用 Skype流量的 Proxy。 如果是這種情況，您必須記住上述問題。
  
Microsoft 也強烈建議：
  
- 使用外部 DNS 解析度
    
- 使用直接 UDP 型路由
    
- 允許 UDP 流量
    
- 依照我們的網路指導方針中的其他建議進行：[準備貴組織的網路以供Teams](prepare-network.md)
  
    
遵循此指引應最小化潛在問題。
  
## <a name="related-topics"></a>相關主題

[Microsoft 365 和 Office 365 網路連線原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[針對 Teams 準備組織的網路](prepare-network.md)