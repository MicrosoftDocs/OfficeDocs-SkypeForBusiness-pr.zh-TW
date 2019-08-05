---
title: 新增 Survivable Branch Appliance PSTN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: '若要為分支網站上的 Survivable 分支裝置定義公用交換電話網絡 (PSTN) 閘道, 請指定以下專案:'
ms.openlocfilehash: 3a146a5bf9b879681b0d490a1d03198853c72305
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193562"
---
# <a name="add-survivable-branch-appliance-pstn"></a>新增 Survivable Branch Appliance PSTN
 
若要為分支網站上的 Survivable 分支裝置定義公用交換電話網絡 (PSTN) 閘道, 請指定以下專案: 
  
- 閘道對等的完整功能變數名稱 (FQDN) 或 IP 位址, Survivable 分支裝置或 Survivable 分支伺服器會與路由輸入和輸出 PSTN 通話相關聯。
    
    > [!IMPORTANT]
    > 如果您是定義 Survivable 分支裝置, 則這是 Survivable 分支裝置中的中繼伺服器將連接至 PSTN 連接的閘道。 
  
- 要用於工作階段初始通訊協定 (SIP) 訊息的聆聽連接埠。根據預設，在閘道、專用交換機 (PBX) 或工作階段界限控制器 (SBC) 上，連接埠為 5066 (針對傳輸控制通訊協定 (TCP)) 及 5067 (針對傳輸層安全性 (TLS))。在分支網站的 Survivable Branch Appliance，預設連接埠為 5081 (針對 TCP) 及 5082 (針對 TLS)。
    
- 基於安全考量，強烈建議您使用 TLS。 如果您是定義 Survivable 分支裝置, 請參閱 Survivable 分支裝置轉銷商檔, 確認您的 Survivable 分支裝置支援 TLS 通訊協定。
    
    > [!IMPORTANT]
    > 基於安全性考量，強烈建議您部署可以使用 TLS 的閘道。 
  
> [!NOTE]
> 如果您想要新增 PSTN 閘道，您可以稍後再設定它，但在定義及設定好 PSTN 閘道之前，完整的功能將會受限。 
  

