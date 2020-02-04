---
title: Edge Server FQDN 設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: 若要編輯或指定 Edge Server 的 [外部設定]，您必須先決定工作階段初始通訊協定 (SIP) 存取、Web Conferencing Edge Service 和 Audio/Video Edge Service 是否使用個別 IP 位址。
ms.openlocfilehash: 2559c1487077465e656ecdfd00ad74002c87a832
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697400"
---
# <a name="edge-server-fqdns-settings-expander"></a>Edge Server FQDN 設定展開工具

若要編輯或指定 Edge Server 的 [外部設定]****，您必須先決定工作階段初始通訊協定 (SIP) 存取、Web Conferencing Edge Service 和 Audio/Video Edge Service 是否使用個別 IP 位址。

如果您想要讓每一項使用個別 IP 位址，請選取核取方塊 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]****。每個服務必須已建立對應的網域名稱系統 (DNS) 主機 (A) 記錄。

對於每個對外的服務，請指定完整網域名稱 (FQDN) 和關聯的連接埠。例如，在 [SIP 存取]**** 中，您可能使用 sip.contoso.com 和關聯的連接埠 5061。

> [!IMPORTANT]
> 如果您為每個對外的服務選取個別 FQDN，則每個服務必須有關聯的唯一連接埠值。根據預設，SIP 位於連接埠 5061/TLS、Web Conferencing Edge Service 位於連接埠 444/TLS，A/V Conferencing Edge Service 位於連接埠 443/TLS。如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或連接埠，您必須更新其他所有依賴初始設定值的服務。

如果您決定讓組織的對外服務使用單一 FQDN 和 IP 位址，請清除 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]**** 核取方塊。接著就可以根據需要，編輯 [SIP 存取]**** 集區 FQDN 和連接埠值。

> [!IMPORTANT]
> 如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或連接埠，您必須更新其他所有依賴初始設定值的服務。

如需定義和設定 Edge Service 設定的詳細資訊，請參閱〈[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)〉。


