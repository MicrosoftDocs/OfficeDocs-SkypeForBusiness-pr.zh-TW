---
title: Lync Server 2010 的 Edge 伺服器 FQDN 設定擴展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: '若要在 [外部設定] 底下定義屬性, 請設定下列專案:'
ms.openlocfilehash: 6b833e89a8e1288af9a203dd5f44201c253ff2f9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189550"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Lync Server 2010 的 Edge 伺服器 FQDN 設定擴展器
 
若要在 [**外部設定**] 底下定義屬性, 請設定下列專案:
  
如果您想要為 web 會議和音訊/視頻定義不同的池 FQDN 和 IP 位址, 請選取 [**針對 web 會議與 A/V 啟用個別的 FQDN 和 ip 位址**] 核取方塊。
  
> [!NOTE]
> 如果您選擇不選取個別 FQDN 和 IP 位址的核取方塊, 您必須針對 Edge 伺服器所提供的三種服務分別提供不同的埠。 唯一要設定的完整功能變數名稱是與存取邊緣服務相關聯的 FQDN。 
  
如果您希望 A/V 邊緣服務使用網路位址轉譯 (NAT) IP 位址和設定, 請選取 [ **a/v edge 服務已啟用 NAT** ] 核取方塊。
  
針對已啟用的邊緣服務, 您可以在 [**埠**] 底下輸入 [**池 FQDN** ] 和 [埠]
  
- 定義**存取邊緣服務**池 FQDN, 以及唯一識別該服務的埠。
    
- 定義**網路會議 Edge 服務**池 FQDN (如果未選取 [web 會議] 和 [a/V] 的不同 FQDN 和 IP 位址) 以及唯一識別該服務的埠。
    
- 定義**A/V Edge 服務**池 FQDN (如果未選取 [web 會議] 和 [a/v] 的不同 FQDN 和 IP 位址) 以及唯一識別該服務的埠。
    
  **確定**：接受並認可對話方塊的變更。
  
  **取消**：捨棄變更，並關閉對話方塊。
  
  **說明**：顯示此說明畫面。
  

