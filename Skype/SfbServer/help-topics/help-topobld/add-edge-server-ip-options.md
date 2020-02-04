---
title: 新增 Edge Server IP 選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013 可讓您針對 Edge 伺服器和 Edge 池的每個介面設定 IPv4 與 IPv6 位址。 若要這樣做，請執行下列動作：
ms.openlocfilehash: f6721f170bbe9a05a247d5ab79fb2cbd1cb7ccaf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698408"
---
# <a name="add-edge-server-ip-options"></a>新增 Edge Server IP 選項
 
Microsoft Lync Server 2013 可讓您針對 Edge 伺服器和 Edge 池的每個介面設定 IPv4 與 IPv6 位址。 若要這樣做，請執行下列動作：
  
- **在內部介面上啟用 ipv4**：如果您想要將 ipv4 位址套用至 edge 伺服器或 edge 池內部介面，請選取此核取方塊。
    
- **在內部介面上啟用 ipv6**：如果您想要將 ipv6 位址套用至 edge 伺服器或 edge 池內部介面，請選取此核取方塊。
    
- **在外部介面上啟用 ipv4**：如果您想要將 ipv4 位址套用至 edge 伺服器或 edge 池外部介面，請選取此核取方塊。
    
- **在外部介面上啟用 ipv6**：如果您想要將 ipv6 位址套用至 edge 伺服器或 edge 池外部介面，請選取核取方塊。
    
您也可以將 Edge 伺服器或 Edge 池設定為使用網路位址轉譯位址作為外部 IP 位址。 您可以選取**此邊緣池的外部 IP 位址（由 NAT 轉譯**）來執行此動作。
  
NAT 支援。 如果您使用的是硬體負載平衡，就不支援網路位址轉譯（NAT），所以如果您要部署含硬體負載平衡的 Edge 伺服器池，請不要選取 NAT 選項。
  

