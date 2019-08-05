---
title: 從池中移除前端伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 前端伺服器不能以獨立電腦的形式存在。 它必須定義為前端池, 即使池中只有一個電腦。
ms.openlocfilehash: 5c1cd06e4cbe5cd6cecd8484e9c7874fb5ba590e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193283"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>從池中移除前端伺服器

前端伺服器不能以獨立電腦的形式存在。 它必須定義為前端池, 即使池中只有一個電腦。
  
本主題將引導您完成從現有的前端池移除個別前端伺服器的程式。 如果前端伺服器是池中的最後一個伺服器, 或如果您要徹底移除該資源池, 請參閱[移除前端池或標準版伺服器](remove-front-end-pool-or-standard-edition-server.md)。 移除前端池前, 不需要移除個別的前端伺服器。 移除該池後, 就會移除每個前端伺服器。
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>從池中移除前端伺服器

1. 在商務用 Skype Server 2019 前端伺服器上, 開啟拓撲建立器。
    
2. 流覽至舊版 [安裝] 節點。
    
3. 展開 [**企業版前端池**], 展開要移除之前端伺服器的 [前端] 池, 以滑鼠右鍵按一下您要移除的前端伺服器, 然後按一下 [**刪除**]。
    

