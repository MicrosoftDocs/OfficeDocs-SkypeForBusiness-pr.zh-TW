---
title: 新增 Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 若要將 Edge Server 或 Edge Server 集區納入拓撲設計，您必須為要部署 Edge Server 或 Edge Server 集區的伺服器指定完整網域名稱 (FQDN)。 在發佈包括 Edge 伺服器或 Edge 伺服器池以及安裝商務用 Skype Server 的拓撲之前，您應該已完成部署外部使用者存取的所有先決條件。 如需這些必要條件的詳細資訊，請參閱部署文件中的〈Preparing for Installation of Servers in the Perimeter Network〉。
ms.openlocfilehash: 3433f5dac67d0e02fb8e8552e205092a51082cc6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698338"
---
# <a name="add-edge-server"></a>新增 Edge Server

若要將 Edge Server 或 Edge Server 集區納入拓撲設計，您必須為要部署 Edge Server 或 Edge Server 集區的伺服器指定完整網域名稱 (FQDN)。 在發佈包括 Edge 伺服器或 Edge 伺服器池以及安裝商務用 Skype Server 的拓撲之前，您應該已完成部署外部使用者存取的所有先決條件。 如需這些必要條件的詳細資訊，請參閱部署文件中的〈[Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx)〉。

> [!IMPORTANT]
> 您指定的名稱必須與伺服器上設定的電腦名稱相同。根據預設，未加入網域之電腦的電腦名稱是簡稱，不是 FQDN。拓撲產生器會使用 FQDN，而非簡稱。您必須為即將部署為 Edge Server 或 Edge Server 集區 (但不加入網域) 的電腦，設定其名稱的網域名稱系統 (DNS) 尾碼。

> [!TIP]
> 如果您打算未來實作 Edge Server 集區，則選取 [多部電腦集區]****。 即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。 當您準備好要在池中新增更多電腦之後，您必須重新建立拓撲建立器，才能定義新的池成員、發佈新的拓撲，然後透過商務用 Skype Server 部署嚮導來設定新的 Edge 伺服器池成員。 您也必須新增集區成員至集區的適當負載平衡器、DNS 負載平衡或硬體負載平衡器。 內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。 您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。 請務必將新成員伺服器新增到適當的負載平衡器。

您可以在部署初始拓撲時，或部署初始拓撲之後，新增外部使用者存取的支援。如需新增 Edge Server 或 Edge Server 集區至現有拓撲的詳細資訊，請參閱 Edge Server 部署文件中的〈[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)〉。


