---
title: 新增 A/V MCU 池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: 沒有 collocated A/V 會議服務的中央網站所有企業版前端伺服器都可以使用相同的獨立 A/V 會議池。 針對每個 A/V 會議池, 您必須指定該池的完整功能變數名稱 (FQDN), 以及它將只具有單一 A/V 會議伺服器或多個負載平衡的 A/V 會議伺服器。
ms.openlocfilehash: b854e7ecaeed13bd7df15c3ac0439323f3deb311
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193688"
---
# <a name="add-av-mcu-pool"></a>新增 A/V MCU 池
 
沒有 collocated A/V 會議服務的中央網站所有企業版前端伺服器都可以使用相同的獨立 A/V 會議池。 針對每個 A/V 會議池, 您必須指定該池的完整功能變數名稱 (FQDN), 以及它將只具有單一 A/V 會議伺服器或多個負載平衡的 A/V 會議伺服器。
  
> [!IMPORTANT]
> 您無法將單一伺服器池轉換成多重伺服器池。 如果您稍後決定您的組織需要多伺服器池, 您必須刪除單一伺服器池, 然後新增多重伺服器池。 
  
> [!TIP]
> 如果您打算在將來實施 A/V 會議池, 請選取 [**多個電腦池**]。 即使集區定義為兩部以上負載平衡的電腦，您仍可建立單一電腦集區，並為單一電腦建立集區 FQDN。 當您準備好要在池中新增更多電腦之後, 您必須重新建立拓撲建立器, 才能定義新的池成員、發佈新的拓撲, 然後透過商務用 Skype Server 部署嚮導來設定新的 A/V 會議池成員。 A/V 會議伺服器池不需要負載平衡器即可建立池, 因此是唯一的。 A/V 會議池會在內部進行負載平衡, 而且不需要額外的硬體。 
  

