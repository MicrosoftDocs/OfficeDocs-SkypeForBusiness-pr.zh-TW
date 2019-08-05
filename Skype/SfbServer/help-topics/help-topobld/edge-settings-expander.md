---
title: Edge 設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 若要編輯一或多個現有服器 Edge 集區的設定，請參考下列區段：
ms.openlocfilehash: 307a861814a8e05065c70299b5ef2a82c20c8c42
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189529"
---
# <a name="edge-settings-expander"></a>Edge 設定展開工具

若要編輯一或多個現有服器 Edge 集區的設定，請參考下列區段：

- 一般設定

- 下一個躍點選取範圍設定

- Edge Server 組態



## <a name="general-settings"></a>一般設定

Edge Server 集區的內部集區完整網域名稱 (FQDN)。編輯集區的 FQDN 以變更此設定。

如果您要將同盟設定為使用 Lync Server 2013、Microsoft Lync Server 2010 或 Microsoft Office 通訊伺服器 2007 R2 信任合作夥伴, 請選取 [**針對此 Edge 池啟用同盟 (埠 5061)** ] 核取方塊。

選取 [啟用此 Edge 集區的 XMPP 同盟]****，啟用 XMPP 同盟。

指定 [內部組態複寫連接埠 (HTTPS)]**** 的連接埠號碼。

## <a name="next-hop-selection-settings"></a>下一個躍點選取範圍設定

若要設定或修改 Edge Server 用來與內部基礎結構進行通訊的 [下一個躍點集區]****，請從下拉式清單方塊中，選取 Director、Director 集區、前端伺服器或前端伺服器集區。 只有已在拓撲結構建立器中設定的控制器或端點會顯示選取範圍。

## <a name="edge-server-configuration"></a>Edge Server 組態

若要為 Edge Server 編輯或指定 [外部設定]**** 的相關設定，必須先判定是否要針對 SIP 存取、Web 會議與音訊/視訊服務使用個別的 IP 位址。

如果您想要讓每一項使用個別 IP 位址，請選取 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]****。每一項服務必須具有專為其建立的對應 DNS 主機 (A) 記錄。

您必須針對每一個對外服務指定 FQDN 以及相關聯的連接埠。例如，[SIP 存取]**** 會使用 sip.contoso.com 以及相關聯的連接埠 5061。

> [!IMPORTANT]
> 如果您為每個對外的服務選取個別 FQDN，則每個服務必須有相關聯的唯一連接埠值。根據預設，SIP 位於連接埠 5061/TLS，Web Conferencing Edge Service 則位於連接埠 444/TLS，而 A/V 會議伺服器則位於連接埠 443/TLS。如果您變更以上任何設定，包括使用個別 FQDN 和 IP 位址或連接埠，即必須更新依賴初始設定值的所有其他服務。

如果您決定讓組織的對外服務使用單一 FQDN 和 IP 位址，請清除 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]**** 核取方塊。接著就可以根據需要，編輯 [SIP 存取]**** 集區 FQDN 和連接埠值。

> [!IMPORTANT]
> 如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或連接埠，您必須更新其他所有依賴初始設定值的服務。

## <a name="see-also"></a>另請參閱

如需詳細瞭解定義和設定 Edge Service 的設定，請參閱〈[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)〉。


