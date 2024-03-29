---
title: 新增常設聊天室檔案存放區
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: 您必須指定要用來做為 Standard Edition server 或 Enterprise Edition 前端集區之檔案存放區的檔案共用。 您可以使用檔案存放區現有的檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。
ms.openlocfilehash: d049f84307d5bd9d2db0e833dbb44b85164e6cd6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391205"
---
# <a name="add-persistent-chat-file-store"></a>新增常設聊天室檔案存放區
 
您必須指定要用來做為 Standard Edition server 或 Enterprise Edition 前端集區之檔案存放區的檔案共用。 您可以使用檔案存放區現有的檔案共用，也可以指定新的檔案共用，方法是指定檔案共用所在的檔案伺服器的完整功能變數名稱 (FQDN) ，以及新檔案共用的資料夾名稱。
  
> [!IMPORTANT]
> 商務用 Skype Server 的檔案共用不能位於 Enterprise Edition 前端伺服器上，但可位於 Standard Edition 伺服器上。 
  
> [!IMPORTANT]
> 您可以先在拓撲產生器中定義檔案共用，然後才建立檔案共用；但是您必須先在您定義的位置中建立檔案共用，才能發行拓撲。 
  
> [!IMPORTANT]
> 當您將 Persistent Chat Server 或 Persistent Chat Server 集區新增至您的拓撲時，拓撲產生器必須能夠設定檔案存放區，並設定檔案存放區 (Dacl) 上的自由存取控制清單，以用於檔案存放區。 這表示，當您執行拓撲產生器以發行新的拓撲時，您必須以具有檔案共用的完整控制權限 (讀取/寫入/修改) 的帳戶登入。 
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 2015 中規劃 Persistent Chat Server](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[將 Persistent Chat Server 新增至您的商務用 Skype Server 2015 拓撲](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[商務用 Skype Server 2015 中的 Persistent Chat Server 的硬體和軟體需求](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[商務用 Skype Server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[商務用 Skype Server 2015 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)
