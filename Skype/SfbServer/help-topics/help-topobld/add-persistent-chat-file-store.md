---
title: 新增常設聊天室檔案存放區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: 您必須指定檔案共用，作為 Standard Edition Server 或 Enterprise Edition 前端集區的檔案存放區。您可以使用現有的檔案共用作為檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於的檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。
ms.openlocfilehash: f11443f8c10db35d5ffb8bfdbfc03d9826700b7c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820675"
---
# <a name="add-persistent-chat-file-store"></a>新增常設聊天室檔案存放區
 
您必須指定檔案共用，作為 Standard Edition Server 或 Enterprise Edition 前端集區的檔案存放區。您可以使用現有的檔案共用作為檔案存放區，也可以指定新的檔案共用。若要指定新的檔案共用，請指定檔案共用將位於的檔案伺服器的完整網域名稱 (FQDN)，以及要作為新檔案共用的資料夾名稱。
  
> [!IMPORTANT]
> 商務用 Skype Server 的檔案共用無法位於企業版前端伺服器上，但可以在標準版伺服器上找到。 
  
> [!IMPORTANT]
> 您可以先在拓撲產生器中定義檔案共用，然後才建立檔案共用；但是您必須先在您定義的位置中建立檔案共用，才能發行拓撲。 
  
> [!IMPORTANT]
> 當您新增持久聊天伺服器或持久聊天伺服器池至您的拓撲時，拓撲建立器必須能夠設定檔案存放區，並在檔案共用上設定要用於檔案存放區的隨機存取控制清單（Dacl）。 這表示，當您執行拓撲產生器以發行新的拓撲時，您必須以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。 
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃常設聊天室伺服器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[在商務用 Skype Server 2015 拓撲中新增持久聊天伺服器](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[常設聊天室伺服器的硬體與軟體需求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[商務用 Skype Server 2015 的拓撲基本知識](../../plan-your-deployment/topology-basics/topology-basics.md)
