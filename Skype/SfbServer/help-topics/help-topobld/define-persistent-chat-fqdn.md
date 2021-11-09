---
title: 定義常設聊天室 FQDN
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 您可以使用 [定義新的持久聊天集區] 嚮導來建立新的 Persistent Chat Server 或 Persistent Chat Server 集區。 選取 [多部電腦集區] 或 [單一電腦集區]。 如果您選取單一電腦集區，後來需要多部電腦集區，則必須移除單一電腦集區，然後再定義多部電腦集區。
ms.openlocfilehash: 44d8fd7647068c98855a2d06f64a2d8f519f2da5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851317"
---
# <a name="define-persistent-chat-fqdn"></a>定義常設聊天室 FQDN
 
您可以使用 [ **定義新的持久聊天集** 區] 嚮導來建立新的 Persistent chat Server 或 Persistent chat server 集區。 選取 [ **多部電腦集** 區] 或 [ **單一電腦集** 區]。 如果您選取單一電腦集區，後來需要多部電腦集區，則必須移除單一電腦集區，然後再定義多部電腦集區。
  
您也必須定義 Persistent Chat Server 或 Persistent Chat Server 集區的 **集區 FQDN** 。 單一電腦集區的集區完整功能變數名稱 (FQDN) 必須與組成單一伺服器集區之電腦的 FQDN 相同。 如果是多部電腦集區，FQDN 必須是您選擇用來代表此多部電腦集區的名稱，而且會由主機 A (和 AAAA （如果 IPv6) record）加以定義。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃 Persistent Chat Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
