---
title: Skype 會議室系統和商務用 Skype 同盟合作夥伴
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 閱讀此主題以瞭解如何設定商務用 Skype 同盟協力廠商的 Skype 會議室系統。
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820803"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 會議室系統和商務用 Skype 同盟合作夥伴
 
閱讀此主題以瞭解如何設定商務用 Skype 同盟協力廠商的 Skype 會議室系統。
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype 會議室系統和商務用 Skype 同盟合作夥伴

Skype 會議室系統依賴行事曆會議邀請中的 [加入商務用 Skype 會議] 連結。 在會議邀請中，通常會找到匯合連結。 不過，Skype 室系統會視此連結出現在郵件的 MAPI 屬性中。 當此會議要求傳送給遠端組織 (商務用 Skype 同盟協力廠商) 時，遠端組織的 Skype 室系統預設不會在行事曆上顯示會議加入連結。 實際上，遠端組織中的任何 Outlook 使用者將無法使用 [行事曆] 專案的右擊或從會議提醒中，加入商務用 Skype 會議。 他們必須開啟會議邀請，然後按一下郵件本文中的 [加入商務用 Skype 會議]。 
  
這種限制的原因是，Outlook 和 Microsoft Exchange 不會使用特殊的方法，封裝在網際網路上傳送郵件的資訊。 從 Exchange 組織外部傳送的郵件預設會停用此方法（稱為傳輸中性封裝格式 (TNEF) ）。 若要讓會議加入連結出現在遠端 Skype 會議室系統上，傳送組織必須使用下列命令來啟用 TNEF：
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

針對遠端組織啟用 TNEF 後，透過網際網路傳送給組織的任何郵件都會以 TNEF 格式的附件形式傳送。 啟用 TNEF 時，商務用 Skype 會議要求傳送至商務用 Skype 同盟協力廠商時，Skype 會議室系統將能夠轉譯 Join 商務用 Skype 會議，而遠端使用者將可以加入商務用 Skype 會議。 
