---
title: Edge 設定展開工具
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
ROBOTS: NOINDEX, NOFOLLOW
description: 若要編輯現有單一或多部伺服器 Edge 集區的設定，您會看到下列各節：
ms.openlocfilehash: 89e23125182f5f413fbad8cbdc3e2a3651f878aa
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396917"
---
# <a name="edge-settings-expander"></a>Edge 設定展開工具

若要編輯現有單一或多部伺服器 Edge 集區的設定，您會看到下列各節：

- 一般設定

- 下一個躍點選取設定

- Edge Server 設定


## <a name="general-settings"></a>一般設定

Edge Server 集區的內部集區完整功能變數名稱 (FQDN) 。 編輯集區的 FQDN，以變更此設定。

若要設定與商務用 Skype Server 2015 Server 的同盟，請選取 [**啟用此 Edge 集區的同盟] 核取方塊 (埠 5061)** 。

指定內部配置複寫埠的埠號碼 **(HTTPS)**。

## <a name="next-hop-selection-settings"></a>下一個躍點選取設定

若要設定或修改 Edge server 將用來與內部基礎結構通訊的 **下一個躍點** 集區，請從下拉式清單方塊中選取 Director、director 集區、前端伺服器或前端伺服器集區。 只會顯示已在拓撲產生器中設定的 Director 或前端，以供選取。

## <a name="edge-server-configuration"></a>Edge Server 設定

若要編輯或指定 Edge server 的 **外部設定** 設定，您必須先決定是否要針對 SIP 存取、web 會議和 Audio/Video 服務使用個別的 IP 位址。

如果您想要讓每一項使用個別 IP 位址，請選取核取方塊 **[為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]**。 每個服務都必須有對應的 DNS 主機 (為它建立的) 記錄。

針對每個對外服務，您可以指定 FQDN 和關聯的埠。 例如， **SIP 存取** 將使用 sip.contoso.com 與關聯的埠5061。

> [!IMPORTANT]
> 如果您為每個對外的服務選取個別 FQDN，則每個服務必須有關聯的唯一連接埠值。 根據預設，SIP 位於埠5061/TLS 上，web 會議 edge service 位於埠444/TLS 上，而 A/V 會議伺服器位於埠443/TLS 上。 如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或埠，您必須更新其他所有依賴初始設定值的服務。

如果您決定讓組織的對外服務使用單一 FQDN 和 IP 位址，請清除 **[為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址]** 核取方塊。然後您就可以視需要編輯 **[SIP 存取]** 集區 FQDN 和連接埠值。

> [!IMPORTANT]
> 如果您變更其中任何設定，包括使用個別 FQDN 和 IP 位址或埠，您必須更新其他所有依賴初始設定值的服務。

## <a name="see-also"></a>另請參閱

如需定義及設定 Edge Service 設定的詳細資訊，請參閱 [定義您的 Edge 拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)。