---
title: Edge Server FQDN 設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 若要定義 [外部設定] 底下的屬性，請進行下列設定：
ms.openlocfilehash: 763fed345ec3d53496be216dbd94e26825c2766b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828916"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Edge Server FQDN 設定展開工具 (適用於 Lync Server 2010)
 
若要定義 [ **外部設定**] 底下的屬性，請進行下列設定：
  
如果您想為 web 會議及音訊/視頻定義不同的集區 FQDN 和 IP 位址，請選取 [ **為 web 會議和 A/V 啟用個別 FQDN 和 ip 位址** ] 核取方塊。
  
> [!NOTE]
> 如果您選擇不選取個別 FQDN 和 IP 位址的核取方塊，則必須為 Edge Server 所提供的三種服務提供不同的埠。 要設定的唯一完整功能變數名稱是與 Access Edge service 相關聯的 FQDN。 
  
如果您希望 A/V Edge service 使用網路位址轉譯 (NAT) IP 位址和設定，請選取 [ **A/V Edge service 為已啟用 NAT** ] 核取方塊。
  
在 [已啟用的 Edge service] 中，在 [**埠**] 底下輸入 **集區 FQDN** 和埠
  
- 定義 **Access Edge service** 集區 FQDN 及可唯一識別服務的埠。
    
- 若未選取 [為 web 會議和 A/V 啟用個別 FQDN 和 IP 位址]，請定義 **Web 會議 Edge service** 集區 FQDN () 和唯一識別服務的埠。
    
- 若未選取 [為 web 會議和 A/V 啟用個別 FQDN 和 IP 位址]) 及可唯一識別服務的埠，請定義 **A/V Edge service** 集區 FQDN (。
    
  **確定**：接受並認可對話方塊的變更。
  
  **取消**：捨棄變更，並關閉對話方塊。
  
  **說明**：顯示此說明畫面。
  

