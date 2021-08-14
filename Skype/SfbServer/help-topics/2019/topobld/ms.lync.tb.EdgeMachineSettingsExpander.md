---
title: Edge 電腦設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
ROBOTS: NOINDEX, NOFOLLOW
description: 若要編輯 Edge Server 集區中某個伺服器的內容，請執行下列動作：
ms.openlocfilehash: 17412ba6e4ef2a90d2227566a8e9762a0baaeda81b8c6834e00b910bb40323f3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328468"
---
# <a name="edge-machine-settings-expander"></a>Edge 電腦設定展開工具
 
若要編輯 Edge Server 集區中某個伺服器的內容，請執行下列動作：
  
您可以編輯完整網域名稱 (FQDN) 來變更 [內部名稱或 FQDN]。FQDN 必須符合網域名稱系統 (DNS) 主機 (A) 記錄以及憑證 (指派給內部 Edge 網路介面的伺服器) 的主體名稱。[內部 IP 位址] 的值定義 IP 位址，此位址被指派已定義為內部網路的網路介面 (相對於周邊網路設計)。
  
對話方塊接下來三個區段定義此 Edge Server 的外部組態的 IP 位址。是否有能力變更 IP 位址，取決於 Edge Server 集區層級的 [內容] 設定上的 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址] 設定。
  
## <a name="sip-access"></a>SIP 存取

編輯外部 IP 位址，以指派給工作階段初始通訊協定 (SIP) 存取的網路介面。此 IP 位址可以是公用 IP 位址或是私人 IP 位址範圍中的位址。
  
> [!NOTE]
> 如果集區設定頁面上的 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址] 設定已啟用，則只能編輯 SIP 存取的 IP 位址。
  
## <a name="web-conferencing"></a>Web 會議

編輯外部 IP 位址，以指派給 Web 會議的網路介面。此 IP 位址可以是公用 IP 位址或是私人 IP 位址範圍中的位址。
  
## <a name="audiovideo"></a>Audio/Video

編輯外部 IP 位址，以指派給音訊/視訊 (A/V) 的網路介面。此 IP 位址可以是公用 IP 位址或是私人 IP 位址範圍中的位址。
  
[已使用啟用 NAT 的公用 IP 位址] 的設定，通常是由 A/V 網路介面或 Edge Server 的外部介面所使用的公用位址。如果 [為 Web 會議和 A/V 啟用個別 FQDN 和 IP 位址] 已啟用，則三個外部介面全部都會使用此公用 IP 位址。
  

