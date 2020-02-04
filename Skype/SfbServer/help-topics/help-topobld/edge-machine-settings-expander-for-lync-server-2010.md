---
title: Edge 電腦設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 若要將 Edge 伺服器電腦的屬性編輯為單一邊緣伺服器或邊緣池中的成員電腦，請設定伺服器名稱和 IP 位址設定設定：
ms.openlocfilehash: 411e870a874366754d17d0601ed1f216ce18899a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684776"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Edge 電腦設定展開工具 (適用於 Lync Server 2010)
 
若要將 Edge 伺服器電腦的屬性編輯為單一邊緣伺服器或邊緣池中的成員電腦，請設定**伺服器名稱和 IP 位址**設定設定：
  
- **內部名稱或 FQDN**：請輸入在網域名稱系統（DNS）中參照的電腦名稱稱。 
    
- **內部 IPv4 位址**：輸入此電腦內部網路介面卡（NIC）的 IPv4 位址。
    
- 您可以設定與此電腦關聯的 [**存取邊緣服務****外部 IPv4 位址**]
    
    > [!IMPORTANT]
    > 如果您已選取針對 Edge 伺服器設定使用單一 IP 位址，您將只能編輯存取邊緣服務的外部 IPv4 位址。 其他邊緣服務將與存取邊緣服務共用相同的 IPv4 位址。 
  
- 如果可供編輯，您可以設定**網路會議服務**與此電腦相關聯的**外部 IPv4 位址**
    
- 如果可供編輯，您可以設定與此電腦相關聯**的 A/V Edge 服務****外部 IPv4 位址**
    
- 如果可供編輯，您可以設定與此電腦關聯的**NAT 啟用公用 IPv4 位址**。
    
    > [!IMPORTANT]
    > 如果您選擇為 A/V 邊緣服務提供網路位址轉譯（NAT），就可以編輯**支援 NAT 之公用 IPv4 位址**的 configuration 屬性
  
  **確定**：接受並認可對話方塊的變更。
  
  **取消**：捨棄變更，並關閉對話方塊。
  
  **說明**：顯示此說明畫面。
  

