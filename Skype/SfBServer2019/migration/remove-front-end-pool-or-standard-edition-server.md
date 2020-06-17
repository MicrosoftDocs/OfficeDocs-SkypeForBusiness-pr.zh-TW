---
title: 移除前端集區或 Standard Edition Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本主題將引導您完成移除前端集區或 Standard Edition 前端伺服器的程式。 當您移除前端集區時，會移除屬於集區的所有前端伺服器，作為集區移除程式的一部分。 當您移除 Standard Edition 前端伺服器時，必須從拓撲產生器移除 SQL 存放區定義。
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752275"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>移除前端集區或 Standard Edition Server

本文將引導您完成移除前端集區或 Standard Edition 前端伺服器的程式。 當您移除前端集區時，會移除屬於集區的所有前端伺服器，作為集區移除程式的一部分。 當您移除 Standard Edition 前端伺服器時，必須從拓撲產生器移除 SQL 存放區定義。
  
## <a name="to-remove-a-front-end-server-pool"></a>移除前端伺服器集區

1. 開啟拓撲產生器。
    
2. 流覽至 [舊版] 節點。
    
3. 展開 [ **Enterprise Edition 前端**集區]，展開前端集區，以滑鼠右鍵按一下您要移除的前端集區，然後按一下 [**刪除**]。
    
4. 發佈拓撲，檢查複寫狀態，然後視需要執行舊版部署嚮導。 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a>移除 Standard Edition 前端伺服器

1. 開啟拓撲產生器。
    
2. 流覽至 [舊版安裝] 節點。
    
3. 展開 [ **Standard Edition 前端伺服器**]，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [**刪除**]。
    
4. 展開 **[SQL 存放區**]，以滑鼠右鍵按一下與 Standard Edition 前端伺服器相關聯的 SQL Server 資料庫，然後按一下 [**刪除**]。
    
    > [!IMPORTANT]
    > 您必須從 Standard Edition 前端伺服器移除組合 SQL Server 資料庫的定義。 
  
5. 發佈拓撲，檢查複寫狀態，然後視需要執行部署嚮導。 
    

