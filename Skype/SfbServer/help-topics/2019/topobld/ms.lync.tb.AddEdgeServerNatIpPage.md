---
title: 新增 Edge 伺服器 NAT IP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: 公用 IP 位址是網路位址轉譯 (NAT) 所使用的 IP 位址。 IP 位址必須是公開路由的。 這是必要的, 因為您已選取此嚮導 [選取功能] 頁面上的 [此 Edge 池的外部 IP 位址是由 NAT 轉譯] 選項。
ms.openlocfilehash: ee70d335c4c8819b7c8b9661315646c98816bd9c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188302"
---
# <a name="add-edge-server-nat-ip"></a>新增 Edge 伺服器 NAT IP

公用 IP 位址是網路位址轉譯 (NAT) 所使用的 IP 位址。 IP 位址必須是公開路由的。 這是必要的, 因為您已選取此嚮導 [**選取功能**] 頁面上的 **[此 Edge 池的外部 IP 位址是由 NAT 轉譯**] 選項。

> [!NOTE]
> 網路位址轉譯 (NAT) 可讓私人網路 (例如192.168.0.0 範圍) 上的用戶端或伺服器能夠透過公用網際網路網路與遠端網路上的系統進行通訊。 NAT 的運作方式是使用外部介面上的單一公用 IP 位址, 並將內部 IP 位址與單一公用 IP 位址建立關聯。 NAT 對應會將內部位址對應至外部公用 IP 位址。 遠端系統只會看到來源的公用位址。 遠端系統會回應來源, 而來源參照 NAT 對應來判斷回應應該傳回哪一個內部 IP 位址。

您可以在部署初始拓撲時新增外部使用者存取的支援，也可以稍後再新增。如需新增 Edge Server 至現有拓撲的詳細資訊，請參閱 Edge Server 部署文件中的〈[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)〉。


