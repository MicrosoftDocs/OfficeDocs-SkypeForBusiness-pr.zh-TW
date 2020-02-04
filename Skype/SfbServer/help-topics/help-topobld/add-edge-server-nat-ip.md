---
title: 新增 Edge Server NAT IP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: 公用 IP 位址是網路位址轉譯（NAT）所使用的 IP 位址。 IP 位址必須是公開路由的。 這是必要的，因為您已選取此嚮導 [選取功能] 頁面上的 [此 Edge 池的外部 IP 位址是由 NAT 轉譯] 選項。
ms.openlocfilehash: f2e5a00b4e7c91f2343b9c917f6249d2ecee8930
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698398"
---
# <a name="add-edge-server-nat-ip"></a>新增 Edge Server NAT IP

公用 IP 位址是網路位址轉譯（NAT）所使用的 IP 位址。 IP 位址必須是公開路由的。 這是必要的，因為您已選取此嚮導 [**選取功能**] 頁面上的 **[此 Edge 池的外部 IP 位址是由 NAT 轉譯**] 選項。

> [!NOTE]
> 網路位址轉譯（NAT）可讓私人網路（例如192.168.0.0 範圍）上的用戶端或伺服器能夠透過公用網際網路網路與遠端網路上的系統進行通訊。 NAT 的運作方式是使用外部介面上的單一公用 IP 位址，並將內部 IP 位址與單一公用 IP 位址建立關聯。 NAT 對應會將內部位址對應至外部公用 IP 位址。 遠端系統只會看到來源的公用位址。 遠端系統會回應來源，而來源參照 NAT 對應來判斷回應應該傳回哪一個內部 IP 位址。

您可以在部署初始拓撲時新增外部使用者存取的支援，也可以稍後再新增。如需新增 Edge Server 至現有拓撲的詳細資訊，請參閱 Edge Server 部署文件中的〈[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)〉。


