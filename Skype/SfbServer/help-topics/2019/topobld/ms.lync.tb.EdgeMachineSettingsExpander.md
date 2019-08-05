---
title: Edge 電腦設定擴展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: '若要編輯 Edge 伺服器池中伺服器的屬性, 請執行下列動作:'
ms.openlocfilehash: a6683766ddbfd11cd38d2d50b80a25c057b302bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188974"
---
# <a name="edge-machine-settings-expander"></a>Edge 電腦設定擴展器
 
若要編輯 Edge 伺服器池中伺服器的屬性, 請執行下列動作:
  
您可以透過編輯完全限定的功能變數名稱 (FQDN) 來變更**內部名稱或 FQDN** 。 FQDN 必須符合網域名稱系統 (DNS) 主機 (A) 記錄, 以及指派給內部 Edge 網路介面之伺服器之證書的消費者名稱。 **內部 IP 位址**的值定義指派為內部網路 (相對於周邊網路設計) 的網路介面的 IP 位址。
  
此對話方塊的後三節定義此 Edge 伺服器的外部設定的 IP 位址。 變更 IP 位址的能力受此設定在 Edge 伺服器池層級的屬性設定上**啟用不同的 FQDN 和 IP 位址與 A/V**的影響。
  
## <a name="sip-access"></a>SIP 存取

編輯指派給網路介面的外部 IP 位址, 以進行會話初始通訊協定 (SIP) 存取。 這個 IP 位址可以是公用 IP 位址或私人 IP 位址範圍中的位址。
  
> [!NOTE]
> 如果啟用 [在 [緩衝集區設定] 頁面上,**啟用網頁會議與 A/V 的個別 FQDN 和 IP 位址**, 則只有 SIP 存取的 ip 位址可供編輯。
  
## <a name="web-conferencing"></a>網路會議

編輯指派給網路會議網路介面的外部 IP 位址。 這個 IP 位址可以是公用 IP 位址或私人 IP 位址範圍中的位址。
  
## <a name="audiovideo"></a>音訊/視頻

編輯指派給音訊/視頻 (A/V) 網路介面的外部 IP 位址。 這個 IP 位址可以是公用 IP 位址或私人 IP 位址範圍中的位址。
  
**使用 NAT 啟用的公用 IP 位址**設定是外部介面 (一般是 A/V 網路介面或邊緣伺服器) 所使用的公用位址。 如果設定**啟用網路會議和 A/V 的個別 FQDN 和 IP 位址**, 則所有三個外部介面都會使用這個公用 IP 位址。
  

