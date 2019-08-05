---
title: 新增 Lync Server 2010 的邊緣伺服器選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: '您可以定義新的邊緣伺服器或 Edge 池, 並供應商機來定義新伺服器或池中的功能。 您可以選擇的選項包括:'
ms.openlocfilehash: 4bb364ee24f2e85ec16ff2f972dfe05aea9306cd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191662"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>新增 Lync Server 2010 的邊緣伺服器選項

您可以定義新的邊緣伺服器或 Edge 池, 並供應商機來定義新伺服器或池中的功能。 您可以選擇的選項包括:

- **使用單一 FQDN 和 IP 位址**: 選取核取方塊以使用單一 Ipv4 或 ipv6 (如果您選擇同時使用 Ipv4 和 ipv6), 則必須為外部邊緣介面定義其中一個 IP 位址類型的位址和完整功能變數名稱 (FQDN)。

    > [!IMPORTANT]
    > 如果您選擇此選項, 您將只使用一個 IP 位址或一個 IPv4 與一個 IPv6, 但是您必須為每個 Edge 介面指派不同的埠號碼。

- **啟用同盟 (埠 5061)**: 如果您要與其他 SIP 聯合體、提供者或使用會話初始通訊協定 (SIP) 的託管產品進行聯盟, 請選取此核取方塊。

- **此 edge 池的外部 ip 位址是由 NAT 來轉譯**: 如果您針對 edge 外部介面使用私人 IP 位址, 並提供網路位址轉譯 (NAT) 裝置以邏輯方式放置邊緣伺服器或邊緣池, 請選取此核取方塊。促使.

## <a name="see-also"></a>另請參閱

[規劃外部使用者存取](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[部署外部使用者存取](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
