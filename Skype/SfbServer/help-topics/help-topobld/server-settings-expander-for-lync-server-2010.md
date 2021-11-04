---
title: 伺服器設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 若要編輯這部電腦的屬性，請執行下列動作：
ms.openlocfilehash: 599f041a1428ae1b418141ef7ce8779c7eba06fa
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765671"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>伺服器設定展開工具 (適用於 Lync Server 2010)
 
若要編輯這部電腦的屬性，請執行下列動作：
  
- 編輯此電腦 **(FQDN) 的完整功能變數名稱** 。 此專案必須符合在網域名稱系統 (DNS) 中定義的電腦名稱稱，以及與此電腦相關聯的主體替代名稱 (SAN) 或主體名稱 (SN) 。
    
- 您可以選取下列其中一項：
    
    **使用所有設定的 ip 位址**：選取此專案即可使用電腦上所有已設定的 ip 位址。
    
    > [!IMPORTANT]
    > 如果電腦有多個 IP 位址，您必須注意，與此電腦相關聯的服務將使用所有服務的所有 IP 位址。 如果聆聽伺服器或服務要求通訊特定的 IP 位址與通訊埠，則服務可能無法對要接聽的 IP 位址進行最佳選擇。 
  
    **將服務使用方式限制為選取的 IP 位址**：如果您想要針對來自部署中其他電腦及集區的通訊，定義此電腦要接聽的 **主要 ip 位址** 的特定 ip 位址，請選取此選項。 針對電腦及服務要接聽通訊的特定 IP 位址，定義 **PSTN IP 位址** ，並將通訊傳送至已定義的 PSTN 閘道或 IP-PBX。
    

