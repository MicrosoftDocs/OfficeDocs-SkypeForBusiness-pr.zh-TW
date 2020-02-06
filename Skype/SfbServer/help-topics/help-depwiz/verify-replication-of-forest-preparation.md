---
title: 驗證樹系準備中的複寫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 若要確認在林準備期間複製通用類別目錄與建立物件，請執行下列動作：
ms.openlocfilehash: 5f02707b8a98ec9869aa2b2b4d867bb45351371b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823277"
---
# <a name="verify-replication-of-forest-preparation"></a>驗證樹系準備中的複寫
 
若要確認在林準備期間複製通用類別目錄與建立物件，請執行下列動作：
  
1. 在網網域控制站（最好是位於其他網網域控制站的遠端網站中），在執行目錄林準備的林中，開啟**Active Directory 使用者和電腦**。
    
2. 在**Active Directory 使用者和電腦**中，展開您的林或子域的功能變數名稱。
    
3. 按一下左側窗格中的 [**使用者**] 容器，然後在右側窗格中尋找 [通用群組] CsAdministrator。 如果 CsAdministrator （八個其他以 Cs 開頭的新通用群組）都存在，則表示已成功完成目錄林準備的複製。
    
4. 如果該群組尚不存在，您可以強制進行複製，或等候15分鐘，然後重新整理右側窗格。 當群組存在時，複製就完成了。
    
> [!TIP]
> 如果您想要查看由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行步驟之 Active Directory 網域服務使用者的 [使用者] 目錄中，找到已執行 [部署嚮導] 的電腦上的日誌檔。 例如，如果使用者是以網域 Contoso.net 的網域管理員身分登入，則記錄檔案位於： C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

