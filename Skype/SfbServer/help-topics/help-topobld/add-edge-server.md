---
title: 新增 Edge Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: 若要將 Edge Server 或 Edge Server 集區併入拓撲設計，您必須指定要部署 Edge Server 或 Edge Server 集區之伺服器的完整功能變數名稱 (FQDN) 。 在發佈包含 Edge server 或 edge server 集區的拓撲，並安裝商務用 Skype Server 之前，您必須完成部署外部使用者存取的所有必要條件。 如需這些必要條件的詳細資訊，請參閱部署檔中的在周邊網路中安裝伺服器的準備。
ms.openlocfilehash: 6f905b24a0ca0da499cf94acda57404fabe289bc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592659"
---
# <a name="add-edge-server"></a>新增 Edge Server

若要將 Edge Server 或 Edge Server 集區併入拓撲設計，您必須指定要部署 Edge Server 或 Edge Server 集區之伺服器的完整功能變數名稱 (FQDN) 。 在發佈包含 Edge server 或 edge server 集區的拓撲，並安裝商務用 Skype Server 之前，您必須完成部署外部使用者存取的所有必要條件。 如需這些必要條件的詳細資訊，請參閱部署檔中的在 [周邊網路中安裝伺服器的準備](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network) 。

> [!IMPORTANT]
> 您指定的名稱必須與伺服器上設定的電腦名稱一模一樣。 根據預設，未加入網域的電腦，其電腦名稱是簡短名稱，而不是 FQDN。 拓撲產生器使用 Fqdn，而非短名稱。 您必須在要部署為 Edge Server 或 Edge Server 集區的網域名稱系統 (DNS) 尾碼（未加入網域的電腦）設定網域名稱系統。

> [!TIP]
> 如果您想要在未來實施 Edge Server 集區，請選取 [ **多部電腦集** 區]。 即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。 當您準備好將更多電腦新增至集區之後，您必須重新建立拓撲產生器以定義新的集區成員、發佈新的拓撲，然後透過「商務用 Skype Server 部署」嚮導設定新的 Edge Server 集區成員。 您也必須新增集區成員至集區的適當負載平衡器、DNS 負載平衡或硬體負載平衡器。 內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。 您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。 確定您要將新的成員伺服器加入適當的負載平衡器。

您可以在部署初始拓撲時，或在部署初始拓撲之後，新增對外部使用者存取的支援。 如需將 Edge Servers 或 Edge Server 集區新增至現有拓撲的詳細資訊，請參閱 Edge Server 部署檔中的 [定義 Edge 拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) 。