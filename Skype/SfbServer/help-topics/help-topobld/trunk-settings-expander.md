---
title: 主幹設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 若要編輯或修改 SIP 主幹的設定，請執行下列動作：
ms.openlocfilehash: 119bd77b55ef616d3441c3432f238aa274de4e71
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696548"
---
# <a name="trunk-settings-expander"></a>主幹設定展開工具

若要編輯或修改 SIP 主幹的設定，請執行下列動作：

 [主幹名稱]**** 是唯一識別部署中 SIP 主幹的必要項目。

 **關聯的 PSTN 閘道**：選取部署中已定義的現有 PSTN 閘道。

 **IP/PSTN 閘道的聆聽連接埠**：指出閘道將在哪個 TCP/IP 連接埠聆聽要求。所需的值可能依閘道的廠商而異，但預設值是連接埠 5067。

 **SIP 傳輸通訊協定**：使用通訊協定 TCP 或 TLS。TLS 是預設值。請參閱閘道廠商文件，以了解您的閘道支援的值。預設值是 TLS，如果閘道支援 TLS 的話，應考慮使用此值作為較安全的選項。

 **關聯的中繼伺服器**：從部署選取現有的中繼伺服器，以與 SIP 幹線建立關聯。

> [!NOTE]
> 只有根幹線可以與 Lync Server 2010 或 Lync Server 2013 轉送伺服器進行關聯。

 **關聯的中繼伺服器埠**： [必要] 值，會設定為轉送伺服器設定為要偵聽的值。

![主幹設定展開工具](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>另請參閱

[SIP 中繼部署檢查清單](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[SIP 中繼的元件與拓撲](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
