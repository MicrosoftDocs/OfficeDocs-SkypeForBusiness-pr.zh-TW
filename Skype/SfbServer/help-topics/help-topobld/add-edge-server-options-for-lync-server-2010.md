---
title: 新增 Edge Server 選項 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 您會定義新的 Edge Server 或 Edge 集區，並會呈現機會，以定義新伺服器或集區的功能。 您可以選擇的選項包括：
ms.openlocfilehash: 273b2543fc3eea1373817ab38eab39379ec59132
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216594"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>新增 Edge Server 選項 (適用於 Lync Server 2010)

您會定義新的 Edge Server 或 Edge 集區，並會呈現機會，以定義新伺服器或集區的功能。 您可以選擇的選項包括：

- **使用單一 FQDN 和 IP 位址**：選取此核取方塊可針對外部 Edge 介面，使用單一 IPv4 或 IPv6 (如果選擇同時使用 IPv4 和 IPv6，則必須定義其中一種 IP 位址類型) 位址及完整網域名稱 (FQDN)。

    > [!IMPORTANT]
    > 如果選擇這個選項，只會使用一個 IP 位址，或 IPv4 和 IPv6 各一個，但是必須為每個 Edge 介面指派不同的連接埠號碼。

- **啟用同盟 (連接埠 5061)**：如果您想與使用工作階段初始通訊協定 (SIP) 的其他 SIP 同盟、提供者或託管服務進行同盟，請選取此核取方塊。

- **此 Edge 集區的外部 IP 位址由 NAT 轉譯**：如果您對 Edge 外部介面使用私人 ip 位址，並提供網路位址轉譯 (NAT) 裝置，以在邏輯上放置 edge Server 或 edge 集區，則選取此核取方塊。

## <a name="see-also"></a>請參閱

[規劃外部使用者存取](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[部署外部使用者存取](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
