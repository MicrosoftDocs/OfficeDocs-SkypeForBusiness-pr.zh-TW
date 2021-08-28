---
title: 從集區中移除前端伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 前端伺服器不能以獨立電腦形式存在。 它必須定義為前端集區，即使集區中只有一部電腦也一樣。
ms.openlocfilehash: b52954421034d83191e479e59d1efeeda8972868
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594997"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>從集區中移除前端伺服器

前端伺服器不能以獨立電腦形式存在。 它必須定義為前端集區，即使集區中只有一部電腦也一樣。
  
本主題將引導您完成從現有前端集區移除個別前端伺服器的程式。 如果前端伺服器是集區中的最後一部伺服器，或您要完全移除集區，請參閱[移除前端集區或 Standard Edition 伺服器](remove-front-end-pool-or-standard-edition-server.md)。 移除前端集區之前，不需要先移除個別的前端伺服器。 當您移除集區時，會移除每個前端伺服器。
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>從集區移除前端伺服器

1. 在商務用 Skype Server 2019 前端伺服器上，開啟拓撲產生器。
    
2. 流覽至 [舊版安裝] 節點。
    
3. 展開 **Enterprise Edition 前端** 集區，展開要移除前端伺服器的前端集區，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [**刪除**]。
    

