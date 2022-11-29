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
description: 本文提供搭配 Microsoft Teams 或 商務用 Skype 使用 Proxy 伺服器的相關資訊。
ms.openlocfilehash: cdb4e6ccf05f597c87d066c18b1722eb08f89374
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176670"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>適用於 Microsoft Teams 或商務用 Skype® 2015 Online 的 Proxy 伺服器

本文提供搭配 Teams 或 商務用 Skype 使用 Proxy 伺服器的指導方針。
  
## <a name="not-using-a-proxy-server-is-recommended"></a>建議您不要使用 Proxy 伺服器

如果是 Teams 或透過 Proxy 商務用 Skype流量，Microsoft建議略過 Proxy。 Proxy 不會讓 Teams 或 商務用 Skype 更安全，因為流量已加密。
  
而擁有 Proxy 可能會造成問題。 透過延遲和封包遺失，您可以透過嘗試透過 Proxy 伺服器路由 Teams 流量，將效能相關問題引入環境。 這類問題會導致在音訊和視訊等 Teams 或商務用 Skype案例中產生負的體驗，而即時串流是必要的。

我們建議 Teams 流量略過 Proxy 伺服器基礎結構。

## <a name="teams-phones"></a>Teams 手機

Teams Phone 不支援 Proxy 伺服器。

我們建議確保訊號 (TCP 443) 和媒體 (UDP 3478-3481) 流量都略過 Proxy 伺服器基礎結構。

## <a name="teams-meeting-rooms-and-panels"></a>Teams 會議室和麵板

我們建議您確保您的 Teams 會議室略過 Proxy 基礎結構。

Windows 型 Teams 會議室支援 Proxy 伺服器，但不支援需要驗證的 Proxy 伺服器。 Android 型 Teams 會議室不支援 Proxy 伺服器。
  
## <a name="if-you-need-to-use-a-proxy-server"></a>如果您需要使用 Proxy 伺服器

有些組織沒有略過 Teams Proxy 或商務用 Skype流量的選項。 如果是這種情況，您必須記住上述問題。
  
Microsoft也強烈建議：
  
- 使用本機、外部 DNS 解析度 (某些雲端式 Proxy 解決方案可能會導致 DNS 解析度出現在另一個位置) 。
    
- 使用以 UDP 為基礎的直接路由，而非依賴媒體的 TCP 路由
    
- 允許 UDP 流量 (3478-3481) 

- 允許所有必要的 URL 和 IP，包括 Azure、Office 365、Intune 和 Teams Room Pro (使用) 
    
- 依照我們的網路指導方針中的其他建議進行： [為貴組織的 Teams 網路做好準備](prepare-network.md)
  
    
遵循此指引應最小化潛在問題。
  
## <a name="related-topics"></a>相關主題

[Microsoft 365 和 Office 365 網路連線原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[針對 Teams 準備組織的網路](prepare-network.md)
