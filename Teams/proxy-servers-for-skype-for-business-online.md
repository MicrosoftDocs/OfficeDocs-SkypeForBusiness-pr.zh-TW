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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: 本文提供有關在 Microsoft Teams 或商務用 Skype 中使用 Proxy 伺服器的資訊。
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117721"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>適用於 Microsoft Teams 或商務用 Skype® 2015 Online 的 Proxy 伺服器

本文提供使用 Proxy 伺服器與 Teams 或商務用 Skype 的指南。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建議您不要使用 Proxy 伺服器

當涉及 Teams 或商務用 Skype 流量超過代理時，Microsoft 建議忽略代理。 由於流量已加密，因此代理不會讓 Teams 或商務用 Skype 更安全。
  
而擁有 Proxy 可能會導致問題。 透過延遲和封包遺失，可能會將與績效相關的問題引入環境。 這類問題會導致 Teams 或商務用 Skype 案例的負面體驗，例如音訊和視像，即時資料流不可或缺。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果您需要使用 Proxy 伺服器

有些組織無法選擇忽略 Teams 或商務用 Skype 流量的 Proxy。 如果是這種情況，您必須記住上述問題。
  
Microsoft 也強烈建議您：
  
- 使用外部 DNS 解析
    
- 使用直接 UDP 路由
    
- 允許 UDP 流量
    
- 遵循我們的網路指導方針中的其他建議：準備貴組織的 [Teams 網路](prepare-network.md)
  
    
遵循此指南應能將潛在問題降到最低。
  
## <a name="related-topics"></a>相關主題

[Microsoft 365 和 Office 365 網路連接原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[針對 Teams 準備組織的網路](prepare-network.md)