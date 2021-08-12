---
title: 新增 Edge Server IP 選項
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013 可讓您為 Edge Server 和 Edge 集區的每個介面設定 IPv4 和 IPv6 位址。 若要這樣做，請執行下列動作：
ms.openlocfilehash: 713c5030b0ca39555c57bb5ae0d36f873701c54181b46cb845d75012b3a81b65
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284863"
---
# <a name="add-edge-server-ip-options"></a>新增 Edge Server IP 選項
 
Microsoft Lync Server 2013 可讓您為 Edge Server 和 Edge 集區的每個介面設定 IPv4 和 IPv6 位址。 若要這樣做，請執行下列動作：
  
- **在內部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。
    
- **在內部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區內部介面，請選取此核取方塊。
    
- **在外部介面上啟用 IPv4**：若要將 IPv4 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。
    
- **在外部介面上啟用 IPv6**：若要將 IPv6 位址套用至 edge Server 或 edge 集區外部介面，請選取此核取方塊。
    
您也可以將 Edge Server 或 Edge 集區設定為使用網路位址轉譯位址的外部 IP 位址。 您可以藉由選取 [此 Edge 集區的外部 IP 位址由 NAT 轉譯] 核取方塊，來執行此動作。
  
NAT 支援。 當您使用硬體負載平衡時，不支援 [網路位址轉譯 (NAT) ]，所以如果您要部署具有硬體負載平衡的 Edge Server 集區，請勿選取 NAT 選項。
  

