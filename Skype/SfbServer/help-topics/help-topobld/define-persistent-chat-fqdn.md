---
title: 定義常設聊天室 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 您可以使用 [定義新的持久性聊天池] 嚮導來建立新的持久聊天伺服器或持久聊天伺服器池。 請選取 [多部電腦集區] 或 [單一電腦集區]。 如果選取 [單一電腦集區] 並在稍後需要多部電腦集區，則必須移除單一電腦集區，再定義多部電腦集區。
ms.openlocfilehash: 12b5a648de211086d33624afad56ce069493b135
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820195"
---
# <a name="define-persistent-chat-fqdn"></a>定義常設聊天室 FQDN
 
您可以使用 [**定義新的持久性聊天池**] 嚮導來建立新的持久聊天伺服器或持久聊天伺服器池。 請選取 [多部電腦集區]**** 或 [單一電腦集區]****。 如果選取 [單一電腦集區] 並在稍後需要多部電腦集區，則必須移除單一電腦集區，再定義多部電腦集區。
  
您也必須為持續聊天伺服器或持久聊天伺服器池定義一個**池 FQDN** 。 單一電腦集區的集區完整網域名稱 (FQDN) 必須與構成單一伺服器集區之電腦的 FQDN 相同。 若是多部電腦集區，FQDN 必須是您選擇代表此多部電腦集區的名稱，並由主機 A (如果使用 IPv6，則為 AAAA) 記錄在 DNS 中定義。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃常設聊天室伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[在商務用 Skype Server 2015 拓撲中新增持久聊天伺服器](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
