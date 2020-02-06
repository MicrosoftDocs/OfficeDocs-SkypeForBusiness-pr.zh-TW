---
title: 移除前端集區或 Standard Edition Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本主題將引導您完成移除前端池或標準版前端伺服器的程式。 當您移除 [前端] 池時，您會將屬於該池的每個前端伺服器移除為 [池移除] 程式的一部分。 當您移除標準版前端伺服器時，必須從拓撲建立器移除 SQL Store 定義。
ms.openlocfilehash: d3397b47f94a96cde3326b2479a9e5c6ffd365e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813001"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>移除前端集區或 Standard Edition Server

本文將引導您完成移除前端池或標準版前端伺服器的程式。 當您移除 [前端] 池時，您會將屬於該池的每個前端伺服器移除為 [池移除] 程式的一部分。 當您移除標準版前端伺服器時，必須從拓撲建立器移除 SQL Store 定義。
  
## <a name="to-remove-a-front-end-server-pool"></a>移除前端伺服器池

1. 開啟拓撲建立器。
    
2. 流覽至 [舊版] 節點。
    
3. 展開 [**企業版前端] 池**、展開 [前端] 池、以滑鼠右鍵按一下您要移除的 [前端] 池，然後按一下 [**刪除**]。
    
4. 發佈拓撲、檢查複製狀態，然後視需要執行舊版部署嚮導。 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>移除標準版前端伺服器

1. 開啟拓撲建立器。
    
2. 流覽至 [舊版安裝] 節點。
    
3. 展開 [**標準版前端伺服器**]，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [**刪除**]。
    
4. 展開 **[SQL] 商店**，以滑鼠右鍵按一下與標準版前端伺服器相關聯的 SQL Server 資料庫，然後按一下 [**刪除**]。
    
    > [!IMPORTANT]
    > 您必須從標準版前端伺服器移除 collocated SQL Server 資料庫的定義。 
  
5. 發佈拓撲，檢查複製狀態，然後視需要執行部署嚮導。 
    

