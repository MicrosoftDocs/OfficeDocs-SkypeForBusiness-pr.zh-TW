---
title: 主幹設定展開工具
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 若要編輯或修改 SIP 主幹的設定，請執行下列動作：
ms.openlocfilehash: ea10af8363cd2298f00d06b09c40f6df97014e48
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774983"
---
# <a name="trunk-settings-expander"></a>主幹設定展開工具

若要編輯或修改 SIP 主幹的設定，請執行下列動作：

 [主幹名稱] 是唯一識別部署中 SIP 主幹的必要項目。

 **關聯的 PSTN 閘道**：選取部署中已定義的現有 PSTN 閘道。

 **IP/PSTN 閘道的聆聽連接埠**：指出閘道將在哪個 TCP/IP 連接埠聆聽要求。所需的值可能依閘道的廠商而異，但預設值是連接埠 5067。

 **SIP 傳輸通訊協定**：使用通訊協定 TCP 或 TLS。TLS 是預設值。請參閱閘道廠商文件，以了解您的閘道支援的值。預設值是 TLS，如果閘道支援 TLS 的話，應考慮使用此值作為較安全的選項。

 **關聯** 的轉送伺服器：從部署選取現有的轉送伺服器，以與 SIP 主幹產生關聯。

> [!NOTE]
> 只有根主幹可以與 Lync Server 2010 或 Lync Server 2013 轉送伺服器相關聯。

 **關聯的轉送伺服器埠**：必要值，此值會設定為轉送伺服器設定為接聽的值。

![主幹設定展開器。](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>另請參閱

[SIP 主幹部署檢查表](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[SIP 主幹的元件和拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)