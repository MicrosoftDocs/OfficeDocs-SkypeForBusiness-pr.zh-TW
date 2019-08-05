---
title: 通話品質儀表板 (CQD) 的專案服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '摘要: 瞭解 [通話品質] 儀表板的 [知識庫 API] 中的專案服務。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: 585ba97d9dedbfcbbd572069a792a121e6156afe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186880"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>通話品質儀表板 (CQD) 的專案服務
 
**摘要:** 瞭解 [通話品質] 儀表板的 [知識庫 API] 中的專案服務。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。
  
## <a name="item-service"></a>專案服務

知識庫 API 提供簡單的內容管理服務 (稱為「專案服務」), 可用來儲存任何應用程式定義的內容供使用者使用。 
  
系統內容是由系統使用者所擁有, 且由所有擁有唯讀存取權的使用者共用。 專用的使用者內容是由一般使用者所擁有, 而且只有擁有者可以修改或刪除, 但所有使用者仍能以唯讀方式存取。
  
> [!NOTE]
> 這個 API 檔涵蓋知識庫 API 的唯讀作業。 
  
通話品質儀表板將報表和查詢儲存為知識庫資料庫中的專案。 專案可以有選用的子專案, 而 [通話品質儀表板] 會使用 [子專案] 功能來組織階層結構中的報告和查詢。
  
專案服務包含下列概念:
  
- **專案**-知識庫的基本元素。 每個專案都是由恰好一個使用者所擁有。
    
- **子專案**-知識庫的基本組織結構。 專案可以有零個、一或多個從屬專案。
    
- **專案上級**(專案的清單), 從最上方的專案開始, 這是使用者的預設專案, 會引出至指定專案。
    
- **專案內容**-儲存在專案中的特定應用程式內容。 [通話品質儀表板] 會將報表和查詢的 JSON 表示形式儲存在內容中。
    
其餘的作業包括在下表中。
  

|**一道**|**說明**|
|:-----|:-----|
|[取得專案](get-items.md) <br/> |[取得專案] 會傳回知識庫中的所有專案。  <br/> |
|[取得專案](get-item.md) <br/> |[取得專案] 會傳回特定專案。  <br/> |
|[取得子專案](get-sub-items.md) <br/> |[取得子專案] 會傳回特定專案的子專案。  <br/> |
|[取得專案上級](get-item-ancestors.md) <br/> |取得專案上級會傳回特定專案的上級。  <br/> |
|[更新專案](update-item.md) <br/> |更新存儲庫中的特定專案。  <br/> |
   

