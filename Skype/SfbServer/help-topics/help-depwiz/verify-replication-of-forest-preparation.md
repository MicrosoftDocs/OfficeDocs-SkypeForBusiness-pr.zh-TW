---
title: 驗證樹系準備中的複寫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 若要確認在樹系準備過程中，通用類別目錄的複寫和物件的建立已成功，請執行下列操作：
ms.openlocfilehash: 06f72e381ac44050253e2dfc181fe194700969fe
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623995"
---
# <a name="verify-replication-of-forest-preparation"></a>驗證樹系準備中的複寫
 
若要確認在樹系準備過程中，通用類別目錄的複寫和物件的建立已成功，請執行下列操作：
  
1. 在網域控制站上 (首選于從其他網域控制站的遠端網站) ，在執行樹系準備的樹系中，開啟 [ **Active Directory 使用者和電腦**]。
    
2. 在 [ **Active Directory 使用者及電腦**] 中，展開樹系或子域的功能變數名稱。
    
3. 按一下左側窗格中的 [ **使用者** ] 容器，然後在右側窗格中尋找通用群組 CsAdministrator。 如果 CsAdministrator (其他八個以 Cs) 開頭的新通用群組都存在，樹系準備的複寫已成功完成。
    
4. 如果群組 (s) 尚未存在，您可以強制複寫或等候15分鐘，然後重新整理右側窗格。 當群組存在時，就會完成複寫。
    
> [!TIP]
> 如果您想要查看由商務用 Skype Server 部署嚮導所建立的記錄檔，您可以在執行該步驟的 Active directory 網域服務使用者的使用者目錄中，找到執行部署嚮導之電腦上的記錄檔。 例如，如果使用者登入網域 Contoso.net 中的網域管理員，則記錄檔位於： C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

