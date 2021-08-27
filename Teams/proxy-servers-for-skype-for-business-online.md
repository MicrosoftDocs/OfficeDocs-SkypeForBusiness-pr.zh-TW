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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: 本文提供有關將 Proxy 伺服器與 Microsoft Teams 或 商務用 Skype。
ms.openlocfilehash: 559a42c19aa47a9e72a5c0549e80f45de8d50fdf
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582157"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>適用於 Microsoft Teams 或商務用 Skype® 2015 Online 的 Proxy 伺服器

本文提供有關將 Proxy 伺服器與 Teams 或 商務用 Skype。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建議您不要使用 Proxy 伺服器

當涉及代理Teams或商務用 Skype流量時，Microsoft 建議忽略代理。 由於流量已加密，因此Teams或商務用 Skype更安全。
  
而擁有 Proxy 也可能會造成問題。 與績效相關的問題可能會透過延遲和封包遺失而引入環境。 這類問題會導致音訊和視Teams或商務用 Skype情境中的負面體驗，而即時資料流是不可或缺的。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果您需要使用 Proxy 伺服器

有些組織無法針對流量或流量Teams商務用 Skype Proxy。 如果是這種情況，您必須記住上述問題。
  
Microsoft 也強烈建議您：
  
- 使用外部 DNS 解析
    
- 使用直接 UDP 路由
    
- 允許 UDP 流量
    
- 遵循我們的網路指導方針中的其他建議：準備貴組織的網路[Teams](prepare-network.md)
  
    
遵循此指引應能將潛在問題降到最低。
  
## <a name="related-topics"></a>相關主題

[Microsoft 365 和 Office 365 網路連線原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[針對 Teams 準備組織的網路](prepare-network.md)