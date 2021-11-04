---
title: 新增 Survivable Branch Appliance PSTN
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 若要在分支網站定義 Survivable Branch Appliance 的公用交換電話網路 (PSTN) 閘道，請指定下列各項：
ms.openlocfilehash: 1b8470f88217a5ded93094bc83cc0f31c8c916ca
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745089"
---
# <a name="add-survivable-branch-appliance-pstn"></a>新增 Survivable Branch Appliance PSTN
 
若要在分支網站定義 Survivable Branch Appliance 的公用交換電話網路 (PSTN) 閘道，請指定下列各項： 
  
- Survivable Branch Appliance 或 Survivable Branch 伺服器關聯之對等閘道的完整網域名稱 (FQDN) 或 IP 位址，以用於傳送撥入和撥出 PSTN 通話。
    
    > [!IMPORTANT]
    > 如果您是在定義 Survivable Branch Appliance，此為 Survivable Branch Appliance 內之中繼伺服器將會連線以進行 PSTN 連線功能的閘道。 
  
- 要用於工作階段初始通訊協定 (SIP) 訊息的聆聽連接埠。根據預設，在閘道、專用交換機 (PBX) 或工作階段界限控制器 (SBC) 上，連接埠為 5066 (針對傳輸控制通訊協定 (TCP)) 及 5067 (針對傳輸層安全性 (TLS))。在分支網站的 Survivable Branch Appliance，預設連接埠為 5081 (針對 TCP) 及 5082 (針對 TLS)。
    
- 基於安全性考量，我們強烈建議您使用 TLS。如果您是在定義 Survivable Branch Appliance，請參閱您的 Survivable Branch Appliance 廠商文件，確認您的 Survivable Branch Appliance 支援 TLS 通訊協定。
    
    > [!IMPORTANT]
    > 基於安全性考量，強烈建議您部署可以使用 TLS 的閘道。 
  
> [!NOTE]
> 如果您想要新增 PSTN 閘道，您可以稍後再設定它，但在定義及設定好 PSTN 閘道之前，完整的功能將會受限。 
  

