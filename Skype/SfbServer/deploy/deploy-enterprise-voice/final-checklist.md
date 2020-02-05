---
title: 呼叫許可控制部署商務用 Skype Server 的最終檢查清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: 在商務用 Skype Server Enterprise Voice 中部署通話許可控制（CAC）的最終檢查清單。
ms.openlocfilehash: 5d5e4f6f40143bfec2a215e6bc9a54817d53da1b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767226"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a>呼叫許可控制部署：適用于商務用 Skype Server 的最終檢查清單
 
在商務用 Skype Server Enterprise Voice 中部署通話許可控制（CAC）的最終檢查清單。 
  
使用下列檢查清單來確認您已完成所有必要的設定工作，以部署呼叫許可控制（CAC）。
  
- 如果一或多個邊緣伺服器已部署，則必須將每個外部介面 IP 位址新增到 [網路設定] 中的子網清單中，位元遮罩為32。 您也應該將這個子網（IP 位址）與「A/V Edge」服務所部署之地理位置的 [網路 site ID] 建立關聯。
    
    > [!NOTE]
    > Edge 伺服器不是實現 CAC 所必需的。 
  
- 請確定您已啟用 CAC，如在[商務用 Skype Server 的 [啟用呼叫許可控制](enable-call-admission-control.md)] 中所述。
    
- 確定所有中央網站都已啟用 CAC。 這可以透過拓撲產生器完成。 如果您發佈時產生警告，*請勿*忽略。
    
- 確認在商業網路中管理的所有子網都已設定在 [網路設定] 中。 在[商務用 Skype 中部署網路區域、網站和子網](deploy-network.md)中所述，您也必須將每個子網與網路網站相關聯。
    
- 確定所有前端伺服器、Survivable 分支裝置（SBAs）、音訊/視訊會議伺服器（如果在個別的池中），以及在 [網路設定] 設定中設定了轉送伺服器的子網或 IP 位址。
    

