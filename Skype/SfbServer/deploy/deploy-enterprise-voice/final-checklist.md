---
title: 商務用 Skype Server 的通話許可控制部署最終檢查清單
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 在商務用 Skype Server 企業語音中 (CAC) 部署通話許可控制的最終檢查清單。
ms.openlocfilehash: ca9162604d1a25ecbde0df800e891931cd756d99
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855107"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>通話許可控制部署：商務用 Skype Server 的最終檢查清單
 
在商務用 Skype Server 企業語音中 (CAC) 部署通話許可控制的最終檢查清單。 
  
使用下列檢查清單，確認您已完成所有必要的設定工作，以將通話許可控制部署 (CAC) 。
  
- 如果已部署一或多部 Edge Server，則每個外部介面 IP 位址都必須新增至網路設定設定中的子網清單，而位元遮罩為32。 您也應該針對部署 A/V Edge service 的地理位置，將該子網 (IP 位址) 與網路網站識別碼產生關聯。
    
    > [!NOTE]
    > 不需要 Edge Server 來執行 CAC。 
  
- 確定已啟用 CAC，如在[商務用 Skype Server 中啟用通話許可控制](enable-call-admission-control.md)中所指定。
    
- 確定所有中央網站皆已啟用 CAC。 這可以透過拓撲產生器來完成。 如果您發佈時產生警告，  *請勿*  略過。
    
- 請確定 [網路設定] 中已設定商業網路中所管理的所有子網。 將每個子網與網路網站相關聯也是必要的，如在[商務用 Skype 中部署網路地區、網站和子網](deploy-network.md)所述。
    
- 請確定所有前端伺服器、Survivable 分支裝置 (Sba) 、Audio/Video 會議服務器 (如在不同的集區) 中，以及在 [網路設定] 中設定轉送伺服器時的子網或 IP 位址。
    

