---
title: 新增 A/V MCU 集區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: 中央網站裡，沒有配置音訊/視訊會議服務的所有 Enterprise Edition 前端伺服器，可以使用相同的獨立式 A/V 會議集區。針對每個 A/V 會議集區，您必須指定集區的完整網域名稱 (FQDN)，以及它是否將只有單一 A/V 會議伺服器，還是多個負載平衡的 A/V 會議伺服器。
ms.openlocfilehash: 114d67f6643fe2629cf3a6c1a72daa70eb2db65f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626865"
---
# <a name="add-av-mcu-pool"></a>新增 A/V MCU 集區
 
中央網站裡，沒有配置音訊/視訊會議服務的所有 Enterprise Edition 前端伺服器，可以使用相同的獨立式 A/V 會議集區。針對每個 A/V 會議集區，您必須指定集區的完整網域名稱 (FQDN)，以及它是否將只有單一 A/V 會議伺服器，還是多個負載平衡的 A/V 會議伺服器。
  
> [!IMPORTANT]
> 您無法將單一伺服器的集區轉換成多伺服器的集區。如果您後來決定組織需要多伺服器的集區，必須刪除單一伺服器的集區，然後新增多伺服器的集區。 
  
> [!TIP]
> 如果您打算未來實作 A/V 會議集區，請選取 [多部電腦集區]。 即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。 當您準備好將更多電腦新增至集區之後，您必須重新建立拓撲產生器以定義新的集區成員、發佈新的拓撲，然後透過商務用 Skype Server 部署嚮導設定新的 A/V 會議集區成員。 A/V 會議伺服器集區是獨一無二的，它們不需要負載平衡器便能建立集區。 A/V 會議集區內部即具有負載平衡，不需要使用額外的硬體。 
  

