---
title: 新增 Edge Server NAT IP
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: 公用 IP 位址是網路位址轉譯 (NAT) 所使用的 IP 位址。 IP 位址必須可公開路由傳送。 這是必要的，因為您已在此嚮導的 [選取功能] 頁面上，選取 [此 Edge 集區的外部 IP 位址是由 NAT 轉譯] 選項。
ms.openlocfilehash: 20fc7b116fe5d0b57b7f818f89a6a473e58a6a4a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633897"
---
# <a name="add-edge-server-nat-ip"></a>新增 Edge Server NAT IP

公用 IP 位址是網路位址轉譯 (NAT) 所使用的 IP 位址。 IP 位址必須可公開路由傳送。 這是必要的，因為您已在此嚮導的 [**選取功能**] 頁面上，選取 [**此 Edge 集區的外部 IP 位址是由 NAT 轉譯**] 選項。

> [!NOTE]
> 網路位址轉譯 (NAT) 會在私人網路 (上啟用用戶端或伺服器。例如，192.168.0.0 範圍) ，可與透過公用網際網路網路的遠端網路上的系統進行通訊。 NAT 的運作方式是使用外部介面上的單一公用 IP 位址，並將內部 IP 位址與一個公用 IP 位址產生關聯。 NAT 對應會將內部位址對應至外部公用 IP 位址。 遠端系統只會看到來源的公用位址。 遠端系統會回應來源，而且來源會參照 NAT 對應，以決定回應應傳回的內部 IP 位址。

您可以在部署初始拓撲時新增外部使用者存取的支援，也可以稍後再新增。如需新增 Edge Server 至現有拓撲的詳細資訊，請參閱 Edge Server 部署文件中的＜[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)＞。